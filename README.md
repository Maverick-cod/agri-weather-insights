# 🌾 🌦️ 📊 Agri-Weather Insights  
**Prototype RTGS-Style AI Analyst for Telangana Open Data — Agriculture + Weather Sector**  

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10%2B-blue.svg?style=for-the-badge&logo=python" />
  <img src="https://img.shields.io/badge/Jupyter-Notebook-orange.svg?style=for-the-badge&logo=jupyter" />
  <img src="https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Contributions-Welcome-brightgreen.svg?style=for-the-badge" />
</p>  

---

📂 **Dataset & Resources**  
[![Google Drive](https://img.shields.io/badge/📂%20Access%20Dataset-Google%20Drive-blue?style=flat&logo=google-drive)](https://drive.google.com/drive/folders/1XQ3lvMYUm0kvVloAyEhnxs9hYEToP18H?usp=drive_link)  

---

## 📑 Table of Contents
- [🔑 Key Features](#-key-features)  
- [🚀 Vision](#-vision)  
- [🛠️ Tech Stack](#️-tech-stack)  
- [📊 Example Outputs](#-example-outputs)  
- [⚡ Quick Start](#-quick-start)  
- [🤝 Contributing](#-contributing)  
- [📜 License](#-license)  

---

## 🔑 Key Features  

### 1️⃣ Comprehensive Data Ingestion  
- `load_and_standardize_data(file_path: str)` (Cell 4)  
- 2.3M records processed in **chunks of 100k**  
- 11 standardized columns, **zero missing values**  
- Full logging with conversion issue tracking  

---

### 2️⃣ Temporal Feature Engineering  
- Extracted **year, month, day, week, quarter**  
- Seasonal tagging: `Winter, Summer, Monsoon, Post-Monsoon`  
- Rolling averages:  
  - 7-day rainfall → `rolling_avg_rainfall_7d`  
  - 30-day rainfall → `rolling_avg_rainfall_30d`  

---

### 3️⃣ Advanced Quality Control  
- **Dual outlier detection** → Z-score + IQR  
- Flags for temp, humidity, and rainfall anomalies  

---

### 4️⃣ Agricultural Risk Modeling  
- Weather Stress Index (**WSI**)  
- Agricultural Risk Index (**ARI**) → normalized 0–100  
- Risk tiers: Low / Medium / High (Config thresholds)  

---

### 5️⃣ District Vulnerability Assessment  
- `generate_insights(df)` → per-district stats  
- Avg rainfall, Avg ARI, high-risk days count  

---

### 6️⃣ Statistical Validation  
- Seasonal ANOVA (rainfall variation)  
- Pearson correlation (Temp ↔ Rainfall)  

---

### 7️⃣ Policy-Ready Output  
- `generate_policy_recommendations(df)`  
- Insights on rainfall deficit, heatwaves, dry spells  
- Priority tagging → High / Medium  

---

### 8️⃣ Multi-Format Export  
- CSV + Parquet (cleaned/standardized)  
- JSON logs, Excel chunked exports  
- Visualizations → PNG & interactive HTML  

---

### 9️⃣ Interactive Access Infrastructure  
- **RTGSCLI Class** → CLI + Widgets  
- Methods: `show_summary()`, `show_high_risk_districts()`, `run_hypothesis_test()`  

---

### 🔟 Actionable Intelligence Delivery  
- End-to-end pipeline:  
  - ✅ Clean dataset  
  - ✅ Validated insights JSON  
  - ✅ Policy recommendations CSV  

---

## 🚀 Vision  
This project bridges **open government data** with **AI-powered analytics**, transforming raw weather & agriculture datasets into **decision-ready intelligence** for policymakers, researchers, and farmers.  

---

## 🛠️ Tech Stack  
- **Python 3.10+**  
- **Pandas / NumPy** (data processing)  
- **Matplotlib / Seaborn / Plotly** (visualization)  
- **Scikit-learn** (ML models)  
- **SciPy** (statistical testing)  
- **ipywidgets** (interactive UI)  

---

## 📊 Example Outputs  
<p align="center">
  <img src="https://img.shields.io/badge/📈-Visualization-blue?style=for-the-badge" />
</p>  

*(You can add screenshots here — e.g., rainfall plots, ARI maps, dashboards)*  

---
