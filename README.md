# ⚡ Electricity Demand Forecasting Project

> 🏅 Our team placed **4th out of 11** at the 2025 Datathon in Zurich, organized around Alpiq's forecasting challenge.

---

## 📊 Project Overview

This project focuses on predicting **hourly electricity demand** for thousands of consumers across Italy and Spain.

During the 2025 Alpiq Datathon, our team was tasked with developing a model to forecast **an entire month of hourly demand** for each individual consumer. We began with a baseline model that averaged consumption by weekday and hour, using the prior month's data.

From there, we iteratively improved performance through advanced modeling techniques and feature engineering to boost accuracy and reduce test loss.

---

## 🛠️ How to Use

### 📦 Prepare the Dataset

1. Place the dataset files in the **root directory**.
2. Unzip the provided `model_weights.zip` file in the root — these weights are required for imputation during preprocessing.

---

### 🚀 Run the Main Notebook

Run the following notebook to execute the full pipeline:

📓 [`notebooks/per_consumer_modeling.ipynb`](https://github.com/Drykx/Hackathon2025-ETH/blob/main/notebooks/per_consumer_modeling.ipynb)

This notebook covers:

- Data loading and preprocessing  
- Imputation using the Global Model  
- Training and evaluating per-consumer models  

> ✅ This is the only notebook you need to run the full forecasting workflow.

---

## 🤖 Developed Models

### 🔁 Global Model

Used **consumer ID** as an input to impute missing values in the demand series, serving as a foundation for preprocessing.

### 👤 Per-Consumer Models

Trained separately for each consumer, using carefully engineered features such as:

- Time-based cyclic features (sine/cosine)
- Temperature and sunlight data
- Weekend and holiday flags
- Lag features (1 day, 1 week, 2 weeks)

We selected **LightGBM** for both imputation and forecasting due to its speed and accuracy.

---

## 📂 Repository Structure

- `README.md` — Project overview and instructions  
- `datathon2025_quAIntly_presentation.pptx` — Final presentation  
- `configs/` — Configuration files  
- `datasets2025/` — Input data (Italy, Spain, holidays, weather, etc.)  
- `environmentAlpiqDatathon.yml` — Dependency list (conda environment)  
- `model.pkl` — Trained model file  
- `notebooks/` — Jupyter notebooks for development and analysis  
- `predictions/` — Model output predictions  
- `scripts/` — Scripts for preprocessing, forecasting, and scoring  
- `setup.py` — Setup script for packaging  
- `src/` — Core code: preprocessing, feature engineering, training

---

## 🙏 Acknowledgments

Special thanks to **Alpiq** for organizing the challenge and providing the opportunity to work on a real-world, large-scale energy forecasting problem!
