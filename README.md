<div align="center">

# <span style="color:#58A6FF;">⌬ Optimización del Triage Clínico</span>

<img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&size=28&pause=1000&color=58A6FF&center=true&vCenter=true&width=950&lines=Machine+Learning+Aplicado+a+Salud;Feature+Engineering+Pipeline;Modelado+de+Riesgo+Clínico;Regresión+Logística+vs+XGBoost" />

<br>

![Python](https://img.shields.io/badge/Python-0F172A?style=for-the-badge&logo=python&logoColor=38BDF8)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-111827?style=for-the-badge&logo=scikitlearn&logoColor=A855F7)
![XGBoost](https://img.shields.io/badge/XGBoost-0B1120?style=for-the-badge&logoColor=2DD4BF)
![Estado](https://img.shields.io/badge/Estado-Completado-111827?style=for-the-badge&logoColor=F43F5E)

</div>

---

<div align="center">

## <span style="color:#C084FC;">ACCESO RÁPIDO</span>

<a href="#-descripción">
<kbd style="background-color:#0F172A;">
<span style="color:#38BDF8;"> Descripción </span>
</kbd>
</a>

<a href="#-dataset">
<kbd style="background-color:#111827;">
<span style="color:#2DD4BF;"> Dataset </span>
</kbd>
</a>

<a href="#-metodología">
<kbd style="background-color:#1E293B;">
<span style="color:#A855F7;"> Metodología </span>
</kbd>
</a>

<a href="#-modelos">
<kbd style="background-color:#0B1120;">
<span style="color:#F43F5E;"> Modelos </span>
</kbd>
</a>

<a href="#-hallazgos">
<kbd style="background-color:#111827;">
<span style="color:#22C55E;"> Hallazgos </span>
</kbd>
</a>

<a href="#-stack">
<kbd style="background-color:#0F172A;">
<span style="color:#F59E0B;"> Tecnologías </span>
</kbd>
</a>

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
