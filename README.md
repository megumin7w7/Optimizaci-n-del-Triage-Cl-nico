<div align="center">

# <span style="color:#7AA2F7;">⌬ Optimización del Triage Clínico</span>

<img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&size=26&pause=1000&color=7AA2F7&center=true&vCenter=true&width=900&lines=Machine+Learning+Aplicado+a+Salud;Feature+Engineering+Pipeline;Modelado+de+Riesgo+Clínico;Regresión+Logística+vs+XGBoost" />

<br>

![Python](https://img.shields.io/badge/Python-1A1B26?style=for-the-badge&logo=python&logoColor=7DCFFF)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-24283B?style=for-the-badge&logo=scikitlearn&logoColor=BB9AF7)
![XGBoost](https://img.shields.io/badge/XGBoost-1F2335?style=for-the-badge&logoColor=73DACA)
![Estado](https://img.shields.io/badge/Estado-Completado-24283B?style=for-the-badge&logoColor=F7768E)

</div>

---

<div align="center">

## <span style="color:#BB9AF7;">ACCESO RÁPIDO</span>

<a href="#-descripción"><kbd><span style="color:#7DCFFF;"> Descripción </span></kbd></a>

<a href="#-dataset"><kbd><span style="color:#73DACA;"> Dataset </span></kbd></a>

<a href="#-metodología"><kbd><span style="color:#BB9AF7;"> Metodología </span></kbd></a>

<a href="#-modelos"><kbd><span style="color:#F7768E;"> Modelos </span></kbd></a>

<a href="#-hallazgos"><kbd><span style="color:#9ECE6A;"> Hallazgos </span></kbd></a>

<a href="#-stack"><kbd><span style="color:#E0AF68;"> Tecnologías </span></kbd></a>

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
