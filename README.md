# 🩺 Predicción de Diabetes desde Notas Clínicas (NLP + ML)

Este proyecto tiene como objetivo desarrollar un sistema capaz de **predecir la presencia de diabetes** en pacientes a partir de **notas médicas en texto libre**.
Combina **procesamiento del lenguaje natural (NLP)** y **aprendizaje automático (ML)** para transformar texto clínico no estructurado en variables médicas relevantes y entrenar un modelo predictivo.

---

## 🎯 Objetivo del Proyecto

Construir un pipeline que:

1. **Obtenga y almacene** datos clínicos de pacientes desde una API.
2. **Extraiga información médica clave** de notas clínicas (HbA1c, glucosa, IMC, tabaquismo…).
3. **Entrene un modelo de Machine Learning** que prediga si un paciente tiene diabetes (`has_diabetes` = 0 o 1).

---

## 🧠 Tecnologías Utilizadas

* **Python 3.10+**
* **NLP:** `spaCy`, `medSpaCy`
* **Machine Learning:** `scikit-learn`, `Optuna`
* **Manejo de datos:** `pandas`, `requests`
* **Logging y utilidades:** `loguru`

---

## ⚙️ Flujo de Trabajo

1. **Descarga de datos:**
   El sistema obtiene datos de pacientes mediante una API (`https://api.hackupm2025.workers.dev/api/v1/patients/train`)
   y los guarda en `patients_train.csv.gz` para su posterior uso sin volver a llamar al servidor.

2. **Extracción NLP con medSpaCy:**
   Se identifican marcadores clínicos relevantes:

   * **HbA1c**, **Glucose**, **BMI**, y sus valores asociados.
   * Opcionalmente, **tabaquismo** y su contexto (negación, histórico, familiar).
   * Además, se contemplan historial de enfermedad del corazón e hipertensión.

3. **Entrenamiento del modelo:**

   * Se usa un **Random Forest** para predecir `has_diabetes`.
   * Se optimizan hiperparámetros mediante **Optuna**.

4. **Evaluación:**
   Métricas principales: *Accuracy*, *F1-score* y *ROC-AUC*.

---

## 📂 Estructura del Proyecto

```
.
├── data/
│   └── patients_train.csv.gz       # Dataset almacenado localmente
├── notebooks/
│   └── datos.ipynb                 # Notebook principal del proyecto
├── README.md
└── requirements.txt
```

---

## 🧩 Ejecución

1. **Instala las dependencias:**

   ```bash
   pip install -r requirements.txt
   ```

2. **Ejecuta el notebook principal:**
   Abre `notebooks/datos.ipynb` y corre todas las celdas secuencialmente:

   * Descarga y carga de datos
   * Extracción NLP
   * Entrenamiento y evaluación del modelo

3. **Resultado:**
   Se genera un modelo capaz de predecir si un paciente tiene diabetes a partir de su texto clínico.

---

## 📈 Resultados Esperados

* **Features extraídas automáticamente** desde texto médico.
* **Modelo entrenado y evaluado** sobre datos estructurados.
* **Análisis de importancia de variables** (por ejemplo, HbA1c y glucosa como factores más determinantes).

---

## 👥 Equipo

Proyecto desarrollado por **Compila2**
en el marco del **Hackathon Roche Diabetes Prediction Challenge 2025**.

> *“De texto clínico desordenado a predicción médica accionable.”*
