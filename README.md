# Modelos-de-aprendizaje
# Proyecto de Modelado de Enfermedad Cardíaca

Este proyecto tiene como objetivo desarrollar y comparar modelos de aprendizaje automático para predecir la presencia de enfermedad cardíaca basándose en un conjunto de datos de pacientes.

## Tabla de Contenidos

1.  [Propósito](#propósito)
2.  [Dependencias](#dependencias)
3.  [Descripción del Código](#descripción-del-código)
    * [Importar Datos](#importar-datos)
    * [Análisis Exploratorio de Datos (EDA)](#análisis-exploratorio-de-datos-eda)
    * [Limpieza de Datos](#limpieza-de-datos)
    * [Preprocesamiento](#preprocesamiento)
    * [Modelado](#modelado)
        * [Árbol de Decisión](#árbol-de-decisión)
        * [KNN](#knn)
        * [Regresión Logística](#regresión-logística)
    * [Comparación de Modelos](#comparación-de-modelos)
4.  [Resultados](#resultados)
5.  [Conclusión](#conclusión)

## Propósito

El objetivo principal de este proyecto es construir y comparar diferentes modelos de clasificación (Árbol de Decisión, K-Nearest Neighbors - KNN, y Regresión Logística) para predecir si un paciente tiene o no enfermedad cardíaca, utilizando un conjunto de características clínicas.

## Dependencias

Para ejecutar este proyecto, se requieren las librerías de Python `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn` (`sklearn`), `scipy`, y `imblearn` (si se implementan técnicas de manejo de desbalance). Estas librerías se utilizan para la manipulación de datos, visualización, aprendizaje automático y operaciones científicas.

## Descripción del Código

### Importar Datos

Se cargó el conjunto de datos de enfermedad cardíaca desde un archivo CSV utilizando la librería `pandas` en un DataFrame para su posterior análisis.

### Análisis Exploratorio de Datos (EDA)

Se realizó un análisis exploratorio para comprender las características del conjunto de datos, incluyendo la descripción de las variables, la visualización de la distribución de la variable objetivo y la exploración visual de las distribuciones de las características numéricas y categóricas en relación con la presencia o ausencia de enfermedad cardíaca.

### Limpieza de Datos

Se aplicaron pasos de limpieza para manejar valores atípicos o erróneos en el conjunto de datos, asegurando la calidad de los datos para el modelado.

### Preprocesamiento

Se prepararon los datos para el modelado a través de varias etapas:

* **Manejo de Outliers:** Se identificaron y potencialmente se trataron los valores atípicos en las características continuas.
* **División de Datos:** El conjunto de datos se dividió en conjuntos de entrenamiento y prueba para evaluar el rendimiento de los modelos en datos no vistos.
* **Transformación de Características:** Se aplicó la transformación Box-Cox a las características continuas para reducir el sesgo, seguido del escalado utilizando `StandardScaler`. Las características categóricas se codificaron utilizando One-Hot Encoding.
* **Pipeline de Preprocesamiento:** Se utilizó `ColumnTransformer` para aplicar las transformaciones adecuadas a los diferentes tipos de columnas.

### Modelado

Se implementaron y ajustaron tres modelos de clasificación:

* **Árbol de Decisión:** Se realizó una búsqueda de hiperparámetros para encontrar la mejor configuración del modelo utilizando validación cruzada.
* **KNN:** Se ajustaron los hiperparámetros del modelo KNN, como el número de vecinos y la métrica de distancia, utilizando `GridSearchCV`.
* **Regresión Logística:** Se realizó una búsqueda exhaustiva de hiperparámetros para el modelo de Regresión Logística, incluyendo diferentes valores de regularización y solvers, utilizando validación cruzada estratificada.

### Comparación de Modelos

Se comparó el rendimiento de los tres modelos en el conjunto de prueba utilizando la curva AUC-ROC y el valor del AUC (Area Under the Curve) para evaluar su capacidad de discriminación.

## Resultados

Los resultados de la evaluación de los modelos en el conjunto de prueba mostraron que el **KNN** obtuvo el mejor rendimiento con un AUC-ROC de 0.8544. El Árbol de Decisión logró un AUC-ROC de 0.7740, mientras que la Regresión Logística tuvo un rendimiento inferior con un AUC-ROC de 0.6563.

## Conclusión

El modelo de K-Nearest Neighbors (KNN) demostró ser el más efectivo para predecir la presencia de enfermedad cardíaca en este conjunto de datos, superando al Árbol de Decisión y a la Regresión Logística en términos de capacidad de clasificación general.
