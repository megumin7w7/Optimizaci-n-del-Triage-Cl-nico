🏥 Optimización del Triage Clínico

PythonScikit-LearnXGBoostStatus

🚀 Navegación Rápida
 Descripción  Dataset  Metodología  Hallazgos Clave  Tecnologías  Ejecución 

📌 Descripción
Este repositorio contiene el desarrollo de un pipeline de clasificación para la detección temprana de diabetes, enfocado en reducir la fricción diagnóstica mediante Ingeniería de Variables (Feature Engineering).

El proyecto contrasta modelos lineales interpretables (Regresión Logística) frente a estrategias de ensamblaje complejas (Random Forest, XGBoost), evaluando si la transformación de datos (ratios fisiológicos, binning) puede superar a la complejidad algorítmica pura. Se implementa un sistema de validación robusto mediante Bootstrap e Intervalos de Confianza.

Objetivos técnicos del notebook:

Diseñar variables derivadas que representen lógica clínica (ej: Ratio Insulina/Glucosa).
Implementar un sistema de "Voting" para selección de variables (ANOVA + Lasso + Boruta).
Comparar estabilidad de modelos mediante análisis de varianza (Bootstrap 1000 iteraciones).
Cuantificar el impacto del FE mediante la variación de Odds Ratios.
📂 Dataset

Fuente de datos: Pima Indians Diabetes Database (UCI Machine Learning Repository / Kaggle).
Población: Mujeres de al menos 21 años de ascendencia Pima.
Variable Objetivo: Outcome (Diabetes: 1 / No Diabetes: 0).
Variables clave transformadas:

Glucosa / Insulina → Ratio_Insulina_Glucosa (Indicador de resistencia a la insulina).
IMC / Edad → Ratio_IMC_Edad (Composición corporal relativa).
IMC → IMC_Categoria (Discretización en Normal/Sobrepeso/Obesidad).
⚙️ Metodología
El flujo de trabajo sigue un patrón estricto de Ingeniería de Software aplicado a Datos:

Preprocesamiento: Imputación de ceros fisiológicos mediante mediana y manejo de outliers.
Feature Engineering: Creación de variables de interacción y discretización (Binning) para capturar no-linealidades.
Selección de Variables (Ensemble):
Filter: ANOVA F-test.
Embedded: Lasso (L1) y Random Forest Importance.
Wrapper: Algoritmo BorutaPy.
Decisión: Votación mayoritaria (mínimo 2 métodos confirman la variable).
Modelado y Arena de Comparación:
Entrenamiento de 7 algoritmos (LogReg, RF, XGBoost, SVM, KNN, GBC, AdaBoost).
Optimización de hiperparámetros mediante GridSearchCV.
Validación: Cálculo de métricas (ROC-AUC, F1) con Intervalos de Confianza al 95% (Bootstrapping).
💡 Hallazgos Clave y Conclusiones
A través de la comparación de Odds Ratios (Raw vs. Engineered) y la tabla maestra de modelos:

El Feature Engineering supera al algoritmo: La creación de variables como Ratio_Insulina_Glucosa aumentó significativamente el poder predictivo en comparación con el uso de variables crudas, permitiendo que modelos simples (Regresión Logística) compitan de cerca con ensamblajes complejos.
Estabilidad vs. Complejidad: El análisis de Intervalos de Confianza reveló que, aunque XGBoost ofreció el AUC más alto, su intervalo de confianza se solapaba con el de la Regresión Logística optimizada. Esto sugiere que el aumento de complejidad no justifica la pérdida de interpretabilidad en este caso clínico.
Variables de Decisión: Glucosa e IMC mantienen su posición como predictores dominantes, pero el IMC_Categoria generado artificialmente demostró tener una asociación más fuerte con el resultado que la variable numérica continua original.
⚙️ Tecnologías y Librerías
El desarrollo se realizó en Google Colab (Python 3.12) utilizando un stack optimizado para ciencia de datos:

Core: pandas, numpy
Feature Engineering: feature_engine (Creation, Discretisation, Encoding), category_encoders
Modelado: scikit-learn (Pipelines, GridSearch), xgboost, lightgbm
Selección: boruta
Visualización: matplotlib, seaborn (Paleta Corporativa: #1B3A5C)
🚀 Ejecución
Para reproducir este análisis en un entorno local:

Clona este repositorio.
Instala las dependencias específicas del proyecto:
pip install pandas numpy scikit-learn xgboost lightgbm boruta feature-engine imblearn
Abre el notebook principal optimizacion_triaje_clinico.ipynb en Jupyter o Google Colab.
Ejecuta las celdas secuencialmente. El script descarga automáticamente el dataset desde KaggleHub.
