<div align="center">

# ⌬ Clinical Triage Optimization

```text
[ initializing pipeline... ]
[ loading engineered features... ]
[ preparing model arena... ]
[ validating bootstrap confidence... ]
[ system status: stable ]
```

<img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&size=26&pause=1000&color=00D9FF&center=true&vCenter=true&width=850&lines=Machine+Learning+Applied+to+Healthcare;Feature+Engineering+Pipeline;Clinical+Risk+Modeling;Logistic+Regression+vs+XGBoost" />

<br>

![Python](https://img.shields.io/badge/Python-0D1117?style=for-the-badge&logo=python&logoColor=00D9FF)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-111827?style=for-the-badge&logo=scikitlearn&logoColor=7C3AED)
![XGBoost](https://img.shields.io/badge/XGBoost-0F172A?style=for-the-badge&logoColor=22D3EE)
![Status](https://img.shields.io/badge/System-Stable-111827?style=for-the-badge&logoColor=00FFFF)

</div>

---

<div align="center">

## QUICK ACCESS

<a href="#-description"><kbd> Description </kbd></a>
<a href="#-dataset"><kbd> Dataset </kbd></a>
<a href="#-methodology"><kbd> Methodology </kbd></a>
<a href="#-model-arena"><kbd> Model Arena </kbd></a>
<a href="#-findings"><kbd> Findings </kbd></a>
<a href="#-stack"><kbd> Stack </kbd></a>

</div>

---

# ~/description

Machine Learning pipeline focused on early diabetes prediction using Feature Engineering and supervised classification models.

The project evaluates whether engineered clinical variables can compete against complex ensemble architectures while preserving interpretability and model stability.

Main objectives:

- Design clinically meaningful engineered variables
- Compare interpretable and ensemble models
- Evaluate Odds Ratio variation after Feature Engineering
- Analyze interpretability vs predictive complexity

---

# ~/dataset

<div align="center">
<img src="https://cdn-icons-png.flaticon.com/512/2966/2966486.png" width="110"/>
</div>

| Property | Value |
|---|---|
| Dataset | Pima Indians Diabetes Database |
| Source | UCI / Kaggle |
| Task | Binary Classification |
| Target Variable | `Outcome` |

---

## Engineered Features

```bash
> Ratio_Insulina_Glucosa
> Ratio_IMC_Edad
> IMC_Categoria
> Presion_Sanguinea_div_Glucosa
> Ratio_Presion_IMC
```

These engineered variables were created to capture hidden physiological relationships and improve predictive representation.

---

# ~/methodology

## preprocessing

```yaml
invalid_values: imputed
outliers: treated
scaling: StandardScaler
missing_data: handled
```

---

## feature_engineering

```yaml
clinical_ratios: enabled
interaction_features: enabled
binning: enabled
non_linear_patterns: captured
```

---

## feature_selection

```yaml
methods:
  - ANOVA F-Test
  - Lasso (L1)
  - Random Forest Importance
```

---

## validation

```yaml
metrics:
  - ROC-AUC
  - F1-Score
  - Accuracy

bootstrap_iterations: 1000
confidence_interval: 95%
```

---

# ~/model_arena

| Model | Purpose |
|---|---|
| Logistic Regression | Clinical Interpretability |
| Random Forest | Feature Importance |
| XGBoost | Predictive Optimization |
| SVM | Margin Optimization |
| KNN | Local Similarity |
| AdaBoost | Ensemble Benchmark |

---

# ~/findings

```yaml
dominant_predictor: Glucosa
feature_engineering: effective
best_interpretable_model: Logistic Regression
highest_predictive_model: XGBoost
model_stability: high
bootstrap_validation: completed
```

### Key Conclusions

- `Glucosa` remained the strongest predictor across all experiments.
- Feature Engineering improved several pressure and BMI-related relationships.
- Logistic Regression achieved competitive performance while maintaining interpretability.
- Some engineered variables improved stability more than raw predictive power.
- Increasing model complexity did not always justify interpretability loss.

---

# ~/stack

```bash
Python
Pandas
NumPy
Scikit-Learn
XGBoost
Matplotlib
Seaborn
Feature-Engine
SciPy
```

---

<div align="center">

```text
[ model arena completed ]
[ feature engineering validated ]
[ clinical pipeline terminated successfully ]
```

</div>
