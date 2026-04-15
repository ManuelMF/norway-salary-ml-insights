# Análisis de Salarios en Noruega: Machine Learning y Reducción de Dimensiones

Este proyecto aplica técnicas de aprendizaje no supervisado y supervisado para segmentar perfiles laborales, detectar anomalías y predecir salarios.

## Objetivos
* **Segmentar** la población laboral mediante Clustering.
* **Detectar anomalías** estadísticas (outliers).
* **Comparar métodos de reducción de dimensionalidad** (PCA, IPCA, KPCA) aplicados a una regresión SVR.
* **Visualizar** datos complejos en entornos 2D y 3D interactivos.

---

## Flujo de Trabajo

### 1. Clustering y Anomalías
* **K-Means:** Uso de métricas de inercia y silueta para determinar el número óptimo de clústeres.
* **Regla 3-Sigma:** Identificación de anomalías calculando la distancia de cada punto al centroide de su clúster. Esto permite aislar perfiles con salarios o características fuera de la norma.

### 2. Reducción de Dimensionalidad para Regresión
Entrenamiento de un **Support Vector Regressor (SVR)** comparando tres enfoques de reducción para mantener el 90% de la varianza:
* **PCA Estándar:** Identificación de las variables con mayor impacto (pesos de las componentes).
* **Incremental PCA:** Procesamiento por lotes (10% de los datos) para optimizar memoria en grandes datasets.
* **Kernel PCA (RBF):** Captura de relaciones no lineales que el PCA tradicional no detecta.

### 3. Visualización de Datos
* **Proyección 2D:** Análisis de la varianza con el salario como variable de color (*hue*).
* **Visualización 3D Interactiva:** Implementación con **Plotly** para explorar la estructura del dataset y la distribución de los salarios más altos en tres ejes.

---

## Conclusiones Principales
* El modelo **SVR** mantiene un buen rendimiento incluso tras reducir drásticamente el número de variables.
* **Kernel PCA** revela patrones en los salarios más altos que sugieren una estructura no lineal en los datos.
* La **regla 3-sigma** sobre clústeres es más precisa para detectar anomalías que el análisis sobre el dataset completo, al tener en cuenta el contexto de cada grupo profesional.
