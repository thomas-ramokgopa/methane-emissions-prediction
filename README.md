# Predictive Modelling for Methane (CH₄) Emissions Estimation

**MSc Business Analytics Consultancy Project/Dissertation 2024-25**

This project develops supervised machine learning models to predict methane (CH₄) emissions from UK facilities using spatial, sectoral, and climate data.

## 📋 Project Overview

The goal is to build predictive models that can estimate methane emissions using contextual data sources, including:

- **Climate conditions**: Temperature, rainfall, wind speed, pressure
- **Spatial and geographic context**: Urbanicity, region, population density
- **Sectoral and operator-level metadata**: Industry sector, facility operator information

## 🎯 Objectives

- Train and evaluate multiple regression models to estimate CH₄ emissions
- Compare performance across model types using standard metrics (R², MAE, RMSE)
- Use SHAP values to interpret model predictions and identify key drivers
- Extract spatial, sectoral, and environmental insights relevant to climate policy

## 📊 Dataset

The modeling dataset combines:

- **Point Source Emissions Data**: Methane emissions reported by UK facilities (2018–2022)
- **Climate Grid Data**: High-resolution NetCDF files with monthly climate observations (1 km × 1 km grid)

### Data Sources
- Historical point-source emissions (2018–2022)
- Sector-level and geographic metadata
- High-resolution climate variables from NetCDF grids

## 🔧 Methodology

### Models Implemented
- Baseline Linear Regression
- Random Forest Regressor
- XGBoost Regressor
- LightGBM Regressor (optional)
- Neural Network (MLPRegressor)

### Evaluation Metrics
- R² (Coefficient of Determination)
- MAE (Mean Absolute Error)
- RMSE (Root Mean Squared Error)

### Model Explainability
- SHAP (SHapley Additive exPlanations) values for feature importance analysis

## 📁 Project Structure

```
Dissertation project/
├── README.md
├── Copy_of_final_ch4_greenteai_modelling.ipynb  # Main analysis notebook
└── 897971_Thomas_Ramokgopa_Dissertation_Project_7240302_47196390 (2).pdf  # Dissertation document
```

## 🚀 Getting Started

### Prerequisites

```python
# Core Data Libraries
pandas
numpy

# Climate Data Handling
xarray
netCDF4
pyproj

# Data Visualization
matplotlib
seaborn
geopandas
plotly

# Machine Learning
scikit-learn
xgboost
lightgbm

# Model Explainability
shap
```

### Installation

```bash
pip install pandas numpy xarray netCDF4 pyproj matplotlib seaborn geopandas plotly scikit-learn xgboost lightgbm shap
```

## 📓 Notebook Overview

The main notebook (`Copy_of_final_ch4_greenteai_modelling.ipynb`) is organized as follows:

1. **Introduction and Objective**  
   Overview of methane emissions modeling, project goals, and context.

2. **Data Preparation and Preprocessing**  
   Loading datasets, merging climate and emissions data, handling missing values, and encoding.

3. **Exploratory Data Analysis (EDA)**  
   Identifying spatial, sectoral, and temporal trends in CH₄ emissions across the UK.

4. **Feature Engineering**  
   Creating climate interactions, regional aggregations, and spatial density features.

5. **Model Training and Evaluation**  
   Comparing full vs strategic models using XGBoost, Random Forest, and Optuna tuning.

6. **SHAP Feature Importance**  
   Visualizing and interpreting top predictors driving CH₄ output.

7. **Sources**  
   References for datasets and domain methodologies.

## 🔬 Key Features

- **Target Variable**: Log-transformed methane emissions (`log_emission`)
- **Time Period**: 2018 to 2022
- **Geographic Scope**: United Kingdom
- **Spatial Resolution**: 1 km × 1 km grid cells

## 📈 Results

[Results and findings will be documented here after model evaluation]

## 📚 References

[References and data sources will be listed here]

## 👤 Author

**Thomas Ramokgopa**  
MSc Business Analytics Consultancy  
2024-25

## 📄 License

This project is submitted as part of academic coursework. Please refer to the confidentiality statement in the dissertation document.

---

**Note**: This repository contains academic work. The dissertation PDF is included for reference but may contain confidential information as per the project partner's designation.

