# Heart Disease Prediction

> An end-to-end machine learning pipeline that predicts the presence of heart disease from clinical attributes, comparing seven classifiers under cross-validation. Best model: Random Forest at ~92% accuracy and 0.96 ROC-AUC.

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.x-F7931E?logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-1.x-337AB7)
![Jupyter](https://img.shields.io/badge/Jupyter-notebook-F37626?logo=jupyter&logoColor=white)

## Overview

This project builds a complete supervised-learning pipeline for binary heart-disease classification on a combined clinical dataset of 1,190 patients (Statlog, Cleveland, and Hungary). It covers exploratory analysis, outlier removal, feature scaling and encoding, a comparison of seven classifiers, and feature-importance analysis to identify the strongest clinical predictors.

## Key Results

Cross-validated performance across all models (the headline numbers; a single 80/20 split produced a higher 96% for the top models, reported here under cross-validation for a more reliable estimate):

| Model | Accuracy | F1 | ROC-AUC |
|---|---|---|---|
| **Random Forest** | **0.92** | **0.93** | **0.96** |
| XGBoost | 0.89 | 0.90 | 0.94 |
| Decision Tree | 0.86 | 0.87 | 0.85 |
| SVC | 0.82 | 0.84 | 0.89 |
| Naive Bayes | 0.81 | 0.82 | 0.89 |
| Logistic Regression | 0.81 | 0.82 | 0.89 |
| KNN | 0.81 | 0.82 | 0.88 |

**Best model:** Random Forest — ~92% accuracy, 0.93 F1, 0.96 ROC-AUC under cross-validation.

**Top predictive features** (by correlation and model importance): ST slope, oldpeak, exercise-induced angina, chest pain type, and max heart rate.

## Approach

- **Data:** combined Statlog + Cleveland + Hungary heart dataset (1,190 patients, 11 clinical features), roughly balanced between disease / no-disease
- **EDA:** distributions, correlation heatmap, pairplots, and breakdowns of disease prevalence by sex, age, and cholesterol
- **Cleaning:** IQR-based outlier removal with before/after visualization
- **Preprocessing:** StandardScaler on continuous features (age, resting BP, cholesterol, max heart rate, oldpeak) and one-hot encoding of categorical features (chest pain type, resting ECG, ST slope)
- **Modeling:** compared 7 classifiers — Logistic Regression, Decision Tree, Random Forest, SVC, Naive Bayes, KNN, XGBoost
- **Evaluation:** confusion matrices, accuracy, precision, recall, F1, and ROC-AUC, validated with k-fold cross-validation
- **Interpretation:** feature-importance analysis for Random Forest, Decision Tree, XGBoost, and Logistic Regression

## Repository Structure

    Heart_Project_Code.ipynb   # full pipeline: EDA → cleaning → modeling → evaluation
    requirements.txt
    README.md


> **Data:** the combined heart dataset (`heart_statlog_cleveland_hungary_final.csv`) is publicly available on Kaggle.

## License

Released under the MIT License — see [LICENSE](LICENSE).
