# 🛍️ Segmentación de Clientes - Clustering No Supervisado (Analisis de Datos)

Este proyecto tiene como objetivo aplicar técnicas de aprendizaje no supervisado para segmentar clientes de un centro comercial, utilizando los algoritmos K-means y clustering jerárquico. El análisis se basa en el dataset **Mall Customer Segmentation** dado para estudio del caso.

---

## 📁 Estructura del Proyecto

- `Mall_Customers.csv`: Dataset utilizado.
- `mall_segmentation.ipynb`: Notebook principal con el desarrollo del análisis.
- `README.md`: Documento de referencia del proyecto.

---

## 🎯 Objetivos

- Comprender la estructura y características de los clientes mediante análisis exploratorio de datos.
- Preprocesar y escalar los datos para su uso en modelos de clustering.
- Identificar segmentos homogéneos de clientes utilizando K-means y clustering jerárquico.
- Evaluar y comparar la calidad de ambos modelos con métricas adecuadas.
- Visualizar los clústeres y analizar los resultados para posibles aplicaciones en marketing.

---

## 🧪 Tecnologías y herramientas

- **Lenguaje:** Python 3.x
- **Entorno de desarrollo:** Jupyter Notebook (Anaconda)
- **Librerías:**  
  - `pandas`, `numpy`: procesamiento y análisis de datos  
  - `matplotlib`, `seaborn`: visualización  
  - `sklearn`: algoritmos de clustering y métricas  
  - `scipy`: clustering jerárquico  
  - `PCA`: reducción de dimensionalidad para visualización

---

## 📊 Proceso de análisis

### 1. **EDA (Análisis Exploratorio de Datos):** histogramas, boxplots, correlaciones.

- Se identificaron 5 variables: `CustomerID`, `Gender`, `Age`, `Annual Income (k$)`, `Spending Score (1-100)`.
- Se verificó que no existían valores nulos ni duplicados.
- Se exploraron gráficamente distribuciones, relaciones entre variables y valores atípicos mediante gráficos de dispersión (`pairplot`) y diagramas de caja (`boxplot`).

### 2. **Preprocesamiento:** codificación de variables categóricas, escalado, eliminación de baja varianza.

- Se eliminó la variable `CustomerID` al no aportar información útil al modelo.
- Se convirtió la variable categórica `Gender` a formato numérico binario (`Male` → 0, `Female` → 1).
- Se normalizaron las variables numéricas mediante `StandardScaler`.
  
### 3. **Modelado con K-means:**

- Se utilizó el método del codo para determinar el valor óptimo de *k = 5*.
- Se entrenó el modelo sobre las variables `Annual Income (k$)` y `Spending Score (1-100)`.

### 4. **Modelado con clustering jerárquico:**

- Se construyó un dendrograma con `linkage(method='ward')`.
- Se seleccionaron también 5 clusters para fines comparativos.
  
### 5. **Evaluación de modelos:** uso de coeficiente de Silhouette e índice de Calinski-Harabasz.

- Se calcularon métricas de validación como el **coeficiente de Silhouette** y el **índice de Calinski-Harabasz**.
- Se visualizaron los clusters en dos dimensiones para evaluar su coherencia.

---

## 📌 Conclusiones

- Ambos algoritmos son eficaces para segmentar clientes en función de su comportamiento de consumo.
- **K-Means** fue más claro en la visualización y segmentación directa.
- El **clustering jerárquico** permitió analizar las relaciones jerárquicas entre los clientes sin necesidad de definir previamente el número de clusters.
- Estos hallazgos permiten desarrollar campañas de marketing más focalizadas, mejorar la atención al cliente y optimizar la distribución de productos en un centro comercial.
