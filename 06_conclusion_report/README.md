
# Customer Credit Default Prediction

This GitHub repository contains our final submission for the AAI500 course (Applied Artificial Intelligence). The project focuses on predicting whether a customer is likely to default on their credit payment using machine learning.

## Objective

The goal was to create a predictive model that uses customer-related information to estimate the chances of credit default. The data used includes both financial and personal details.

## Key Features

- **Dataset**: Sourced from Kaggle, containing 70,000 training samples and 33,000 test samples.
- **Classification Type**: Binary — 0 (No Default), 1 (Default).
- **Original Features**: 189 columns reduced to 72 after filtering.
- **Label**: `SeriousDlqin2yrs` — indicates default within 2 years.

## Data Preprocessing Steps

- Missing numerical values were replaced using median values.
- Categorical variables were handled using One-Hot Encoding.
- Features were scaled using RobustScaler to limit the influence of outliers.
- Addressed class imbalance using class weights.

## Feature Selection Approach

- **Information Value (IV)**:
  - Helped identify weak or suspicious features.
  - 85 columns were dropped based on IV thresholds.

- **Correlation Analysis**:
  - Removed 16 columns that were highly correlated (above 75%) to reduce redundancy.

Final selected features: **72**

## Machine Learning Models Tested

| Algorithm           | ROC AUC | F1 Score | Accuracy |
|--------------------|---------|----------|----------|
| Logistic Regression| 0.9352  | 0.7991   | 0.8840   |
| Decision Tree      | 0.9015  | 0.7752   | 0.8564   |
| XGBoost            | 0.9617  | 0.8033   | 0.9065   |
| **Random Forest**  | **0.9633**  | **0.8049**   | **0.9091**   |

## Final Model Choice: Random Forest

- Performed best among all models tested.
- Handled imbalanced data, categorical variables, and outliers efficiently.
- Produced consistent and interpretable results.

## Business Value

- Assists banks in identifying high-risk applicants.
- Improves efficiency by automating approvals for low-risk profiles.
- Minimizes financial losses and supports better lending decisions.

## 📂 Project Structure

```
📁 01_data
    └── IV_result.csv, REAMDE.md, null_percentage_df.csv, processed_test_data.csv, processed_train_data.csv, test_data.csv, train_data.csv, train_labels.csv, zero_percentage_df.csv

📁 02_data_prep
    └── data_prep_and_analysis.ipynb, REAMDE.md

📁 03_analysis
    └── data_analysis.ipynb, REAMDE.md

📁 04_modeling
    └── Baseline Model.ipynb, Advance Modeling.ipynb, README.md

📁 05_final_analyses
    └── final_analysis.ipynb, README.md

📁 06_conclusion_report
    └── Final_Project-Report-Team-7.pdf, Final_Project-Report-Team-7 Presentation.pdf, README.md, conclusions.ipynb, Advance_modeling_Updated.ipynb

README.md
requirements.txt
Instruction_README_GitHub-AAI.docx
```

## Summary

Random Forest delivered the highest accuracy and F1 score, making it the most reliable model in this case. We recommend its use in credit risk systems, supported by regular updates and fairness checks.

## Team Members

- Anugrah Rastogi – Data Preparation, EDA, Plot, and Analysis 
- Dhrub Satyam – Model Slection, Model Training and Hyperparameter Tuning
- Mallesham D – Final Analysis, Conclusions, Reports
