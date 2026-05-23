<div align="center">

```
  ██████╗██╗     ██╗███╗   ██╗██╗ ██████╗ █████╗ ██╗
 ██╔════╝██║     ██║████╗  ██║██║██╔════╝██╔══██╗██║
 ██║     ██║     ██║██╔██╗ ██║██║██║     ███████║██║
 ██║     ██║     ██║██║╚██╗██║██║██║     ██╔══██║██║
      ╚██████╗███████╗██║██║ ╚████║██║╚██████╗██║  ██║███████╗
       ╚═════╝╚══════╝╚═╝╚═╝  ╚═══╝╚═╝ ╚═════╝╚═╝  ╚═╝╚══════╝
```

# `clinical-triage-optimization`

**Optimización del Triaje Clínico mediante Ingeniería de Variables y Comparación de Modelos de Ensamblaje**

[![Python](https://img.shields.io/badge/Python-3.10+-cba6f7?style=flat-square&logo=python&logoColor=0d0e11)](https://python.org)
[![Colab](https://img.shields.io/badge/Google_Colab-notebook-89b4fa?style=flat-square&logo=googlecolab&logoColor=0d0e11)](https://colab.research.google.com/drive/1S-u4TlzLr0ynqacQEUs4iH_cyEAebgSU)
[![Dataset](https://img.shields.io/badge/Dataset-Pima_Indians_Diabetes-a6e3a1?style=flat-square&logo=kaggle&logoColor=0d0e11)](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)
[![License](https://img.shields.io/badge/License-MIT-f38ba8?style=flat-square)](LICENSE)

</div>

---

## `~/problema`

Las alertas de diagnóstico médico generan un alto volumen de falsos positivos cuando los modelos trabajan con variables fisiológicas de forma aislada. Este proyecto evalúa si la **ingeniería de características con lógica clínica** puede mejorar la capacidad discriminativa sin necesidad de modelos algorítmicamente más complejos.

**Hipótesis central:** un feature engineerig bien diseñado sobre datos crudos supera a un modelo de ensamblaje entrenado sobre los mismos datos sin transformar.

---

## `~/pipeline`

```
DATOS CRUDOS  ──►  LIMPIEZA  ──►  FEATURE ENGINEERING  ──►  SELECCIÓN  ──►  MODELADO  ──►  EVALUACIÓN
     │                                      │                     │               │
  Pima DB                          ratios clínicos           Boruta          10 modelos
  768 registros                    categorías BMI          SelectKBest     CV 95% IC
  8 variables                      transformaciones          ANOVA-F       odds ratios
```

### Módulos del notebook

| bloque | función |
|--------|---------|
| `01` · Instalación e imports | Stack completo: sklearn · feature-engine · imblearn · boruta · xgboost · lightgbm |
| `02` · Carga | `kagglehub` → Pima Indians Diabetes · renombrado en español |
| `03` · Análisis estructural | Estadísticas extendidas con IQR · detección de ceros fisiológicos |
| `04` · EDA | Distribuciones · correlaciones · análisis de desbalance · entropía |
| `05` · Feature Engineering | Ratios clínicos · discretización · transformación Yeo-Johnson |
| `06` · Selección de variables | Boruta · SelectKBest (ANOVA-F) · SmartCorrelatedSelection |
| `07` · Balanceo de clases | SMOTE · SMOTETomek · ADASYN · comparativa de estrategias |
| `08` · Modelado y comparación | 10 modelos · GridSearchCV · StratifiedKFold · IC al 95% |
| `09` · Odds Ratios | Comparativa Raw vs Feature Engineering · impacto por variable |
| `10` · Conclusiones | Análisis clínico de resultados · variables clave identificadas |

---

## `~/feature-engineering`

Las variables originales se transforman en representaciones con semántica clínica directa:

```python
# Ratios construidos
Ratio_Glucosa_Insulina     = Glucosa / (Insulina + 1)
Presion_div_Glucosa        = Presion_Sanguinea / Glucosa
Presion_div_Edad           = Presion_Sanguinea / Edad
Ratio_Presion_IMC          = Presion_Sanguinea / IMC

# Discretización clínica
IMC_Categoria              = {bajo_peso, normal, sobrepeso, obesidad}
Edad_Categoria             = {joven, adulto, mayor}

# Transformación de distribución
Yeo-Johnson(Insulina, Funcion_Pedigree)
```

> **Hallazgo principal:** `Glucosa` mantiene el OR más alto (3.67) antes y después del FE. Las variables creadas como `Presion_div_Glucosa` (OR 1.31) capturaron relaciones fisiológicas no visibles en los datos crudos. Las versiones categorizadas de IMC y Edad perdieron información — el FE numérico superó al categórico en todos los casos evaluados.

---

## `~/modelos`

```
Regresión Logística          Random Forest             Gradient Boosting
AdaBoost                     XGBoost                   LightGBM
SVM (RBF kernel)             K-Nearest Neighbors       Naive Bayes
Decision Tree
```

**Protocolo de evaluación:** StratifiedKFold · 5 folds · IC 95% bootstrap · métricas: `AUC-ROC · F1 · Recall · Precision · Accuracy`

---

## `~/resultados`

El modelo ganador es **Regresión Logística + ANOVA-F SelectKBest** entrenado sobre el dataset con feature engineering, superando al Random Forest equivalente en AUC-ROC bajo las mismas condiciones de validación cruzada.

```
Variable          OR (Raw)    OR (FE)     Delta
─────────────────────────────────────────────────
Glucosa             3.52        3.67       +0.15   ← señal dominante
Embarazos           1.38        1.44       +0.06
Presion/Glucosa      —          1.31       nuevo
IMC                 1.29        1.22       -0.07
Presion/Edad         —          0.89       nuevo
Ratio_Presion_IMC    —          0.64       nuevo
IMC_Categoria       1.15        0.99       -0.16   ← categorizar perdió info
```

---

## `~/stack`

```toml
[core]
python        = "3.10+"
pandas        = "*"
numpy         = "*"
scikit-learn  = "*"
matplotlib    = "*"
seaborn       = "*"

[feature-engineering]
feature-engine = "*"   # MathFeatures · RelativeFeatures · YeoJohnson · SmartCorrelatedSelection
boruta         = "*"   # selección de variables no lineal

[modeling]
xgboost      = "*"
lightgbm     = "*"
imbalanced-learn = "*"  # SMOTE · SMOTETomek · ADASYN

[data]
kagglehub    = "*"   # descarga directa del dataset
```

---

## `~/uso`

```bash
# Clonar
git clone https://github.com/<tu-usuario>/clinical-triage-optimization.git
cd clinical-triage-optimization
```

```python
# En Colab: el notebook descarga el dataset automáticamente vía kagglehub
import kagglehub
path = kagglehub.dataset_download("uciml/pima-indians-diabetes-database")
```

El notebook está diseñado para ejecutarse secuencialmente en Google Colab. Cada bloque es independiente excepto los de modelado, que requieren el DataFrame procesado del bloque de FE.

---

## `~/dataset`

**Pima Indians Diabetes Database** · UCI Machine Learning Repository

| campo | detalle |
|-------|---------|
| registros | 768 pacientes |
| variables | 8 fisiológicas + 1 objetivo |
| clases | 0 = no diabético · 1 = diabético |
| desbalance | ~65% / 35% |
| fuente | [kaggle.com/uciml/pima-indians-diabetes-database](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database) |

---

## `~/conclusiones`

La ingeniería de características con criterio clínico demuestra ser más efectiva que la complejidad algorítmica por sí sola. Las variables derivadas de ratios entre presión, glucosa y edad capturaron interacciones fisiológicas relevantes que los modelos de ensamblaje no lograban con los datos crudos. La discretización de variables continuas probó ser contraproducente en este contexto — la información clínica se preserva mejor en formato numérico.

---

<div align="center">

```
made with  ·  python + colab  ·  tecsup 2026
```

</div>
