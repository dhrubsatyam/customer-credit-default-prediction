# Credit Default Prediction - Machine Learning Model Comparison 
(Contribution: Dhrub Satyam - dsatyam@sandiego.edu)

## Problem Statement
This project focuses on building a machine learning model to predict customer credit default using real-world tabular data. The objective is to develop robust predictive models that can accurately identify customers who are likely to default on their credit obligations, enabling financial institutions to make informed lending decisions and mitigate risk.

## Overview
This project implements and compares multiple machine learning models for credit default prediction. The analysis is split across two Jupyter notebooks: a baseline implementation and advanced modeling techniques to evaluate performance improvements. The modeling work builds upon the exploratory data analysis (EDA) and preprocessing completed by Anugrah, utilizing the processed dataset generated from their comprehensive data exploration phase.

## Project Structure
 - baseline_model.ipynb          # Baseline implementation
 - advanced_modeling.ipynb       # Advanced modeling

## Data Source
The modeling work utilizes the processed dataset generated from comprehensive Exploratory Data Analysis (EDA) conducted by Anugrah. This preprocessed file includes:
- Cleaned and transformed features
- Handled missing values and outliers
- Feature engineering based on EDA insights
- Ready-to-use dataset for machine learning model training

## Methodology

### Baseline Model
- **Algorithm**: Logistic Regression
- **Purpose**: Establish performance benchmark
- **Implementation**: Standard logistic regression with basic preprocessing

### Advanced Models
The advanced modeling notebook explores multiple algorithms to improve upon the baseline:

- **Logistic Regression**: Enhanced version with hyperparameter tuning
- **Random Forest**: Ensemble method with multiple decision trees
- **XGBoost**: Gradient boosting framework
- **Decision Tree**: Single tree-based classifier

## Results Summary

### Model Performance Comparison

| Metric | Random Forest | XGBoost | Decision Tree | Logistic Regression |
|--------|---------------|---------|---------------|-------------------|
| **Accuracy** | **0.91** | 0.90 | 0.85 | 0.83 |
| **ROC AUC** | **0.9633** | 0.9576 | 0.8808 | 0.9057 |
| **F1 Score (Class 1)** | **0.8049** | 0.7906 | 0.6855 | 0.7134 |
| **Precision (Class 1)** | **0.85** | 0.82 | 0.75 | 0.63 |
| **Recall (Class 1)** | **0.76** | **0.76** | **0.63** | **0.82** |

### Key Findings

**Best Overall Performance**: **Random Forest**
- Achieved highest accuracy (91%) and ROC AUC (0.9633)
- Best balance of precision (85%) and recall (76%) for identifying default cases
- Superior F1 score (0.8049) indicating optimal precision-recall trade-off for credit risk assessment

**Performance Insights**:
- **Random Forest** outperformed all other models across most metrics, making it ideal for credit default prediction
- **XGBoost** showed competitive performance as second-best model
- **Logistic Regression** demonstrated highest recall (82%) but lower precision, potentially leading to more conservative lending decisions
- **Decision Tree** showed the weakest performance, likely due to overfitting on the credit data

## Model Analysis

### Random Forest Advantages
- **Robust Performance**: Ensemble method reduces overfitting
- **Feature Importance**: Provides insights into variable significance
- **Balanced Metrics**: Excellent trade-off between precision and recall

### XGBoost Performance
- Strong second-place performance across all metrics
- Gradient boosting approach shows competitive results
- Good alternative when interpretability is less critical

### Baseline vs Advanced
The advanced models show significant improvement over the baseline:
- **Accuracy improvement**: 91% vs 83% (8 percentage points)
- **ROC AUC improvement**: 0.9633 vs 0.9057 (0.0576 increase)
- **F1 Score improvement**: 0.8049 vs 0.7134 (0.0915 increase)

## Technical Implementation

### Notebooks Description

#### `baseline_model.ipynb`
- Loading and initial exploration of processed dataset from Anugrah's EDA
- Baseline logistic regression implementation for credit default prediction
- Initial performance evaluation and metrics calculation
- Foundation for advanced model comparison

#### `advanced_modeling.ipynb`
- Advanced feature engineering on the preprocessed credit data
- Multiple algorithm implementation and comparison
- Hyperparameter tuning for optimal performance
- Comprehensive model evaluation with business-relevant metrics
- Performance comparison and analysis for credit risk assessment

## Usage

1. **Start with Baseline**: Run `baseline_model.ipynb` to understand the data and establish baseline performance
2. **Advanced Analysis**: Execute `advanced_modeling.ipynb` to explore improved modeling techniques
3. **Model Selection**: We can use Random Forest for production deployment based on superior performance

## Dependencies
- pandas
- numpy
- scikit-learn
- xgboost
- matplotlib/seaborn (for visualization)
- jupyter notebook

## Conclusion

The Random Forest model emerges as the clear winner with 91% accuracy and excellent performance across all evaluation metrics for credit default prediction. This ensemble approach successfully balances bias-variance trade-off while providing robust predictions for identifying potential defaulters. The significant improvement over the baseline logistic regression (8 percentage points in accuracy) demonstrates the value of exploring advanced modeling techniques in credit risk assessment.

The high precision (85%) ensures that the model minimizes false positives (incorrectly flagging good customers as potential defaulters), while maintaining reasonable recall (76%) to catch actual default cases. This balance is crucial for financial institutions to maintain customer relationships while managing risk effectively.
