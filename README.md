# ⚡ Energy Demand Forecasting: Econometrics vs. Machine Learning

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1UjFYGReMuQRNOdUY7dnZh-P0f12DGK-C?usp=sharing)

Este repositorio contiene la solución técnica para el **Data Challenge de EY**. El objetivo principal es predecir la demanda de energía horaria (en MW) de la red PJM East, comparando la eficacia de modelos econométricos clásicos (**ARIMA**) frente a algoritmos de Machine Learning (**XGBoost**).

## 📄 Descripción del Proyecto

El proyecto aborda un problema de series de tiempo univariante con fuerte estacionalidad múltiple. Se contrastan dos enfoques para determinar cuál ofrece mejor capacidad predictiva (menor RMSE) y valor para el negocio:

1.  **Enfoque Clásico (Econometría):** * Análisis exploratorio (Descomposición estacional, ACF/PACF).
    * Tests estadísticos (Dickey-Fuller, Ljung-Box, Jarque-Bera).
    * Modelado con **ARIMA** y **SARIMA** usando `statsmodels`.
2.  **Enfoque Moderno (Machine Learning):** * Ingeniería de características temporales (lags, variables de calendario como hora, día, mes).
    * Modelado supervisado con **XGBoost Regressor**.

## 📂 Dataset

Utilizamos el dataset **PJM Hourly Energy Consumption** (`PJME_hourly.csv`), que contiene datos reales de consumo eléctrico.

-   **Fuente:** Kaggle / PJM Interconnection LLC
-   **Rango:** 2002 - 2018
-   **Granularidad:** Horaria
-   **Variable Objetivo:** `PJME_MW` (Megavatios)

## 🛠️ Tecnologías

* **Python 3.x**
* **Manipulación de Datos:** Pandas, NumPy
* **Visualización:** Matplotlib, Seaborn
* **Econometría:** `statsmodels` (ARIMA, SARIMAX, ETS Decompose)
* **Machine Learning:** `xgboost`, `scikit-learn` (Metrics, Time Series Split)

## 🏆 Resultados del Modelado

Tras evaluar ambos enfoques utilizando una partición de prueba (Test Set) a partir de **2017**, se obtuvieron los siguientes resultados:

| Modelo | RMSE (MW) | Observación |
| :--- | :--- | :--- |
| **ARIMA (Baseline)** | 6,583.84 | Modelo rígido; sufre de reversión a la media al no capturar la estacionalidad diaria compleja. |
| **XGBoost (Propuesto)** | **3,889.32** | **Mejora del ~41%**. Captura eficazmente los "dobles picos" diarios y la variabilidad semanal/anual. |

> **Nota:** El ligero aumento en el RMSE respecto a validaciones previas se debe a la selección de un periodo de prueba más desafiante (2017-2018), lo que confirma la robustez del modelo ante datos nuevos.

## 🚀 Conclusión de Negocio

El enfoque de **Machine Learning (XGBoost)** demostró ser superior para la predicción operativa. La reducción del error en más de **2,600 MW** permite:
1.  **Optimizar la generación:** Evitar el encendido costoso de plantas de respaldo.
2.  **Reducir incertidumbre:** Mejorar la planificación de compra de energía en el mercado spot.

---
**Autor:** Luis Mauricio Aguirre Stornaiuolo  
*Estudiante de Economía (8vo Ciclo) - UNMSM*
