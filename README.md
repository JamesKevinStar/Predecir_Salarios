# Predicción de Salarios
Este proyecto tiene como objetivo el usar diferentes técnicas de machine learning y ver su rendimiento, para luego ver cuál es el mejor modelo que se adapte a este problema.

## Tabla de Contenidos 
- [Datos](#datos)
- [Metodología](#metodología)
- [Resultados](#resultados)
- [Conclusión](#conclusión)

## Datos 
- El dataset utilizado proviene de la página "Kaggle", el cual se sacó de "Glassdoor", el dataset utilizado se llama [glassdoor_jobs.csv](https://www.kaggle.com/datasets/thedevastator/jobs-dataset-from-glassdoor).
- Los datos son mayormente de puestos en el área de ciencia de datos.

![Dataset](Imágenes/Dataset.png)

## Metodología 

### 1. Exploración de Datos 
- Se realizó una exploración inicial del dataset a cada parámetro.
- No se obtuvieron valores faltantes o nulos, pero si se vió datos que no coinciden con la descripción del atributo.
- También se observó que hay más variables categóricas que numéricas.

### 2. Limpieza de Datos 
- Todos los datos que tenial valores raros se eliminaron, algunos pocos casos de hicieron un cambio en su valor.
- Se limpiaron 265 datos, lo que viene a ser el 27.7197% de los datos originales.

### 3. Conversión de Datos 
- Se convirtieron todos los diferentes títulos de puestos de trabajo a uno genérico que se adecue al original, se intentó usar un LLM para que los categorize, pero como en el cuaderno de google colab solo me dan cierta cantidad de recursos limitados usé un modelo no tan listo, el cual no dio buenos resultado y decidí no hacerlo de esa forma.
- Para los salarios se quitaron las letras, se conservó solo los números, y se promedió su valor. En el caso de los salarios por hora se convirtió a anuales y se promedió.
- En el nombre de la compañia se quitó la última parte de su nombre, que parece que se juntó a los valores de "Rating".
- Finalmente en la parte de Competidores se reemplazó el "-1" por vacío.

### 4. Agregar Valores Importantes
- Se agregó el nivel que piden para el puesto de trabajo, ya sea "junior", "senior" o si no especifica.
- También se calculó el número de competidores que tiene la empresa.
- Se agregó una nueva columna solo con el Estado en el que se solicita el empleo.
- Obtuve la antiguedad de la compañia.
- Finalmente se filtró palabras clave de la descripción del trabajo, para decidir las palabras a usar me ayudé de una IA para que me diera términos comunes en las profesiones que filtré, esos datos se guardaron como valores booleanos (1 = Sí existe) y (0 = No existe).

### 5. Reducción de Dimensionalidad
- Se eliminó todas las columnas innecesarias.
- También se redujo la cantidad de datos borrando los datos atípicos que existian en las variables numéricas.

### 6. Exploración de Datos Limpios
- Se exploró por medio de gráficos las variables que quedaban.

### 7. Transformación de Datos
- En esta etapa se convirtieron los valores categóricos a numéricos.
- Luego con esos valores se usó una "matriz de correlación de pearson" para determinar las variables que sí hacían un impacto en la variable "Salary Estimate".

### 8. Normalización de Datos
- Se normalizaron los datos por 2 métodos "Min-Max Scaling" y "Z-Score", se hicieron pruebas con ambos pero el que dió mejores resultados fue el  "Min-Max Scaling".

### 9. División de Datos 
- En esta parte se dividieron los datos en 80% train y 20% test.

### 10. Implementación de Modelos
- 

### 11. Evaluación de Modelos
- 

![Grupos](Imágenes/Grupos.png)

## Resultados 
- Se pudo comparar varios métodos, de los cuales se pudo obtener los que sobresalieron para esta tarea en específico.
- El "Random Forest" obtuvo los mejores resultados.

![Tabla Comparación](Imágenes/TablaComparacion.png)

- Los resultados muestran que los modelos no son muy buenos para predecir, pero lo hacen de una manera aceptable.

## Conclusión 
Se puede obtener mejores resultados si se juega más con los hiperparámetros de cada modelo, métodos de normalización de datos, división de los datos y demás..
