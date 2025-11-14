# Prediccion-Precios-Acciones-NVDA-ARIMA
---
# Predicción de Precios de Acciones de NVIDIA (NVDA) usando ARIMA
---

Este proyecto realiza un **análisis de series de tiempo** del precio de las acciones de **NVIDIA (NVDA)** durante un período de **siete años** (2018-2025) utilizando la metodología **ARIMA** (AutoRegressive Integrated Moving Average). El objetivo principal es modelar la volatilidad y la tendencia de los datos logarítmicos del precio de cierre para generar predicciones confiables a **12 meses** con sus respectivos intervalos de confianza. Se demuestra el proceso de aseguramiento de la **estacionariedad** mediante diferenciación y la selección del modelo óptimo, resultando en el modelo final **ARIMA(1,1,0)**.

## Contenido

Este repositorio contiene un Jupyter Notebook (`Código Nvda.ipynb`) que implementa un pipeline completo de análisis de series temporales para predecir los precios de las acciones de NVIDIA (NVDA). El enfoque se centra en datos históricos desde noviembre de 2018 hasta noviembre de 2025, utilizando técnicas de modelado estadístico para generar pronósticos mensuales futuros.

El notebook incluye:
- Descarga de datos en tiempo real usando API financiera.
- Análisis exploratorio de datos (EDA), pruebas de estacionariedad y descomposición de series.
- Selección automática y ajuste de modelo ARIMA.
- Generación de predicciones con intervalos de confianza.
- Visualizaciones gráficas y tablas de resultados.
- Métricas de rendimiento como RMSE y MAPE.
- Exportación de predicciones a CSV para uso posterior.

## Flujo de Trabajo

1. **Preparación de Datos**:
   - Importación de librerías esenciales (yfinance, pandas, numpy, matplotlib, seaborn, statsmodels, pmdarima, sklearn).
   - Configuración para suprimir warnings y mejorar visualizaciones.
   - Descarga de datos históricos de NVDA desde 7 años atrás hasta el día anterior a la ejecución.

2. **Análisis Exploratorio**:
   - Visualización de la serie temporal.
   - Prueba de estacionariedad (ADF Test).
   - Descomposición estacional (tendencia, estacionalidad, residuales).
   - Transformación logarítmica para estabilizar la varianza.
   - Diferenciación para lograr estacionariedad.

3. **Modelado**:
   - Uso de `auto_arima` para seleccionar el mejor modelo ARIMA basado en AIC.
   - Ajuste del modelo ARIMA(1,1,0).
   - División de datos en entrenamiento (80%) y prueba (20%).

4. **Predicción y Evaluación**:
   - Generación de pronósticos para el conjunto de prueba y 12 meses futuros.
   - Cálculo de intervalos de confianza al 95%.
   - Evaluación con métricas: RMSE y MAPE.
   - Visualización combinada de datos históricos, predicciones y bandas de confianza.

5. **Resultados**:
   - Tabla de predicciones mensuales exportada a CSV.
   - Resumen de métricas y perspectivas.

## Herramientas

- **Entorno de Desarrollo**: Jupyter Notebook para un análisis interactivo y reproducible.
- **Librerías Principales**:
  - `yfinance`: Para descargar datos financieros en tiempo real.
  - `pandas` y `numpy`: Manipulación y cálculos numéricos.
  - `matplotlib` y `seaborn`: Visualizaciones gráficas.
  - `statsmodels`: Pruebas estadísticas (ADF, descomposición) y modelado ARIMA.
  - `pmdarima`: Selección automática de hiperparámetros ARIMA.
  - `sklearn`: Métricas de error (MSE, MAPE).
- **Otras Dependencias**: `datetime`, `warnings` para manejo de fechas y supresión de alertas.

## Características Técnicas Destacadas

- **Selección Automática de Modelo**: Uso de `auto_arima` con criterios como AIC para optimizar parámetros (p, d, q), considerando estacionalidad y pruebas de estacionariedad.
- **Transformaciones de Datos**: Aplicación de logaritmo y diferenciación para manejar no-estacionariedad y heteroscedasticidad en series financieras.
- **Pronósticos con Incertidumbre**: Inclusión de intervalos de confianza al 95% para cuantificar la incertidumbre en las predicciones futuras.
- **Evaluación Robusta**: Métricas como RMSE (63.1388) y MAPE (45.57%) para validar el rendimiento, reconociendo la volatilidad inherente en mercados financieros.
- **Visualización Integrada**: Gráficos combinados de entrenamiento, prueba y predicciones futuras con bandas de confianza para una interpretación intuitiva.
- **Reproducibilidad**: Código modular con comentarios en español, fechas dinámicas basadas en `datetime.now()` y exportación de resultados a CSV.

## Tecnologías Utilizadas

- **Lenguaje**: Python 3.11+.
- **Bibliotecas Clave**: yfinance, pandas, numpy, matplotlib, seaborn, statsmodels, pmdarima, scikit-learn.
- **Entorno**: Jupyter Notebook (compatible con Google Colab o entornos locales como Anaconda).
- **Datos**: API de Yahoo Finance (yfinance) para datos en tiempo real.

## Conclusión

El modelo ARIMA(1,1,0) proporciona predicciones estadísticamente significativas para los precios de NVDA, proyectando un valor promedio de ~198.27 USD en los próximos 12 meses, con un intervalo de confianza amplio (160.72 USD - 244.59 USD) que refleja la volatilidad del mercado. Aunque el MAPE alto (45.57%) indica limitaciones en precisión absoluta, el enfoque es útil para análisis de tendencias. Este proyecto sirve como base para extensiones como integración de machine learning (e.g., LSTM) o factores externos (e.g., noticias financieras). Recomendación: No usar para decisiones de inversión sin validación adicional.

## Autor

- **Nombre**: Karina Serrano
- **Contacto**: https://www.linkedin.com/in/karina-serrano-data-science/
- **Fecha**: Noviembre 2025 
