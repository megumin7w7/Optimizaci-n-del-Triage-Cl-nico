<div align="center">

# ⌬ Optimización del Triage Clínico

<img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&size=26&pause=1000&color=00D9FF&center=true&vCenter=true&width=850&lines=Machine+Learning+Aplicado+a+Salud;Feature+Engineering+Pipeline;Modelado+de+Riesgo+Clínico;Regresión+Logística+vs+XGBoost" />

<br>

![Python](https://img.shields.io/badge/Python-0D1117?style=for-the-badge&logo=python&logoColor=00D9FF)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-111827?style=for-the-badge&logo=scikitlearn&logoColor=7C3AED)
![XGBoost](https://img.shields.io/badge/XGBoost-0F172A?style=for-the-badge&logoColor=22D3EE)
![Estado](https://img.shields.io/badge/Estado-Completado-111827?style=for-the-badge&logoColor=00FFFF)

</div>

---

<div align="center">

## ACCESO RÁPIDO

<a href="#-descripción"><kbd> Descripción </kbd></a>
<a href="#-dataset"><kbd> Dataset </kbd></a>
<a href="#-metodología"><kbd> Metodología </kbd></a>
<a href="#-modelos"><kbd> Modelos </kbd></a>
<a href="#-hallazgos"><kbd> Hallazgos </kbd></a>
<a href="#-stack"><kbd> Tecnologías </kbd></a>

</div>

---

# ~/descripción

Pipeline de Machine Learning enfocado en la detección temprana de diabetes utilizando técnicas de Feature Engineering y modelos de clasificación supervisada.

El proyecto evalúa si variables clínicas derivadas pueden competir contra modelos complejos de ensamblaje manteniendo interpretabilidad y estabilidad.

## Objetivos principales

- Diseñar variables derivadas con lógica clínica
- Comparar modelos interpretables y modelos ensemble
- Analizar el impacto del Feature Engineering sobre los Odds Ratios
- Evaluar interpretabilidad vs complejidad predictiva

---

# ~/dataset

<div align="center">
<img src="https://cdn-icons-png.flaticon.com/512/2966/2966486.png" width="110"/>
</div>

| Propiedad | Valor |
|---|---|
| Dataset | Pima Indians Diabetes Database |
| Fuente | UCI / Kaggle |
| Problema | Clasificación Binaria |
| Variable Objetivo | `Outcome` |

---

## Variables Generadas

```bash
> Ratio_Insulina_Glucosa
> Ratio_IMC_Edad
> IMC_Categoria
> Presion_Sanguinea_div_Glucosa
> Ratio_Presion_IMC
```

Estas variables fueron creadas para capturar relaciones fisiológicas ocultas y mejorar la representación predictiva del modelo.

---

# ~/metodología

## preprocessing

```yaml
valores_invalidos: imputados
outliers: tratados
escalado: StandardScaler
datos_faltantes: manejados
```

---

## feature_engineering

```yaml
ratios_clinicos: habilitado
variables_interaccion: habilitado
binning: habilitado
patrones_no_lineales: capturados
```

---

## selección_de_variables

```yaml
métodos:
  - ANOVA F-Test
  - Lasso (L1)
  - Random Forest Importance
```

---

## validación

```yaml
métricas:
  - ROC-AUC
  - F1-Score
  - Accuracy

bootstrap_iterations: 1000
confidence_interval: 95%
```

---

# ~/modelos

| Modelo | Objetivo |
|---|---|
| Regresión Logística | Interpretabilidad Clínica |
| Random Forest | Importancia de Variables |
| XGBoost | Optimización Predictiva |
| SVM | Optimización de Márgenes |
| KNN | Similitud Local |
| AdaBoost | Benchmark Ensemble |

---

# ~/hallazgos

```yaml
predictor_dominante: Glucosa
feature_engineering: efectivo
mejor_modelo_interpretable: Regresión Logística
mejor_modelo_predictivo: XGBoost
estabilidad_modelo: alta
validación_bootstrap: completada
```

## Conclusiones Principales

- `Glucosa` se mantuvo como el predictor dominante en todos los experimentos.
- El Feature Engineering mejoró relaciones asociadas al IMC y presión sanguínea.
- La Regresión Logística logró competir contra modelos complejos manteniendo interpretabilidad.
- Algunas variables derivadas aportaron más estabilidad que mejora predictiva bruta.
- Mayor complejidad no siempre justificó la pérdida de interpretabilidad.

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
