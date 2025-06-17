# 🫀 Detección de Fibrilación Auricular en ECGs mediante Análisis de Intervalos RR

Este proyecto tiene como objetivo detectar episodios de **fibrilación auricular (AFib)** a partir de señales de electrocardiograma (ECG), utilizando análisis estadístico de los **intervalos RR** (tiempo entre latidos) y aprendizaje automático. Se utiliza un enfoque de extracción de características simples, entrenamiento de modelos supervisados (Random Forest), y evaluación del rendimiento.

## 📁 Estructura del Proyecto

- `data/ecg_rr_features_curado.csv`: dataset con las características extraídas (mean_rr, std_rr, skew_rr, kurt_rr).
- `notebooks/proyecto.ipynb`: notebook principal con todo el flujo del análisis.

## 📊 Características Usadas

Se analizaron las siguientes métricas de variabilidad del ritmo cardiaco (HRV):

- `mean_rr`: promedio de los intervalos RR.
- `std_rr`: desviación estándar de los intervalos RR.
- `skew_rr`: asimetría de la distribución.
- `kurt_rr`: curtosis de la distribución.

Estas características permiten diferenciar entre ritmos cardíacos normales y aquellos asociados a fibrilación auricular.

## 🤖 Modelo Entrenado

- Algoritmo: **Random Forest**
- Validación: **train/test split (70/30)** con estratificación
- Métricas obtenidas:
  - **Accuracy:** 96.3%
  - **Precision (AFib):** 88%
  - **Recall (AFib):** 82%
  - **F1-Score (AFib):** 85%

Se obtuvo un desempeño general muy alto, aunque se destaca la necesidad de seguir reduciendo falsos negativos para mejorar la utilidad clínica.

## 📉 Limitaciones

- Solo se usaron características temporales (RR), sin considerar morfología de la señal.
- Algunos falsos negativos pueden representar un riesgo clínico serio.

## 📓 Notebook del proyecto

Puedes revisar todo el análisis, desde la carga de datos hasta el entrenamiento del modelo, en el siguiente notebook:

🔗 [Ver Notebook en GitHub](notebooks/proyecto.ipynb)

## ✅ Requisitos

- Python 3.8+
- scikit-learn
- numpy
- pandas
- matplotlib
- seaborn
- wfdb
