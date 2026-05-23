<div align="center">

# OPTIMIZACIÓN DEL TRIAGE CLÍNICO

<img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&size=24&pause=1000&color=C9D1D9&center=true&vCenter=true&width=750&lines=Machine+Learning+Applied+to+Healthcare;Feature+Engineering+Pipeline;Clinical+Risk+Modeling;Python+%7C+Scikit-Learn+%7C+XGBoost" />

<br>

![Python](https://img.shields.io/badge/Python-3.12-1f2937?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-0f172a?style=for-the-badge&logo=scikitlearn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-111827?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Stable-374151?style=for-the-badge)

</div>

---

<div align="center">

## QUICK ACCESS

<a href="#description"><kbd> Description </kbd></a>
<a href="#dataset"><kbd> Dataset </kbd></a>
<a href="#methodology"><kbd> Methodology </kbd></a>
<a href="#findings"><kbd> Findings </kbd></a>
<a href="#stack"><kbd> Stack </kbd></a>

</div>

---

# Description

This repository contains the development of a Machine Learning pipeline focused on early diabetes prediction using Feature Engineering and supervised classification models.

The project evaluates whether engineered clinical variables can improve predictive performance and interpretability when compared against more complex ensemble-based approaches.

Main objectives:

- Design clinically meaningful engineered variables
- Compare linear and ensemble models
- Evaluate Feature Engineering impact over Odds Ratios
- Analyze model interpretability vs complexity

---

# Dataset

<div align="center">
<img src="https://cdn-icons-png.flaticon.com/512/2966/2966486.png" width="110"/>
</div>

| Property | Value |
|---|---|
| Dataset | Pima Indians Diabetes Database |
| Source | UCI / Kaggle |
| Target Variable | `Outcome` |
| Task | Binary Classification |

### Engineered Features

- `Ratio_Insulina_Glucosa`
- `Ratio_IMC_Edad`
- `IMC_Categoria`
- `Presion_Sanguinea_div_Glucosa`

---

# Methodology

## Preprocessing

- Invalid physiological value imputation
- Outlier handling
- Standardization

## Feature Engineering

- Clinical ratios
- Variable discretization
- Interaction features

## Feature Selection

- ANOVA F-Test
- Lasso (L1)
- Random Forest Importance

## Models Evaluated

- Logistic Regression
- Random Forest
- XGBoost
- SVM
- KNN
- AdaBoost

## Validation

- ROC-AUC
- F1-Score
- Bootstrap Confidence Intervals

---

# Findings

- `Glucosa` remained the strongest predictor across all experiments.
- Feature Engineering improved the representation of BMI and pressure-related patterns.
- Logistic Regression achieved competitive performance while preserving interpretability.
- Some engineered variables stabilized model behavior despite modest performance gains.

---

# Stack

```bash


[ system stable ]
[ feature engineering loaded ]
[ clinical pipeline initialized ]

</div> ```
