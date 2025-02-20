# Integrated Energy System Multi-Load Prediction

This repository contains code and a report for predicting energy loads (electric, cooling, heating) in an integrated energy system using electricity usage data (Jan 2023) and meteorological data from Taiwan’s Central Weather Bureau.

## Overview
- **Objective:** Predict energy loads to optimize energy dispatch and reduce carbon emissions.
- **Approach:** Convert continuous load values into binary labels (high/low) and apply multi-output binary classification.
- **Models:** KNN, Random Forest, AdaBoost, Gradient Boosting, SVM (using MultiOutputClassifier).

## Data
- **Energy Data:** Internal company data (`energy_data.xlsx`)
- **Meteorological Data:** Taiwan Central Weather Bureau  
  *Citation:* Central Weather Bureau. (2023). *Central Weather Bureau Meteorological Data* [Data set]. Retrieved from [https://www.cwb.gov.tw/](https://www.cwb.gov.tw/)

## Methodology
- **Data Cleaning:**  
  - Derived features: Season, Daylight_Duration  
  - Removed redundant features (e.g., GHG, Year, DOW)  
  - Handled missing values/outliers and applied Z-score standardization.
- **EDA:**  
  - Visualized distributions (histograms, box plots, scatter plots, heatmaps)  
  - Retained low-correlation features to explore potential hidden predictive power.
- **Modeling:**  
  - Employed multiple models with hyperparameter tuning (GridSearchCV) and cross-validation.
  - Evaluated using confusion matrices and ROC/AUC.

## Results
- **Best Performance:** Random Forest and SVM (~87% accuracy, AUC ≈ 1.00).
- **Key Findings:** Temperature, Hour, and Month are major drivers; low-correlation features might enhance accuracy when further refined.

## How to Run
1. **Clone the Repository:**
   ```bash
   git clone https://github.com/Joeychen80627/Integrated-Energy-System-Multi-Load-Prediction.git
   cd Integrated-Energy-System-Multi-Load-Prediction
