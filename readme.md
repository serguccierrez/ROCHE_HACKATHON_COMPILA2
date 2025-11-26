# 🩺 Predicción de Diabetes desde Notas Clínicas (NLP + ML)

> **ES:** Proyecto desarrollado para el **Roche Diabetes Prediction Challenge 2025**, centrado en predecir diabetes a partir de texto clínico.  
> **EN:** Project developed for the **Roche Diabetes Prediction Challenge 2025**, focused on predicting diabetes from clinical free-text notes.

---

## 📌 Descripción | Description

🟢 **ES:**  
Este proyecto desarrolla un sistema capaz de **predecir la presencia de diabetes** analizando **notas médicas en texto libre**.  
Combina **procesamiento del lenguaje natural (NLP)** y **aprendizaje automático (ML)** para extraer variables clínicas relevantes y entrenar un modelo predictivo.

🔵 **EN:**  
This project builds a system that **predicts the presence of diabetes** using **free-text clinical notes**.  
It combines **natural language processing (NLP)** and **machine learning (ML)** to extract meaningful clinical features and train a predictive model.

---

## 🎯 Objetivo del Proyecto | Project Goal

🟢 **ES:**  
Construir un pipeline que:  
1. **Obtenga y almacene** datos clínicos mediante una API.  
2. **Extraiga información médica clave** de notas clínicas (HbA1c, glucosa, IMC, tabaquismo…).  
3. **Entrene un modelo de Machine Learning** para predecir si un paciente tiene diabetes (`has_diabetes` = 0/1).

🔵 **EN:**  
Build a pipeline that:  
1. **Fetches and stores** clinical patient data from an API.  
2. **Extracts key medical information** from clinical notes (HbA1c, glucose, BMI, smoking…).  
3. **Trains a Machine Learning model** to predict whether a patient has diabetes (`has_diabetes` = 0/1).

---

## 🧠 Tecnologías Utilizadas | Technologies Used

- **Python 3.10+**  
- **NLP:** `spaCy`, `medSpaCy`  
- **Machine Learning:** `scikit-learn`, `Optuna`  
- **Data Handling:** `pandas`, `requests`  
- **Logging:** `loguru`  

---

## ⚙️ Flujo de Trabajo | Workflow

🟢 **ES:**  
1. **Descarga de datos:**  
   Los datos se obtienen desde la API  
   `https://api.hackupm2025.workers.dev/api/v1/patients/train`  
   y se guardan en `patients_train.csv.gz`.

2. **Extracción NLP:**  
   Con `medSpaCy` se identifican marcadores clínicos como:  
   - **HbA1c**, **Glucose**, **BMI** y sus valores asociados.  
   - Información opcional sobre **tabaquismo** y contexto (negación, histórico, familiar).  
   - Historial de **enfermedad cardíaca** e **hipertensión**.

3. **Entrenamiento del modelo:**  
   - Se emplea un **Random Forest**.  
   - Optimización de hiperparámetros con **Optuna**.

4. **Evaluación:**  
   Métricas: *Accuracy*, *F1-score*, *ROC-AUC*.

🔵 **EN:**  
1. **Data download:**  
   Patient data is fetched from the API  
   `https://api.hackupm2025.workers.dev/api/v1/patients/train`  
   and stored locally as `patients_train.csv.gz`.

2. **NLP extraction:**  
   Using `medSpaCy`, the system detects:  
   - **HbA1c**, **Glucose**, **BMI** and associated values.  
   - Optional **smoking status** with context (negation, historical, family).  
   - **Heart disease** and **hypertension** history.

3. **Model training:**  
   - A **Random Forest** classifier is used.  
   - Hyperparameters optimized with **Optuna**.

4. **Evaluation:**  
   Metrics: *Accuracy*, *F1-score*, *ROC-AUC*.

---

## 📂 Estructura del Proyecto | Project Structure

```
.
├── data/
│   └── patients_train.csv.gz
├── notebooks/
│   └── datos.ipynb
├── README.md
└── requirements.txt
```

---

## 🧩 Ejecución | How to Run

🟢 **ES:**  
1. Instala dependencias:  
   ```bash
   pip install -r requirements.txt
   ```
2. Abre `notebooks/datos.ipynb` y ejecuta todas las celdas:  
   - Descarga y carga de datos  
   - Extracción NLP  
   - Entrenamiento y evaluación del modelo  

3. Obtendrás un modelo capaz de predecir diabetes a partir de texto clínico.

🔵 **EN:**  
1. Install dependencies:  
   ```bash
   pip install -r requirements.txt
   ```
2. Open `notebooks/datos.ipynb` and run all cells:  
   - Data download and loading  
   - NLP extraction  
   - Model training and evaluation  

3. A predictive model for diabetes from clinical text will be generated.

---

## 📈 Resultados Esperados | Expected Results

🟢 **ES:**  
- **Extracción automática** de features médicas.  
- **Modelo entrenado** sobre datos estructurados.  
- **Importancia de variables**, destacando HbA1c y glucosa.

🔵 **EN:**  
- **Automatic extraction** of medical features.  
- **Trained model** on structured data.  
- **Feature importance analysis**, with HbA1c and glucose among top predictors.

---

## 👥 Equipo | Team

🟢 **ES:**  
Proyecto desarrollado por **Compila2** en el **Hackathon Roche Diabetes Prediction Challenge 2025**.

🔵 **EN:**  
Project developed by **Compila2** for the **Roche Diabetes Prediction Challenge 2025**.

> _“De texto clínico desordenado a predicción médica accionable.”_  
> _“From messy clinical text to actionable medical prediction.”_

---

## 📬 Contacto | Contact

📩 **serguccierrez** → https://github.com/serguccierrez  
Si tienes preguntas o sugerencias, crea un **issue** en este repositorio.

If you have any questions or suggestions, feel free to open an **issue** in this repository.

---

💡 _Made with ❤️ by **Compila2**._