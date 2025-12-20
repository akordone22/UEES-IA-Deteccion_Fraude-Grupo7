# UEES-IA-Deteccion_Fraude-Grupo7
# 📌 Resumen del Proyecto Final – Sistema de IA para Detección de Fraude en Pagos Digitales

## 🧾 Contexto
- Fraude financiero: 0.1% de transacciones → 60% de pérdidas.
- Problema actual: alta tasa de falsos positivos → bloqueos de pagos legítimos.

## 📊 Dataset Empleado
- **Dataset**: Datos sintéticos de transacciones bancarias
- **Descripción**: El dataset está conformado por 200.000 registros de transacciones, asociados a aproximadamente 5.000 usuarios únicos.


## 🎯 Objetivo General
Diseñar y validar un sistema supervisado de IA, explicable y adaptable, que maximice la detección de fraudes y minimice falsos positivos, integrando aprendizaje continuo.

## ✅ Objetivos Específicos
- Pipeline automatizado con >200 variables derivadas.
- Implementar IA explicable (SHAP) para justificar ≥95% de alertas.
- Arquitectura de scoring en tiempo real + dashboard de monitoreo.
- Estrategia de online learning para actualización periódica.

## 🛠️ Solución Propuesta
- **Tipo de problema**: Clasificación binaria (fraude vs legítimo).
- **Modelos**: XGBoost, LightGBM, ANN → Ensemble híbrido.
- **Explicabilidad**: SHAP para transparencia y cumplimiento.
- **Pipeline**: modular, escalable, adaptable a sistemas financieros.

## 🧠 Arquitectura Preliminar
1. Flujo transaccional en tiempo real.
2. Pipeline de feature engineering.
3. Modelos paralelos:
   - Ensemble supervisado + SHAP.
   - Autoencoder para anomalías.
   - GNN para patrones colusivos.
4. Consolidación de alertas → Dashboard de monitoreo.

## 📊 Datos
- Dataset sintético: 200,000 transacciones, 5,000 usuarios.
- Variables: demográficas, transaccionales, temporales, contextuales.
- Desbalance intencional: 0.1% fraude.
- Almacenamiento en CSV, estructura jerárquica (raw, processed, results).

## 📈 Metodología (14 semanas)
- F1–EDA y diseño de features.
- F3–Entrenamiento y comparación de modelos.
- F4–Explicabilidad con SHAP + GNN preliminar.
- F5–Dashboard prototipo con Streamlit.
- F6–Documentación y presentación final.

## 📌 Métricas
- Negocio: Precisión a Recall fijo (95%).
- Técnicas: AUC-PR, F1, matriz de confusión.

## ⚙️ Herramientas
- Python, Jupyter Notebook.
- Librerías: Pandas, NumPy, Scikit-learn, XGBoost, LightGBM, TensorFlow/PyTorch, SHAP, Optuna.
- Visualización: Matplotlib, Seaborn, Plotly, Streamlit, Power BI.
- Infraestructura: Google Colab Pro, instancias cloud con GPU.

## 🧾 Viabilidad
- Hardware: GPU NVIDIA T4 o superior.
- Presupuesto: $150–$500 (cloud computing).
- Riesgos: integración de múltiples enfoques, claridad de explicaciones SHAP.
- Mitigación: enfoque modular + reportes estandarizados.

## Análisis Dashboard
Se realizó una simulación de score combinando variables de riesgo que son las siguientes:
**Variable	Riesgo**
- is_foreign = 1		Riesgo alto
- high_amount = 1	Riesgo alto
- account_age_days < 30	Riesgo alto
- amount > avg_amount	Riesgo medio
- Horas nocturnas	Riesgo medio

Una vez que tenemos el score a partir de este creamos el Nivel de Riesgo
- Fraud_Score] >= 70, "Alto",
- Fraud_Score] >= 40, "Medio",
- Resto =  "Bajo"

Dado que el conjunto de datos no incluía un score de riesgo explícito, se construyó un Índice de Riesgo Transaccional basado en reglas heurísticas, utilizando variables comúnmente asociadas al fraude financiero. Posteriormente, el índice fue validado comparando los niveles de riesgo con la ocurrencia real de fraude.

## 📌 Autores
- **Nombre**: César Cabrera (04.Dashboard), Ana Lucía Espinoza (01_Base_Datos.ipynb), Andrea Ordoñez(02_Feature_Engineering_y_Scoring.ipynb), Andrea Tapia(03_Modelo_explicable_SHAP_values.ipynb)
- **Email**: cesar.cabrerav@uees.edu.ec - ana.espinozaa@uees.edu.ec - andrea.ordonezr@uees.edu.ec - andrea.tapian@uees.edu.ec

## Limitaciones presentes en el trabajo
Es importante tener en consideración que el proyecto funcionó bien, sin embargo en exportación de colab a GitHub se presentaron problemas con el notebook: "Proyecto_Final/notebooks/04_DashboardFraudes.ipynb", puesto que se realizó un dashboard para simular la información en el aplicativo Streamlit, el archivo que contiene la data era pesado, no obstante se optó por se subir el comprimido. Por lo cual se optó por hacer un Dashboard también en Power BI, para presentación del proyecto de estudio. 


## 📚 Referencias
- Chen & Guestrin (2016) – XGBoost.
- Ke et al. (2017) – LightGBM.
- Lundberg & Lee (2017) – SHAP.
- Molnar (2022) – Interpretable ML.
- Zhou et al. (2021) – GNNs en fraude.
- Chalapathy & Chawla (2019) – Anomaly detection.
- Bhattacharyya et al. (2011) – Credit card fraud mining.
