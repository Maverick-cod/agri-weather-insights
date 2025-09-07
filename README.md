# 🌾 Agri-Weather Insights  
**Prototype RTGS-Style AI Analyst for Telangana Open Data — Agriculture + Weather Sector**

📂 **Dataset & Resources**  
[👉 Access Google Drive Folder](https://drive.google.com/drive/folders/1XQ3lvMYUm0kvVloAyEhnxs9hYEToP18H?usp=drive_link)

---

## 🔑 Key Features

### 1. Comprehensive Data Ingestion
- **Implementation:** `load_and_standardize_data(file_path: str)` (Cell 4)  
- **Scale:** 2.3M records processed with `pd.read_csv(..., chunksize=100000)`  
- **Parameters:** 11 standardized columns  
- **Integrity:** Zero missing values, with detailed logging and `conversion_issues` tracking  

---

### 2. Temporal Feature Engineering
- Extracted **year, month, day, day_of_year, week_of_year, quarter** from `date`  
- **Seasonal categorization:** `get_season(month: int)` → Winter, Summer, Monsoon, Post-Monsoon  
- **Rolling averages:**  
  - 7-day rainfall: `rolling_avg_rainfall_7d`  
  - 30-day rainfall: `rolling_avg_rainfall_30d`  

---

### 3. Advanced Quality Control
- Dual outlier detection: **Z-score** + **IQR** methods  
- Data quality flags: `temp_consistency_flag`, `humidity_consistency_flag`, `{col}_outlier_flag`  

---

### 4. Agricultural Risk Modeling
- **Weather Stress Index (WSI):** Derived risk components (rainfall, temperature, etc.)  
- **Agricultural Risk Index (ARI):** Weighted sum, normalized to 0–100 scale  
- **Risk tiers:** 5-category system (`Low`, `Medium`, `High`) using `Config.RISK_THRESHOLDS`  

---

### 5. District Vulnerability Assessment
- **Functions:** `generate_insights(df: pd.DataFrame)`  
- Produces district-level statistics for:  
  - Avg. rainfall  
  - Avg. ARI  
  - Count of high-risk days (`high_risk_districts`)  

---

### 6. Statistical Validation Framework
- **ANOVA testing:** Seasonal rainfall variation (`stats.f_oneway`)  
- **Correlation analysis:** Temperature vs. rainfall (`stats.pearsonr`)  

---

### 7. Policy-Ready Output Generation
- **Function:** `generate_policy_recommendations(df)`  
- Recommendations on rainfall deficit, high-risk frequency, heatwaves, dry spells  
- Priority tagging: **High / Medium**  

---

### 8. Multi-Format Output System
- **Exports:**  
  - CSV & Parquet → `standardized/`, `cleaned/`  
  - Insights & reports (JSON) → `insights/`, `logs/`  
  - CSV & Excel with chunking → `export_results()`  
  - Visualizations → PNG & interactive HTML in `visualizations/`  

---

### 9. Interactive Access Infrastructure
- **RTGSCLI Class:**  
  - Explore results with:  
    - `show_summary()`  
    - `show_high_risk_districts()`  
    - `show_policy_recommendations()`  
    - `run_hypothesis_test()`  
  - Interactive dashboard with `ipywidgets`  

---

### 10. Actionable Intelligence Delivery
- **Function:** `run_rtgs_pipeline()`  
- End-to-end pipeline transforms raw input into:  
  - ✅ Cleaned dataset  
  - ✅ Validated insights JSON  
  - ✅ Policy recommendations CSV  

---

## 🚀 Vision
This project bridges **open government data** with **AI-powered analytics**, transforming raw weather and agriculture datasets into **decision-ready intelligence** for policy makers, researchers, and farmers.  

---
