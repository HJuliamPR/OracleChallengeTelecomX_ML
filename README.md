# OracleChallengeTelecomX_ML
Challenge 2 - Machine Learning

# 📊 Predicción de Cancelación (Churn) en Telecom X

## 🎯 Propósito del Análisis

Este proyecto tiene como objetivo principal desarrollar modelos predictivos capaces de identificar a los clientes de Telecom X con mayor probabilidad de **cancelar** sus servicios (Churn). Al prever el *churn*, la empresa puede implementar estrategias de retención dirigidas y proactivas, minimizando la pérdida de clientes y optimizando los recursos.

## 📂 Estructura del Proyecto

El proyecto está organizado de la siguiente manera:

-   **`ML_TelecomX.ipynb`**: Este cuaderno de Google Colab contiene todo el código Python, el análisis y los resultados del proyecto.
-   **`df_TelecomeX.csv`**: Archivo CSV que contiene los datos de los clientes de Telecom X utilizados para el análisis y modelado. (Este archivo se carga directamente desde una URL en el cuaderno).
-   **Visualizaciones**: Las visualizaciones generadas durante el análisis exploratorio y la evaluación del modelo están incrustadas directamente en el cuaderno.

## 🧹 Preparación de los Datos

El proceso de preparación de los datos incluyó las siguientes etapas clave:

1.  **Carga de Datos**: Los datos fueron cargados desde un archivo CSV.
2.  **Eliminación de Columnas Irrelevantes**: Se eliminó la columna `customerID` por ser un identificador único sin valor predictivo.
3.  **Clasificación y Codificación de Variables**:
    -   Se identificaron las variables **categóricas**.
    -   Se aplicó **One-Hot Encoding** a las variables categóricas para convertirlas a formato numérico, haciéndolas compatibles con los algoritmos de Machine Learning.
4.  **Balanceo de Clases**:
    -   Se identificó un **desbalance significativo** en la variable objetivo ('Churn').
    -   Se utilizó la técnica **SMOTE** (Synthetic Minority Over-sampling Technique) para sobremuestrear la clase minoritaria y balancear las clases.
5.  **Normalización (para modelos sensibles a la escala)**:
    -   Se aplicó **Normalización** (StandardScaler) a las características solo para el modelo KNN, ya que este algoritmo es sensible a la escala de los datos. Los modelos basados en árboles (como Random Forest) no requirieron este paso.
6.  **Separación de Datos**: El conjunto de datos balanceado fue dividido en conjuntos de **entrenamiento (80%)** y **prueba (20%)** para entrenar y evaluar los modelos de manera imparcial.

## 🤖 Modelado Predictivo

Se entrenaron dos modelos de clasificación para predecir el *churn*:

-   **KNN (K-Nearest Neighbors)**: Un modelo basado en distancia que requiere datos normalizados.
-   **Random Forest**: Un modelo basado en árboles que no es sensible a la escala de los datos.

## 📊 Evaluación y Comparación de Modelos

Ambos modelos fueron evaluados utilizando métricas clave para problemas de clasificación en el conjunto de prueba:

| Modelo          | Exactitud (Accuracy) | Precisión (Precision) | Recall (Recall) | F1-score |
| :-------------- | :------------------- | :-------------------- | :-------------- | :------- |
| **KNN**         | (Insertar valor)     | (Insertar valor)      | (Insertar valor)| (Insertar valor)|
| **Random Forest**| (Insertar valor)    | (Insertar valor)      | (Insertar valor)| (Insertar valor)|

*(Nota: Los valores exactos se pueden obtener de la ejecución del cuaderno)*

**Análisis Crítico:**

*(Aquí iría un resumen del análisis crítico de los modelos, destacando cuál tuvo mejor rendimiento y posibles indicios de overfitting/underfitting basados en la comparación de métricas de entrenamiento vs prueba, si se realizó)*

## 💡 Insights y Factores Clave del Churn

El análisis de correlación y la importancia de las variables en el modelo Random Forest revelaron los factores más influyentes en la cancelación de clientes:

-   **Tiempo de Contrato (`customer.tenure`)**: Los clientes con menor antigüedad son más propensos a cancelar.
-   **Tipo de Contrato (`account.Contract`)**: Los contratos mes a mes están fuertemente asociados con el *churn*.
-   **Gasto Total (`account.Charges.Total`) y Gasto Mensual (`account.Charges.Monthly`)**: Menor gasto total y mayor gasto mensual (en relación a la antigüedad) son indicadores de riesgo.
-   **Servicio de Internet y Soporte Técnico (`internet.InternetService`, `internet.TechSupport`)**: El servicio de fibra óptica y la falta de soporte técnico aumentan la probabilidad de cancelación.
-   **Método de Pago (`account.PaymentMethod_Electronic check`)**: Este método de pago mostró una correlación positiva con el *churn*.

*(Opcional: Incluir aquí miniaturas o descripciones de los gráficos más reveladores del EDA y análisis dirigido).*

## ▶️ Cómo Ejecutar el Cuaderno

Para ejecutar este cuaderno de Google Colab:

1.  Abre el cuaderno `ML_TelecomX.ipynb` en Google Colab.
2.  Asegúrate de tener instaladas las bibliotecas necesarias. Las principales son:
