# Predictive Modelling for Methane (CH₄) Emissions Estimation

**MSc Business Analytics Consultancy Project/Dissertation 2024-25**

This project develops supervised machine learning models to predict methane (CH₄) emissions from UK facilities using spatial, sectoral, and climate data.

## Project Overview

The goal is to build predictive models that can estimate methane emissions using contextual data sources, including:

- **Climate conditions**: Temperature, rainfall, wind speed, pressure
- **Spatial and geographic context**: Urbanicity, region, population density
- **Sectoral and operator-level metadata**: Industry sector, facility operator information

## Objectives

- Train and evaluate multiple regression models to estimate CH₄ emissions
- Compare performance across model types using standard metrics (R², MAE, RMSE)
- Use SHAP values to interpret model predictions and identify key drivers
- Extract spatial, sectoral, and environmental insights relevant to climate policy

## Dataset

The modeling dataset combines:

- **Point Source Emissions Data**: Methane emissions reported by UK facilities (2018–2022)
- **Climate Grid Data**: High-resolution NetCDF files with monthly climate observations (1 km × 1 km grid)

### Data Sources
- Historical point-source emissions (2018–2022)
- Sector-level and geographic metadata
- High-resolution climate variables from NetCDF grids

## Methodology

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

## Project Structure

```
Dissertation project/
├── README.md
├── Copy_of_final_ch4_greenteai_modelling.ipynb  # Main analysis notebook
└── Dissertation_Project.pdf  # Dissertation document
```

## Getting Started

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

## Notebook Overview

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

## Key Features

- **Target Variable**: Log-transformed methane emissions (`log_emission`)
- **Time Period**: 2018 to 2022
- **Geographic Scope**: United Kingdom
- **Spatial Resolution**: 1 km × 1 km grid cells

## Results

### Model Performance

The XGBoost model, trained on a strategically engineered subset of features, emerged as the most effective algorithm in terms of predictive accuracy and generalisability. The final tuned model achieved:

- **Test R²**: 0.72
- **MAE**: 0.27
- Outperformed baseline models while maintaining interpretability through SHAP analysis

### Key Findings

**Strategic Feature Selection:**
- Key predictors included winter temperature, mean wind speed, regional classifications, facility density within 25 km, and sectoral identifiers
- Strategic feature selection played a pivotal role in reducing overfitting

**Spatial and Sectoral Patterns:**
- The Oil and Gas, Power Generation, Waste, and Chemical sectors were consistently the highest emitters
- Emissions hotspots tended to co-locate with regions exhibiting elevated temperatures and wind speeds
- Climate overlays highlighted how emissions patterns correlate with environmental conditions

**SHAP Feature Importance Analysis:**
- Industrial sector encodings were the most influential predictors (Oil & Gas exploration, Major Power Producers, Natural Gas Processing)
- Spatial characteristics (latitude, longitude, regional density metrics) ranked highly
- Climate variables (mean annual temperature, winter temperature, annual wind speed) were among top-ranked numerical features
- Common patterns among high-emitting sites included proximity to other facilities, sector classification, location in Scotland or high-latitude zones, and elevated wind speed and winter temperature values

**Model Interpretation:**
- SHAP values confirmed that methane emissions are governed by a multifactorial interplay of sector, location, and seasonal conditions
- The interpretability of results provides actionable insight for stakeholders seeking to identify super-emitters and prioritize monitoring resources

## References

Akiba, T., Sano, S., Yanase, T., Ohta, T. and Koyama, M. (2019) 'Optuna: A Next-generation Hyperparameter Optimization Framework', Proceedings of the 25th ACM SIGKDD International Conference on Knowledge Discovery & Data Mining.

Alam, G.M.I. et al. (2025) 'Deep learning model based prediction of vehicle CO₂ emissions with eXplainable AI integration', Scientific Reports, 15(1).

Alnuaimi, H.S. et al. (2025) 'Machine Learning Applications for Carbon Emission Estimation', Resources, Conservation & Recycling Advances.

Baba et al. (2025) Applied XGBoost and SHAP to predict methane emissions at a cattle market, identifying temporal and seasonal features as dominant drivers.

Balać, N. et al. (2025) 'Implementation of XGBoost Models for Predicting CO₂ Emission and Specific Tractor Fuel Consumption', Agriculture, 15(11).

Bhardwaj, P., Kumar, R., Mitchell, D.A., Randles, C.A., Downey, N., Blewitt, D. and Kosovic, B. (2022) 'Evaluating the detectability of methane point sources from satellite observing systems using microscale modeling', Scientific Reports, 12(1).

Bista, P. et al. (2025) 'Evaluating Machine Learning Models for Greenhouse Gas Emissions Prediction in Diversified Semi-Arid Cropping Systems', Soil Science Society of America Journal, 89(2).

Chai, T. and Draxler, R.R. (2014) 'Root mean square error (RMSE) or mean absolute error (MAE)?', Geoscientific Model Development, 7(3), pp.1247–1250.

Chang, H.-T., Chern, Y.-R., Asri, A.K., Liu, W.-Y., Hsu, C.-Y., Hsiao, T.-C., Chi, K.H., Lung, S.-C.C. and Wu, C.-D. (2025) 'Innovating Taiwan's greenhouse gas estimation: A case study of atmospheric methane using GeoAI-based ensemble mixed spatial prediction model', Journal of Environmental Management, 380.

Cionni, I., Lledó, L., Torralba, V. and Dell'Aquila, A. (2022) 'Seasonal predictions of energy-relevant climate variables through Euro-Atlantic Teleconnections', Climate Services, 26.

Cutler, J., Li, B., Alhnaity, B., Partridge, T., Thompson, M. and Meng, Q. (2025) 'AI for sustainable land management and greenhouse gas emission forecasting: advancing climate action', IEEE CACML.

Esiri, B. and Ekemezie, P. (2024) 'Standardizing methane emission monitoring: A global policy perspective for the oil and gas industry', Engineering Science & Technology Journal, 5(6).

Hasan, R. et al. (2025) 'AI-Driven Greenhouse Gas Monitoring: Enhancing Accuracy, Efficiency, and Real-Time Emissions Tracking', AIMS Environmental Science, 12(3).

IPCC (2021) Climate Change 2021: The Physical Science Basis. Contribution of Working Group I to the Sixth Assessment Report of the Intergovernmental Panel on Climate Change.

Jeong, S., Hamilton, S.D., Johnson, M.S., Wu, D., Turner, A.J. and Fischer, M.L. (2025) 'Applying Gaussian Process Machine Learning and modern probabilistic programming to satellite data to infer CO₂ emissions', Environmental Science & Technology.

Kow, P.-Y., Liou, J.-Y., Yang, M.-T., Lee, M.-H., Chang, L.-C. and Chang, F.-J. (2024) 'Advancing climate-resilient flood mitigation: Utilizing transformer-LSTM for water level forecasting at pumping stations', Science of The Total Environment, 927.

Lei, T., Chen, X., Ma, S., Guan, D. and Jing, L. (2025) 'A global inventory of methane emissions from abandoned oil and gas wells and possible mitigation pathways', National Science Review, 12(7).

Li, Z., Wang, Y., Liu, J. and Xian, J. (2025) 'Using machine learning to unravel chemical and meteorological effects on ground-level ozone: Insights for ozone-climate control strategies', Environment International, 201.

Liu, Z., Lu, Z., Zhu, W., Yuan, J., Cao, Z., Cao, T., Liu, S., Xu, Y. and Zhang, X. (2025) 'Comparison of machine learning methods for predicting ground-level ozone pollution in Beijing', Frontiers in Environmental Science, 13.

Luo, R., Wang, J. and Gates, I. (2024) 'Forecasting Methane Data Using Multivariate Long Short-Term Memory Neural Networks', Environmental Modeling & Assessment, 29(3).

Mathew, N., Somanathan, A., Tirpude, A. and Arfin, T. (2024) 'The impact of short-lived climate pollutants on the human health', Environmental Pollution and Management, 1.

Saunois, M., Stavert, A.R., Poulter, B., Bousquet, P., Canadell, J.G., Jackson, R.B., Raymond, P.A., Dlugokencky, E.J., Houweling, S., Patra, P.K., Ciais, P., Arora, V.K., Bastviken, D., Bergamaschi, P., Blake, D.R., Brailsford, G., Bruhwiler, L., Carlson, K.M., Carroll, M. and Castaldi, S. (2020) 'The Global Methane Budget 2000–2017', Earth System Science Data, 12(3).

Sherwin, E.D., Rutherford, J.S., Chen, Y., Aminfard, S., Kort, E.A., Jackson, R.B. and Brandt, A.R. (2023) 'Single-blind validation of space-based point-source detection and quantification of onshore methane emissions', Scientific Reports, 13(1).

Si, M. et al. (2024) 'Long-Term Evaluation of Machine Learning Based Methods for Air Emission Monitoring', Environmental Management, 75(3).

Smeeton, G. (2022) Net zero: why is it necessary? Energy & Climate Intelligence Unit.

Sysoeva et al. (2024) Used SHAP to disentangle the role of climate and facility-level factors in methane concentrations across Alberta's oil sands, highlighting the dual role of atmospheric features and facility configuration.

Wang, M., Li, Y., Yuan, H., Zhou, S., Wang, Y., Muhammad, R., Ikram, A. and Li, J. (2023) 'An XGBoost–SHAP approach to quantifying morphological impact on urban flooding susceptibility', Ecological Indicators, 156.

West, R.M. (2021) 'Best practice in statistics: The use of log transformation', Annals of Clinical Biochemistry: International Journal of Laboratory Medicine, 59(3).

Xu, Y., Yazdinejad, A., Wang, H. and Kong, J.D. (2025) 'Methane monitoring: A systematic review of multi-source data integration challenges and solutions', SSRN.

Yazdinejad, A., Wang, H. and Kong, J.D. (2025) 'Advanced AI-driven methane emission detection, quantification, and localization in Canada: A hybrid multi-source fusion framework', SSRN.

Zhang, S., Ma, J., Zhang, X. and Guo, C. (2023) 'Atmospheric remote sensing for anthropogenic methane emissions: Applications and research opportunities', Science of The Total Environment, 893.

*For complete citations with DOIs and full details, please refer to the Dissertation_Project.pdf document.*

## Author

**Thomas Ramokgopa**  
MSc Business Analytics Consultancy  
2024-25

## License

This project is submitted as part of academic coursework. Please refer to the confidentiality statement in the dissertation document.

---

**Note**: This repository contains academic work. The dissertation PDF is included for reference but may contain confidential information as per the project partner's designation.

