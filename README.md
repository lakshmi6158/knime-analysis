<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Titanic Survivors Classification Analysis Using KNIME

## Project Overview

This project presents a comprehensive analysis and classification of Titanic passenger survival using machine learning techniques implemented in the KNIME Analytics Platform. The goal is to predict passenger survival based on various features such as gender, age, passenger class, fare, and family size, and to understand which factors had the most significant influence on survival during the Titanic disaster.

## Dataset

- The dataset contains information on 1,204 passengers aboard the Titanic, acquired from Kaggle.
- Key features include:
    - Demographics: Age, Sex, Passenger Class (Pclass)
    - Ticket and Fare data
    - Family details: Number of siblings/spouses (SibSp), parents/children (Parch), family size (engineered)
    - Additional engineered features, such as Titles extracted from names
- Target variable: *Survived* (0 = No, 1 = Yes)


## Tools and Techniques

- **KNIME Analytics Platform** for data processing, exploration, and modeling
- Machine learning models:
    - Decision Tree Classifier
    - Logistic Regression
- Data preprocessing steps including handling missing values, encoding categorical variables, and feature normalization
- Model evaluation metrics: Accuracy, Precision, Recall, F1-Score, ROC Curve, and AUC
- Cross-validation (k-fold) to assess model robustness
- Feature importance analysis embedded in models


## Key Project Steps

### 1. Data Exploration and Preprocessing

- Loaded and merged passenger ticket and personal data
- Explored data statistics to identify missing values and outliers
- Removed irrelevant or problematic columns such as *Cabin*, *PassengerId*, and *Ticket*
- Imputed missing values:
    - Age missing values filled by random numbers within mean ± std range
    - Embarked missing values replaced with the most common port
- Categorical variables such as *Sex* and *Embarked* were numerically encoded
- Feature engineering:
    - Extracted *Title* from passenger names using regex
    - Created *FamSize* combining siblings/spouses and parents/children counts
- Normalized numerical features to improve model training


### 2. Model Building and Evaluation

- Data split into training (80%) and testing (20%) sets, using stratified sampling to maintain class proportions
- Trained:
    - Decision Tree model, with hyperparameter tuning options
    - Logistic Regression model, with normalization applied for better performance
- Cross-validation applied to Decision Tree model to reduce overfitting
- Evaluated models on multiple metrics with ROC curve analysis


### 3. Results and Insights

| Metric | Decision Tree | Logistic Regression |
| :-- | :-- | :-- |
| Accuracy | ~85.9% | ~86.3% |
| Recall | ~90.1% | ~90.7% |
| Precision | ~87.7% | ~87.8% |
| F1-Score | ~88.9% | ~89.3% |
| AUC (ROC) | 0.824 | 0.902 |

- Logistic Regression slightly outperformed Decision Tree across all metrics.
- The most important predictors identified were:
    - Gender (Sex) — strongest influence on survival
    - Passenger class (Pclass) and fare — higher class/fare had better survival rates
    - Age — younger passengers had higher survival likelihood, especially children under 10
    - Family size — moderate-sized families (up to 4 members) showed higher survival
- Visualized decision tree and ROC curves provided interpretability and model evaluation insights.


## Conclusions

- Survival prediction works well with both logistic regression and decision tree models, with logistic regression showing marginally better performance in this case.
- Gender was the dominant predictive factor, followed by socioeconomic indicators such as fare and passenger class.
- Feature engineering and data preprocessing significantly contributed to model effectiveness.
- The project illustrates a complete machine learning pipeline in KNIME, from raw data handling to model evaluation and interpretation.


## How to Use This Project in KNIME

1. Open KNIME Analytics Platform.
2. Import the provided workflow files.
3. Load the Titanic datasets (`titanic_ticket_data.csv` and `titanic_personal_data.csv`).
4. Follow the workflow steps to preprocess data, engineer features, partition the dataset, train models, and evaluate results.
5. Inspect the nodes for detailed configurations, including data imputation, normalization, and model parameters.
6. Visualize results through the ROC curve and feature importance nodes.

***

This README summarizes the key aspects of the Titanic survival classification project performed using KNIME, providing clarity on the methodology, models, and findings.

<div style="text-align: center">⁂</div>

[^1]: 230140648.pdf

[^2]: Analysis-of-Titanic-Survival-Data.html

