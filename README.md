# Pipelines de Preprocesamiento

Por: Samuel Angel Cardona

## Pipeline de pre-procesamiento con `scikit-learn` sobre el dataset **Chronic Kidney Disease**
Extraido de: https://www.kaggle.com/datasets/salam0340/kidney-disease-dataset
## Proyecto
 
Este proyecto realiza un análisis sobre un dataset clínico de pacientes con y sin
enfermedad renal crónica, con datos de Kaggle. El objetivo es diseñar e implementar un
pipeline de preprocesamiento capaz de manejar variables numéricas y categóricas (nominales
y ordinales), imputar datos faltantes y limpiar inconsistencias de texto, para dejar los
datos listos para un modelo de clasificación. Se realiza un mini-EDA identificando tipos de
variable, rangos numéricos, datos faltantes y categorías, y se valida el pipeline
entrenando un modelo de Regresión Logística.
 
## Archivos adjuntos
 
* `kidney_disease.csv`: archivo que contiene los datos originales del proyecto.
* `Pipeline`: notebook de Jupyter en el que se realizó la exploración de los datos y el pipeline.

## Dataset y variables usadas
 
Del dataset original (400 pacientes, 24 variables clínicas) se selecciona un subconjunto de
7 variables predictoras que cumple los requisitos de la guía (mezcla numérica/categórica,
baja cardinalidad, datos faltantes reales):
 
| Variable | Tipo | Descripción |
|---|---|---|
| `age` | Numérica continua | Edad |
| `bp` | Numérica continua | Presión arterial |
| `hemo` | Numérica continua | Hemoglobina |
| `sc` | Numérica continua | Creatinina sérica |
| `rbc` | Categórica nominal | Glóbulos rojos en orina (normal/abnormal) |
| `dm` | Categórica nominal | Diabetes mellitus (yes/no) — texto sucio en crudo (`'\tno'`, `' yes'`) |
| `appet` | Categórica ordinal | Apetito (poor < good) |
| `classification` | Target | Diagnóstico (ckd / notckd) |
## Conclusiones
 
En este proyecto se diseñó un pipeline de preprocesamiento con scikit-learn sobre un
subconjunto de 7 variables clínicas (edad, presión arterial, hemoglobina, creatinina
sérica, glóbulos rojos en orina, diabetes mellitus y apetito), iniciando con un mini-EDA,
identificación de datos faltantes y sus estrategias de imputación, y un Custom Transformer
para limpiar inconsistencias reales de texto detectadas en la variable `dm`. El
`ColumnTransformer` garantiza que cada tipo de variable reciba el tratamiento adecuado
(imputación por mediana y escalado para las numéricas, imputación por moda y codificación
one-hot u ordinal según corresponda para las categóricas), y el pipeline completo asegura
reproducibilidad y evita fuga de información al aplicarse de forma idéntica en
entrenamiento y prueba. La validación con Regresión Logística confirma que las variables
seleccionadas están fuertemente asociadas al diagnóstico de enfermedad renal.
