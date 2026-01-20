# ⚡ Energy Demand Forecasting: Econometrics vs. Machine Learning

Este repositorio contiene el código y los recursos para el **Data Challenge de EY**. El objetivo principal es predecir la demanda de energía horaria (en MW) utilizando y comparando dos enfoques distintos: modelos clásicos de Series de Tiempo (**ARIMA**) y algoritmos de Machine Learning (**XGBoost**).

## 📄 Descripción del Proyecto

El proyecto busca resolver un problema de series de tiempo univariante utilizando datos históricos de consumo de energía. Se contrastan dos metodologías para determinar cuál ofrece mejor capacidad predictiva (RMSE) y explicabilidad:

1.  **Enfoque Econométrico:** Análisis de estacionariedad, descomposición estacional y modelado **ARIMA/SARIMA** con `statsmodels`.
2.  **Enfoque de Machine Learning:** Ingeniería de características temporales (lags, ventanas móviles, variables de calendario) y modelado supervisado con **XGBoost**.

## 📂 Dataset

El dataset utilizado es **PJM Hourly Energy Consumption** (`PJME_hourly.csv`), proveniente de la red de interconexión eléctrica regional PJM (EE.UU.).

- **Fuente:** Kaggle
- **Granularidad:** Horaria
- **Variable Objetivo:** `PJME_MW` (Consumo de energía en Megavatios)

## 🛠️ Tecnologías

- **Lenguaje:** Python 3.x
- **Análisis de Datos:** Pandas, NumPy
- **Visualización:** Matplotlib, Seaborn
- **Econometría:** Statsmodels (ARIMA, Seasonal Decompose, ADF Test)
- **Machine Learning:** XGBoost, Scikit-Learn (Time Series Split, Metrics)

