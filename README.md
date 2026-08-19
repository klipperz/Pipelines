Pipelines de Preprocesamiento
Por: Samuel Angel Cardona
Pipeline de pre-procesamiento con scikit-learn sobre el dataset Chronic Kidney Disease (Kaggle)
Extraido de: https://www.kaggle.com/datasets/salam0340/kidney-disease-dataset
Contenido
Trabajo_Evaluativo_1_Preprocesamiento.ipynb — notebook con el desarrollo completo: mini-EDA, estrategia de imputación y escalamiento, identificación de categorías, un Custom Transformer (FunctionTransformer) para limpieza de texto, el pipeline de pre-procesamiento (ColumnTransformer + Pipeline) y su validación con un modelo de Regresión Logística.
kidney_disease.csv — dataset original.
Dataset y variables usadas

Del dataset original (400 pacientes, 24 variables clínicas) se selecciona un subconjunto de 7 variables predictoras que cumple los requisitos de la guía (mezcla numérica/categórica, baja cardinalidad, datos faltantes reales):

Variable	Tipo	Descripción
age	Numérica continua	Edad
bp	Numérica continua	Presión arterial
hemo	Numérica continua	Hemoglobina
sc	Numérica continua	Creatinina sérica
rbc	Categórica nominal	Glóbulos rojos en orina (normal/abnormal)
dm	Categórica nominal	Diabetes mellitus (yes/no) — texto sucio en crudo ('\tno', ' yes')
appet	Categórica ordinal	Apetito (poor < good)
classification	Target	Diagnóstico (ckd / notckd)
