# 🌾 Telangana Agri-Weather RTGS System

[![Python 3.8+](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/downloads/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Pandas](https://img.shields.io/badge/Pandas-1.3+-blue.svg)](https://pandas.pydata.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-0.24+-orange.svg)](https://scikit-learn.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**AI-Powered Real-Time Gross Settlement System for Agricultural Risk Assessment in Telangana**

## 📊 Overview

A comprehensive data processing and analysis system for agricultural weather risk assessment in Telangana, India. This system processes meteorological data to generate actionable insights and predictive models for agricultural risk assessment.

![System Architecture](https://via.placeholder.com/800x400.png?text=RTGS+System+Architecture)

## 🚀 Key Features

### 🔄 Data Processing Pipeline
- **Large-scale Data Ingestion**: Handles 2.3M+ records with chunked processing
- **Automated Standardization**: Column normalization and type conversion
- **Temporal Feature Engineering**: Seasonality detection and rolling averages
- **Advanced Quality Control**: Dual outlier detection (Z-score + IQR methods)

### 📈 Risk Assessment Engine
- **Agricultural Risk Index (ARI)**: Multi-factor risk scoring system
- **Weather Stress Indicators**: Rainfall, temperature, humidity, and wind analysis
- **District-level Vulnerability Mapping**: Geospatial risk visualization

### 📊 Advanced Analytics
- **Predictive Modeling**: Rainfall forecasting and risk classification
- **Statistical Validation**: ANOVA testing and correlation analysis
- **Hypothesis Testing**: Seasonal and temperature-rainfall relationships

### 🎯 Policy-Ready Outputs
- **Priority-based Recommendations**: Data-driven policy suggestions
- **Multi-format Exports**: CSV, Parquet, Excel, JSON, PDF reports
- **Interactive Dashboards**: Real-time filtering and visualization

## 🛠️ Installation

```bash
# Clone repository
git clone https://github.com/your-username/telangana-agri-rtgs.git
cd telangana-agri-rtgs

# Install dependencies
pip install -r requirements.txt
```

### 📋 Requirements

The system requires the following Python packages:

- **Data Processing**: pandas, numpy
- **Visualization**: matplotlib, seaborn, plotly
- **Machine Learning**: scikit-learn
- **Utilities**: scipy, joblib, json, datetime

## 📁 Project Structure

```
RTGS_System/
├── RTGS_System.ipynb          # Main Jupyter notebook
├── rtgs_outputs/              # Generated outputs
│   ├── standardized/          # Standardized data
│   ├── cleaned/               # Cleaned datasets
│   ├── insights/              # Analysis results
│   ├── visualizations/        # Charts and graphs
│   ├── models/                # Trained ML models
│   └── reports/               # Comprehensive reports
└── README.md
```

## 🏃‍♂️ Usage

### 1. Configuration Setup
Modify the `Config` class to set:
- Data paths and output directories
- Risk thresholds and analysis parameters
- Visualization settings

### 2. Run Full Pipeline
```python
# Execute complete analysis pipeline
df_clean, insights, cli = run_rtgs_pipeline()
```

### 3. Interactive Analysis
```python
# Use CLI interface for exploration
cli.show_summary()
cli.show_high_risk_districts(top_n=5)
cli.show_policy_recommendations(top_n=5)
```

### 4. Export Results
```python
# Export to multiple formats
cli.export_results('csv')
cli.export_results('excel')
```

## 📊 Data Requirements

The system expects CSV data with the following columns:
- `district`, `mandal`, `date`
- `rainfall_mm`, `temp_min`, `temp_max`
- `humidity_min`, `humidity_max`
- `wind_min`, `wind_max`
- `source_file`

## 📈 Sample Outputs

### Risk Distribution by District
![Risk Distribution](https://via.placeholder.com/600x400.png?text=Risk+Distribution+Chart)

### Seasonal Rainfall Patterns
![Seasonal Analysis](https://via.placeholder.com/600x400.png?text=Seasonal+Rainfall+Analysis)

## 🏛️ Policy Applications

The system generates actionable recommendations for:
- Water conservation measures in drought-prone districts
- Emergency response planning for high-risk areas
- Heat stress management strategies
- Irrigation infrastructure development

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Telangana agricultural department for data support
- Meteorological departments for weather data
- Open-source community for data science libraries


<div align="center">
  <sub>Built with ❤️ for the farmers of Telangana</sub>
</div>
