# ML1_ExamenAplicado_Araya_Juan

## Examen Machine Learning I

Este repositorio contiene el desarrollo del examen aplicado de **Machine Learning I**, utilizando el dataset **Seoul Bike Sharing Demand**.

## Dataset

- **Nombre:** Seoul Bike Sharing Demand
- **Fuente:** UCI Machine Learning Repository
- **URL:** https://archive.ics.uci.edu/dataset/560/seoul+bike+sharing+demand
- **Observaciones:** 8.760
- **Columnas:** 14
- **Variable objetivo:** Rented Bike Count
- **Tipo de tarea:** Regresión

El objetivo del análisis es predecir la cantidad de bicicletas arrendadas por hora a partir de variables meteorológicas, temporales y operacionales.

## Metodología

El análisis se desarrolló en las siguientes etapas:

1. Exploración inicial del dataset con pandas.
2. Revisión de valores faltantes.
3. Detección de outliers mediante el método IQR.
4. Análisis de la distribución de la variable objetivo.
5. Análisis de correlaciones y multicolinealidad.
6. División de los datos en entrenamiento y test con random_state=42.
7. Preprocesamiento mediante `ColumnTransformer`, incluyendo imputación, escalamiento y codificación de variables categóricas.
8. Reducción de dimensionalidad mediante PCA.
9. Clustering mediante K-Means.
10. Entrenamiento y optimización de Ridge Regression y Random Forest Regressor.
11. Comparación de desempeño mediante RMSE, MAE, R² y MAPE.
12. Análisis de importancia de variables y de las observaciones con mayor error.

## Análisis no supervisado

Mediante PCA se seleccionaron **6 componentes principales**, que explican aproximadamente **85,85% de la varianza acumulada**.

Posteriormente se evaluó K-Means para valores de K entre 2 y 10. El valor seleccionado fue:

- K óptimo: 6
- Silhouette Score: 0,3049

El perfil de clusters mostró diferencias relevantes principalmente en variables meteorológicas como lluvia, nieve y humedad.

## Resultados de los modelos

| Modelo | RMSE | MAE | R² | MAPE |
|---|---:|---:|---:|---:|
| Random Forest | 255,1746 | 146,7562 | 0,8437 | 32,0579% |
| Ridge | 440,8677 | 278,7079 | 0,5335 | 69,9315% |

El modelo con mejor desempeño fue Random Forest, ya que presentó menor error y un mayor coeficiente de determinación.

Entre las variables más relevantes se encontraron el estado de funcionamiento del sistema, la temperatura, la hora del día y la cantidad de lluvia.

## Reproducción del análisis

Para instalar las dependencias utilizadas:

```bash
pip install -r requirements.txt
```

Luego, ejecutar el notebook:

Examen_Seoul_Bike_Sharing.ipynb

## Estructura del repositorio

```text
ML1_ExamenAplicado_Araya_Juan/
├── figures/
├── Examen_Seoul_Bike_Sharing.ipynb
├── SeoulBikeData.csv
├── resultados_modelos.csv
├── README.md
└── requirements.txt
```

La carpeta figures/ contiene los gráficos generados durante el análisis.

## Video de presentación


## Uso de inteligencia artificial generativa

Se utilizó Claude como herramienta de apoyo para revisar la estructura del análisis, proponer código base, explicar conceptos de Machine Learning y apoyar la redacción de interpretaciones y conclusiones.

El código fue ejecutado y revisado por el estudiante, quien verificó los resultados obtenidos y mantiene la responsabilidad sobre el contenido final entregado.


**Juan Carlos Araya**  
Machine Learning I
