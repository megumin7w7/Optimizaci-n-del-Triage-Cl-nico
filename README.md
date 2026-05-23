<div align="center">

# 🏥 Optimización del Triage Clínico

<img src="https://readme-typing-svg.herokuapp.com?font=Lexend+Giga&size=28&pause=1000&color=4A90E2&center=true&vCenter=true&width=750&lines=Machine+Learning+Aplicado+a+Salud;Feature+Engineering;Predicción+Temprana+de+Diabetes;Python+y+Scikit-Learn" />

<br>

![Python](https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange?style=for-the-badge&logo=scikitlearn)
![XGBoost](https://img.shields.io/badge/XGBoost-Boosting-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completado-green?style=for-the-badge)

</div>

---

<div align="center">

## 🚀 Navegación Rápida

<a href="#-descripción"><kbd> Descripción </kbd></a>
<a href="#-dataset"><kbd> Dataset </kbd></a>
<a href="#-metodología"><kbd> Metodología </kbd></a>
<a href="#-hallazgos-clave"><kbd> Hallazgos Clave </kbd></a>
<a href="#-tecnologías"><kbd> Tecnologías </kbd></a>
<a href="#-ejecución"><kbd> Ejecución </kbd></a>

</div>

---

# 📌 Descripción

Este repositorio contiene el desarrollo de un pipeline de clasificación para la detección temprana de diabetes mediante técnicas de **Machine Learning** e **Ingeniería de Variables (Feature Engineering)**.

El proyecto compara modelos interpretables como **Regresión Logística** frente a modelos de ensamblaje más complejos como **Random Forest** y **XGBoost**, evaluando si la transformación inteligente de variables puede competir contra algoritmos más sofisticados.

Además, se implementa un sistema robusto de validación utilizando métricas estadísticas y análisis comparativos de Odds Ratios para medir el impacto real del Feature Engineering sobre el poder predictivo del modelo.

---

## 🎯 Objetivos del Proyecto

* Diseñar variables derivadas basadas en lógica clínica.
* Aplicar técnicas de Feature Engineering para mejorar la predicción.
* Comparar modelos lineales y modelos ensemble.
* Interpretar variables mediante Odds Ratios y Feature Importance.
* Analizar si la complejidad algorítmica realmente mejora el rendimiento clínico.

---

# 📂 Dataset

<div align="center">
<img src="https://cdn-icons-png.flaticon.com/512/2966/2966487.png" width="120"/>
</div>

* **Fuente de datos:** `Pima Indians Diabetes Database`
* **Origen:** UCI Machine Learning Repository / Kaggle
* **Población:** Mujeres de ascendencia Pima mayores de 21 años.
* **Variable Objetivo:** `Outcome`
  * `1` → Diabetes
  * `0` → No Diabetes

---

## 📊 Variables Analizadas

### Variables Originales
* `Glucosa`
* `IMC`
* `Edad`
* `Insulina`
* `Presion_Sanguinea`
* `Embarazos`
* `Funcion_Pedigree`

### Variables Generadas (Feature Engineering)
* `Presion_Sanguinea_div_Glucosa`
* `Ratio_Presion_IMC`
* `IMC_Categoria_Obesidad`
* `Edad_Categoria_Joven`

Estas variables fueron creadas para representar relaciones fisiológicas y patrones clínicos no lineales.

---

# ⚙️ Metodología

El flujo de trabajo sigue una estructura completa de Ciencia de Datos aplicada a salud:

---

## 1️⃣ Preprocesamiento

* Limpieza de datos
* Imputación de valores fisiológicamente inválidos
* Escalado mediante `StandardScaler`
* Manejo de outliers

---

## 2️⃣ Feature Engineering

Se generaron nuevas variables derivadas para capturar relaciones clínicas complejas:

* Ratios fisiológicos
* Variables categóricas mediante binning
* Relaciones entre IMC, presión y glucosa

---

## 3️⃣ Selección de Variables

Se aplicaron técnicas híbridas de selección:

* ANOVA F-Test
* Random Forest Feature Importance
* Lasso (L1 Regularization)

---

## 4️⃣ Modelado

Se entrenaron múltiples algoritmos:

* Regresión Logística
* Random Forest
* XGBoost
* Gradient Boosting
* SVM
* KNN
* AdaBoost

---

## 5️⃣ Validación

Evaluación mediante:

* ROC-AUC
* Accuracy
* F1-Score
* Matriz de Confusión
* Odds Ratios
* Comparación Raw vs Feature Engineering

---

# 💡 Hallazgos Clave y Conclusiones

A través del análisis comparativo entre variables originales y variables creadas mediante Feature Engineering se obtuvieron los siguientes resultados:

---

## 🧠 Variables Dominantes

Las variables clínicas originales continúan siendo los predictores más fuertes:

* `Glucosa`
* `IMC`
* `Funcion_Pedigree`

Especialmente `Glucosa`, que mostró el Odds Ratio más elevado del modelo.

---

## ⚗️ Impacto del Feature Engineering

El Feature Engineering sí aportó mejoras interpretables:

* Algunas variables derivadas ingresaron al Top 10 del modelo.
* Variables como `Presion_Sanguinea_div_Glucosa` mostraron capacidad predictiva adicional.
* El rendimiento general mejoró moderadamente sin generar sobreajuste.

---

## ⚖️ Interpretabilidad vs Complejidad

Aunque modelos como Random Forest y XGBoost lograron resultados competitivos:

* La Regresión Logística mantuvo alta interpretabilidad clínica.
* El incremento de complejidad no siempre justificó la pérdida de transparencia.

---

## 📈 Conclusión General

El proyecto demuestra que:

> Un buen Feature Engineering puede acercar modelos simples a rendimientos similares a modelos complejos, manteniendo interpretabilidad clínica y estabilidad estadística.

---

# ⚙️ Tecnologías y Librerías

El proyecto fue desarrollado en **Python 3.12** utilizando:

---

## 🔹 Core
* pandas
* numpy

## 🔹 Machine Learning
* scikit-learn
* xgboost

## 🔹 Visualización
* matplotlib
* seaborn

## 🔹 Ingeniería de Variables
* feature-engine

## 🔹 Validación Estadística
* scipy

---

# 🚀 Ejecución

Para ejecutar el proyecto localmente:

```bash
git clone <repositorio>
