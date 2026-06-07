# Churn Hunters - Solución de Analítica Avanzada para Arca Continental 🚀
Repositorio original del equipo "Las Tortugas Hackatecas".

Integrantes: Jannette Flores, Bianca Cordero, Sofía Sacoto y Dulce Sánchez

## 📋 Descripción del Proyecto
Este repositorio contiene la solución desarrollada para identificar proactivamente las tienditas del canal tradicional en riesgo de Churn (dejar de comprar por un mes), permitiendo mitigar una pérdida estimada de 12 MM MXN mensuales.

## 🛠️ Enfoque Técnico y Justificación
* **Enfoque elegido:** Se desarrolló un modelo de *Machine Learning basado en LightGBM (Light Gradient Boosting Machine)* para la predicción de churn de clientes. LightGBM fue seleccionado por su capacidad para manejar grandes volúmenes de datos, capturar relaciones no lineales entre variables y ofrecer un alto desempeño en problemas de clasificación desbalanceados. Adicionalmente, se implementó ingeniería de características basada en ventanas móviles de 4 meses, Target Encoding para variables categóricas y técnicas de ajuste de umbral enfocadas en maximizar la detección temprana de clientes en riesgo.

* **Métricas logradas en Test Set:**
  * *ROC-AUC:* 0.96
  * *Recall:* 89.21%
  * *F1-Score:* 14.19%.
Dado que el objetivo del negocio es minimizar la pérdida de clientes, se priorizó un alto *Recall*, logrando identificar aproximadamente 9 de cada 10 clientes que efectivamente abandonan la compañía. Esto permite implementar estrategias preventivas de retención antes de que ocurra la pérdida del cliente.

## 📊 Sistema de Scoring de Riesgo
Nuestro sistema clasifica a los clientes en tres niveles:
* **Riesgo Alto:** Probabilidad de churn ≥ 50%. Clientes con alta probabilidad de abandono que requieren acciones inmediatas de retención, como visitas comerciales, ofertas personalizadas o seguimiento prioritario.
* **Riesgo Medio:** Probabilidad de churn entre 30% y 50%. Clientes con señales tempranas de deterioro en su comportamiento de compra que deben ser monitoreados y considerados para campañas preventivas.
* **Riesgo Bajo:** Probabilidad de churn < 30%. Clientes con comportamiento estable y baja probabilidad de abandono, para los cuales se recomienda monitoreo rutinario..

El monitor desarrollado complementa esta clasificación proporcionando una vista Cliente 360°, incluyendo perfil comercial, factores de riesgo identificados por el modelo y estrategias de intervención recomendadas para apoyar la toma de decisiones del equipo comercial.

## 🚀 Cómo ejecutar el proyecto
1. Ingresa al siguiente link y descarga los archivos .csv: https://drive.google.com/drive/folders/1iVC0aG5SAzDBc6BT9zTnFbJFhdd7g9hO?usp=sharing
2. Clona este repositorio o descarga los notebooks.
3. Descarga los datasets originales de Arca Continental y colócalos en una carpeta llamada `data/`.
4. Ejecuta primero `1_EDA.ipynb` para ver los hallazgos y luego `2_Modelado_y_Scoring.ipynb` para generar las predicciones.
