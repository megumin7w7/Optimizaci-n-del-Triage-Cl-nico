<div align="center">

# 🏥 Optimización del Triage Clínico

<img src="https://readme-typing-svg.herokuapp.com?font=Lexend+Giga&size=26&pause=1000&color=1B3A5C&center=true&vCenter=true&width=700&lines=Machine+Learning+Aplicado+a+Salud;Feature+Engineering;Predicción+de+Diabetes;Python+y+Scikit-Learn" />

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
<a href="#-hallazgos-clave"><kbd> Hallazgos </kbd></a>
<a href="#-tecnologías"><kbd> Tecnologías </kbd></a>

</div>

---

## 📌 Descripción

Este proyecto desarrolla un pipeline de Machine Learning para la detección temprana de diabetes utilizando técnicas de **Feature Engineering**, selección de variables y comparación de modelos predictivos.

El objetivo principal fue evaluar si la creación de variables derivadas podía mejorar el rendimiento de modelos interpretables como la **Regresión Logística**, comparándolos frente a modelos más complejos como **Random Forest** y **XGBoost**.

### Objetivos del proyecto

- Crear variables derivadas con lógica clínica.
- Comparar modelos de clasificación supervisada.
- Analizar el impacto del Feature Engineering sobre los Odds Ratios.
- Evaluar interpretabilidad vs complejidad del modelo.

---

## 📂 Dataset

<div align="center">
<img src="https://cdn-icons-png.flaticon.com/512/2966/2966486.png" width="120"/>
</div>

- **Dataset:** Pima Indians Diabetes Database
- **Fuente:** UCI Machine Learning Repository / Kaggle
- **Variable objetivo:** `Outcome` (Diabetes: Sí / No)

### Variables derivadas creadas

- `Ratio_Insulina_Glucosa`
- `Ratio_IMC_Edad`
- `IMC_Categoria`
- `Presion_Sanguinea_div_Glucosa`

---

## ⚙️ Metodología

El flujo del proyecto siguió las siguientes etapas:

### 1. Preprocesamiento
- Imputación de valores fisiológicos inválidos.
- Escalado de variables.
- Tratamiento de outliers.

### 2. Feature Engineering
- Creación de ratios clínicos.
- Discretización de variables.
- Variables de interacción.

### 3. Selección de Variables
- ANOVA F-Test
- Lasso (L1)
- Importancia por Random Forest

### 4. Modelado
Modelos evaluados:
- Regresión Logística
- Random Forest
- XGBoost
- SVM
- KNN
- AdaBoost

### 5. Validación
- ROC-AUC
- F1-Score
- Bootstrap e Intervalos de Confianza

---

## 💡 Hallazgos Clave

- **Glucosa** continúa siendo el predictor dominante del modelo.
- El **Feature Engineering** mejoró variables relacionadas con IMC y presión sanguínea.
- La **Regresión Logística optimizada** logró competir contra modelos más complejos manteniendo interpretabilidad.
- Algunas variables creadas aportaron estabilidad al modelo, aunque no todas generaron mejoras significativas.

---

## ⚙️ Tecnologías

- Python
- Pandas
- NumPy
- Scikit-Learn
- XGBoost
- Matplotlib
- Seaborn

---
