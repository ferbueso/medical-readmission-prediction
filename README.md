# Hospital Readmission Prediction
This repository contains a machine learning project aimed at predicting hospital readmissions. It involves data preprocessing, model training, hyperparameter optimization, and evaluation of different models, including SVC, Random Forest, and XGBoost, using various performance metrics.

## Table of Contents

- [Dataset Citation](#dataset-citation)
- [Overview](#overview)
- [Data Preprocessing](#data-preprocessing)
- [Modeling](#modeling)
- [Evaluation Metrics](#evaluation-metrics)
- [Usage](#usage)
- [Results](#results)

## Dataset Citation
Clore, J., Cios, K., DeShazo, J., & Strack, B. (2014). Diabetes 130-US Hospitals for Years 1999-2008 [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5230J.

## Overview

The goal of this project is to predict hospital readmissions using patient data. The project includes the following steps:
1. Data cleaning and preprocessing
2. Model training with hyperparameter optimization
3. Evaluation using performance metrics such as accuracy, precision, recall, and F1-score
4. Visualizing the results through plots

## Data Preprocessing

The dataset was cleaned and preprocessed by:
- Replacing missing values marked as ‘?’ with NaN
- Mapping categorical variables (e.g., `admission_type`, `discharge_disposition`, `admission_source`) using external ID mappings
- Simplifying the target variable `readmitted` into binary labels (‘0’ for no readmission, ‘1’ for readmission)

## Modeling

Three models were used for prediction:
1. **Support Vector Classifier (SVC)**
2. **Random Forest Classifier**
3. **XGBoost Classifier**

Hyperparameter optimization was performed for each model using Group GridSearchCV, and the best model was selected based on recall performance, which is crucial for this task.

## Evaluation Metrics

Since accuracy alone can be misleading, the following metrics were used:
- **Precision**: Ensures flagged patients are truly at risk, reducing unnecessary follow-ups.
- **Recall**: Captures as many actual readmissions as possible, preventing missed interventions.
- **F1-score**: A balance between precision and recall.
- **Confusion Matrix**: Provides insights into true and false predictions.
