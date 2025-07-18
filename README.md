# Predicción de Churn de Clientes 📡 | Desafío Telecom X Parte 2

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.0+-green?style=for-the-badge&logo=pandas)
![Scikit-learn](https://img.shields.io/badge/Scikit--Learn-1.3+-orange?style=for-the-badge&logo=scikit-learn)
![Google Colab](https://img.shields.io/badge/Google_Colab-Ready-yellow?style=for-the-badge&logo=google-colab)
![Status](https://img.shields.io/badge/status-completado-success?style=for-the-badge)

### 👨‍💻 **Desarrollado por: Carlos Victorio**

---

### 🎯 Resumen del Proyecto

Este repositorio contiene la solución completa al **Desafío Telecom X Parte 2**. El objetivo fue construir un pipeline de Machine Learning para predecir la cancelación de clientes (churn) en una empresa de telecomunicaciones. El proyecto va desde el preprocesamiento avanzado de los datos hasta la creación, evaluación e interpretación de modelos predictivos, culminando en recomendaciones de negocio accionables.

---

### 💡 Resultados Clave y Conclusiones Estratégicas

Tras un análisis exhaustivo, se llegó a las siguientes conclusiones, listas para impactar en la estrategia de negocio:

*   🏆 **Modelo Ganador:** Se eligió la **Regresión Logística** por su excelente balance entre rendimiento y robustez. Alcanzó un **Recall del 64%** para la clase "Churn", siendo más efectivo que otros modelos para identificar a los clientes en riesgo real, y sin sufrir de sobreajuste.

*   🔍 **Factores Críticos que Impulsan el Churn:**
    1.  **Contratos a Corto Plazo (`Month-to-month`):** El principal factor de riesgo.
    2.  **Servicio de Fibra Óptica:** Sorprendentemente, los clientes con este servicio premium son más propensos a cancelar.
    3.  **Baja Antigüedad (`tenure`):** Los clientes nuevos son los más volátiles.

*   🚀 **Recomendaciones Estratégicas Accionables:**
    1.  **Migrar Clientes:** Crear campañas agresivas para mover a los clientes del plan `Month-to-month` a contratos de 1 o 2 años.
    2.  **Auditar Servicios:** Investigar urgentemente por qué el servicio de Fibra Óptica y el pago con Cheque Electrónico están asociados a un alto churn.
    3.  **Implementar Lealtad:** Crear un programa que recompense a los clientes por su antigüedad (`tenure`).
    4.  **Operacionalizar el Modelo:** Usar el modelo para generar listas de clientes en riesgo y que el equipo de retención actúe de forma proactiva.

---

### ⚙️ El Pipeline de Machine Learning

El proyecto siguió un pipeline riguroso para garantizar la calidad y fiabilidad de los resultados:

1.  **Extracción de Datos:** Carga de los datos tratados desde un archivo JSON.
2.  **Preprocesamiento y Limpieza:**
    *   **Aplanamiento de Datos:** Normalización de columnas JSON anidadas (`customer`, `account`, etc.) a un formato tabular.
    *   **Encoding:** Conversión de todas las variables categóricas a formato numérico usando One-Hot Encoding (`get_dummies`).
    *   **Tratamiento de Nulos:** Imputación de valores faltantes en `Charges.Total` usando la mediana.
3.  **Análisis de Desbalance y Balanceo:**
    *   Se identificó un desbalance de clases (74% No Churn vs. 26% Churn).
    *   Se aplicó la técnica **SMOTE (Synthetic Minority Over-sampling Technique)** sobre el set de entrenamiento para crear un conjunto de datos perfectamente balanceado (50/50).
4.  **Estandarización de Datos:**
    *   Se utilizó `StandardScaler` en los datos de entrenamiento y prueba para normalizar la escala de las características, un paso crucial para modelos como la Regresión Logística.
5.  **Modelado y Evaluación:**
    *   Se entrenaron dos modelos: **Regresión Logística** y **Random Forest**.
    *   Se evaluaron usando métricas clave: *Accuracy, Precision, Recall, F1-Score* y la *Matriz de Confusión*.
6.  **Interpretación y Selección:**
    *   El modelo de **Regresión Logística** fue seleccionado por su mayor *Recall* en la clase positiva y su inmunidad al *overfitting* que afectó al Random Forest.
    *   Se analizaron los coeficientes del modelo para identificar las variables más influyentes.

---

### 🛠️ Tecnologías Utilizadas

*   **Lenguaje:** Python 3.x
*   **Librerías Principales:**
    *   `Pandas`: Para manipulación y análisis de datos.
    *   `Scikit-learn`: Para el preprocesamiento, modelado y evaluación.
    *   `Imbalanced-learn`: Para el balanceo de clases con SMOTE.
    *   `Matplotlib` & `Seaborn`: Para visualización de datos.
*   **Entorno de Desarrollo:** Google Colab.

---

### ▶️ Cómo Ejecutar el Proyecto

El proyecto está contenido en un único notebook, diseñado para ser ejecutado de forma sencilla:

1.  **Clona este repositorio (opcional):**
    ```bash
    git clone https://github.com/thecat065/telecom-x-parte-2.git
    ```
2.  **Abre el Notebook:** Carga el archivo `.ipynb` en [Google Colab](https://colab.research.google.com/).
3.  **Ejecuta las Celdas:** Simplemente ejecuta todas las celdas en orden de arriba hacia abajo. Todas las dependencias y la carga de datos están manejadas dentro del propio notebook.

---

### ✨ Créditos y Agradecimientos

Este proyecto fue desarrollado y liderado en su totalidad por **Carlos Victorio**. Su visión analítica y su habilidad para traducir los resultados en estrategias de negocio fueron la clave del éxito de este desafío.

El proyecto contó con la asistencia de una IA de Google para la generación de código y la estructuración de informes, siempre bajo la dirección y validación de Carlos.

---

### 📄 Licencia

Este proyecto se distribuye bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles.
