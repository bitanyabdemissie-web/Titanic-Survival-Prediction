# Titanic-Survival-Prediction
Exploratory data analysis, feature engineering, and comparative supervised machine learning for Titanic passenger survival prediction.
# Titanic Survival Prediction

## Overview

This project explores the factors that influenced passenger survival during the Titanic disaster using exploratory data analysis (EDA) and supervised machine learning.

The objective is to investigate patterns in passenger characteristics, perform feature engineering, and compare multiple classification algorithms to understand their performance on the survival prediction task.

## Objectives

- Perform exploratory data analysis to identify patterns and relationships in the dataset.
- Investigate the relationship between passenger characteristics and survival.
- Apply feature engineering to extract additional information from existing features.
- Develop and compare multiple supervised machine learning models.
- Apply hyperparameter tuning and cross-validation to improve model performance.

## Dataset

The project uses the Titanic dataset from the Kaggle Titanic competition.

The dataset contains passenger information, including:

- Passenger class
- Sex
- Age
- Number of siblings and spouses aboard
- Number of parents and children aboard
- Ticket information
- Fare
- Cabin
- Port of embarkation

The training dataset contains survival labels, while the competition test dataset does not.

**Dataset source:** [Kaggle – Titanic: Machine Learning from Disaster](https://www.kaggle.com/competitions/titanic)

## Technologies and Libraries

| Technology | Purpose |
|---|---|
| Python | Programming language |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical computations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Scikit-learn | Preprocessing, model development, and evaluation |
| XGBoost | Gradient boosting classification |
| Jupyter Notebook | Interactive analysis |

## Methodology

### 1. Exploratory Data Analysis

Investigated the dataset to understand passenger characteristics and identify patterns associated with survival.

Analysis included:
- Survival distribution.
- Survival rates by passenger class and gender.
- Age and fare distributions.
- Family size and survival relationships.
- Missing values and feature distributions.

### 2. Feature Engineering

Created additional features to capture information that was not directly represented by the original dataset.

Examples include:
- Family size.
- Family size categories.
- Passenger titles extracted from names.
- Name length.
- Age categories.
- Ticket-related features.
- Cabin assignment indicators.

### 3. Data Preprocessing

Prepared the dataset for machine learning through:
- Missing-value imputation.
- Categorical feature encoding.
- Numerical and categorical feature transformation.
- Feature preparation for model training.

### 4. Model Development

Implemented and compared several supervised classification algorithms:

-
