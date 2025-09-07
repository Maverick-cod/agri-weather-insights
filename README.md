
---

# 🌾 + 🌦️ + 📊 Agri-Weather Insights

**Prototype RTGS-Style AI Analyst for Telangana Open Data — Agriculture + Weather Sector**

<p align="center">
  <img src="https://img.shields.io/badge/Language-Python-blue?style=for-the-badge&logo=python" />
  <img src="https://img.shields.io/badge/Framework-Jupyter-orange?style=for-the-badge&logo=jupyter" />
  <img src="https://img.shields.io/badge/Data-Pandas-green?style=for-the-badge&logo=pandas" />
  <img src="https://img.shields.io/badge/Visualization-Matplotlib%20|%20Seaborn-red?style=for-the-badge&logo=plotly" />
  <img src="https://img.shields.io/badge/Backend-RTGS%20Pipeline-purple?style=for-the-badge&logo=fastapi" />
  <img src="https://img.shields.io/badge/Output-Policy%20Ready-blue?style=for-the-badge&logo=gov" />
</p>  

📂 **Dataset & Resources**
[👉 Access Google Drive Folder](https://drive.google.com/drive/folders/1XQ3lvMYUm0kvVloAyEhnxs9hYEToP18H?usp=drive_link)

---

## 🔑 Key Features

### 1. 🌐 Comprehensive Data Ingestion

* **Implementation:** `load_and_standardize_data(file_path: str)` (Cell 4)
* **Scale:** 2.3M records processed with `pd.read_csv(..., chunksize=100000)`
* **Integrity:** Zero missing values, with detailed logging

---

### 2. ⏳ Temporal Feature Engineering

* Extracted **year, month, day, quarter, season**
* Rolling averages: `7-day` & `30-day rainfall trends`

---

### 3. 🛡️ Advanced Quality Control

* Outlier detection: **Z-score + IQR**
* Flags: `temp_consistency_flag`, `humidity_consistency_flag`, `{col}_outlier_flag`

---

### 4. 🌱 Agricultural Risk Modeling

* **Weather Stress Index (WSI)**
* **Agricultural Risk Index (ARI)** → 0–100 scale
* Tiered risks: `Low / Medium / High`

---

### 5. 🏙️ District Vulnerability Assessment

* Generates **district-level insights**:

  * Avg. rainfall
  * Avg. ARI
  * High-risk days count

---

### 6. 📐 Statistical Validation Framework

* **ANOVA** → rainfall variation
* **Correlation** → rainfall vs. temperature

---

### 7. 📢 Policy-Ready Output Generation

* Recommendations on: rainfall deficit, high-risk frequency, heatwaves, dry spells
* Tagged priority: **High / Medium**

---

### 8. 📂 Multi-Format Output System

* **Exports:** CSV, Excel, JSON, Parquet
* **Visualizations:** PNG + Interactive HTML

---

### 9. 💻 Interactive Access Infrastructure

* **RTGSCLI Class** → explore results:

  * `show_summary()`
  * `show_high_risk_districts()`
  * `show_policy_recommendations()`
* Interactive **dashboard with ipywidgets**

---

### 10. 🚨 Actionable Intelligence Delivery

* **Function:** `run_rtgs_pipeline()` → transforms raw data into:

  * ✅ Clean dataset
  * ✅ Insights JSON
  * ✅ Policy-ready reports

---

## 📊 Example Outputs

<p align="center">
  <img src="https://img.shields.io/badge/Output-Insights_JSON-success?style=flat-square&logo=json" />
  <img src="https://img.shields.io/badge/Output-Visualizations-orange?style=flat-square&logo=chartdotjs" />
  <img src="https://img.shields.io/badge/Output-Policy_Recs-blueviolet?style=flat-square&logo=gov" />
  <img src="https://img.shields.io/badge/Export-CSV%20|%20Excel-lightgrey?style=flat-square&logo=microsoft-excel" />
</p>  

---

## 🚀 Vision

This project bridges **open government data** with **AI-powered analytics**, transforming raw weather & agriculture datasets into **decision-ready intelligence** for policy makers, researchers, and farmers.

---
