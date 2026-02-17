Sleep Cycle EDA + Modelado (Ridge + Intervalos Conformales)

Este proyecto analiza un dataset personal de sueño (exportado desde una app tipo Sleep Cycle) y construye un modelo predictivo para estimar los minutos de sueño de la próxima noche, incluyendo un intervalo de incertidumbre (90%) basado en Conformal Prediction.

Objetivos del proyecto

Limpieza y preparación del dataset:
- Conversión de fechas y porcentajes
- Corrección de valores inválidos (placeholder 1969)
- Creación de métricas consistentes (tiempo en cama, tiempo dormido, eficiencia, latencia)
- Detección y manejo de outliers

EDA (Exploratory Data Analysis):
- Distribuciones de variables clave
- Relaciones entre métricas (ej. Sleep Quality vs minutos dormidos)
- Tendencias temporales con medias móviles
- Análisis por bins (Regularity y Sleep Quality) y heatmaps

Modelado:
- Target: time_asleep_min (minutos dormidos)
- Features: historial (lag1 y rolling 7 días) + calendario (weekday, month)
- Comparación contra baselines (última noche y media móvil 7 días)
- Modelo final: Ridge Regression (alpha=100)

Predicción con incertidumbre:
- Intervalos 90% con Rolling Conformal Prediction
- Función final para predecir la próxima noche (predicción + intervalo)