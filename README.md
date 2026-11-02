# Titanic Survival Prediction

### Exploratory Data Analysis, Feature Engineering, and Classification Model Evaluation

## Project Overview

This project investigates passenger survival in the Kaggle Titanic dataset through exploratory data analysis and supervised machine learning.

The analysis examines passenger characteristics, explores relationships between features and survival outcomes, and compares multiple classification algorithms using a structured model-selection workflow.

The objective is to develop a reproducible analytical comparison rather than optimize for a competition leaderboard.

## Objectives

- Perform exploratory data analysis to understand the dataset and identify survival patterns.
- Investigate relationships between passenger characteristics and survival.
- Apply feature engineering to extract additional information from existing variables.
- Develop and compare multiple supervised machine learning classifiers.
- Apply stratified cross-validation and hyperparameter optimization.
- Evaluate the selected model using an independent test partition.

## Dataset

The project uses the labelled passenger dataset from the [Kaggle Titanic Competition](https://www.kaggle.com/competitions/titanic).

The dataset contains passenger information, including:

- Passenger class
- Sex and age
- Family relationships aboard the ship
- Ticket and fare information
- Cabin information
- Port of embarkation

The labelled `train.csv` file is used for exploratory analysis, model development, and evaluation.

The competition's unlabelled `test.csv` is not used for model evaluation because it does not contain ground-truth survival labels.

## Technologies and Libraries

| Technology | Purpose |
|---|---|
| Python | Programming language |
| NumPy | Numerical computations |
| Pandas | Data manipulation and analysis |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Scikit-learn | Preprocessing, model development, and evaluation |
| Jupyter Notebook | Interactive analysis |

## Methodology

### 1. Exploratory Data Analysis

Examined the dataset structure, data types, descriptive statistics, missing values, and survival distribution.

Explored survival patterns across:
- Gender
- Passenger class
- Age
- Fare
- Family composition

### 2. Feature Engineering

Developed additional passenger-level features to capture information from the original variables.

| Feature | Description |
|---|---|
| `Family_Size` | Total family size, including the passenger |
| `Is_Alone` | Indicates whether the passenger travelled alone |
| `Title` | Title extracted from the passenger's name |
| `Name_Length` | Number of characters in the passenger's name |
| `Cabin_Deck` | First character of the recorded cabin |
| `Cabin_Known` | Indicates whether cabin information was available |
| `Ticket_Prefix` | Normalized ticket prefix |

### 3. Data Preprocessing

Applied preprocessing through Scikit-learn pipelines.

- Numerical missing-value imputation using the median.
- Numerical feature scaling using StandardScaler.
- Categorical missing-value imputation using the most frequent category.
- Categorical feature encoding using OneHotEncoder.

Preprocessing is fitted within the model pipelines to prevent information leakage during cross-validation.

### 4. Data Partitioning

The labelled dataset is divided into three stratified partitions:

| Partition | Percentage | Purpose |
|---|---:|---|
| Training | 60% | Model training and hyperparameter tuning |
| Validation | 20% | Model comparison and selection |
| Test | 20% | Final performance evaluation |

A fixed random seed of 42 is used to support reproducibility.

### 5. Model Development

Six supervised classification algorithms are implemented and compared:

1. Logistic Regression
2. Decision Tree
3. Random Forest
4. Support Vector Machine (SVM)
5. K-Nearest Neighbors (KNN)
6. Gaussian Naive Bayes

These models represent different classification approaches, including linear, tree-based, distance-based, margin-based, and probabilistic methods.

### 6. Hyperparameter Optimization

GridSearchCV is used to identify suitable hyperparameter configurations for each classifier.

The optimization process uses:

- Stratified 5-Fold Cross-Validation.
- ROC-AUC as the primary optimization metric.
- Model-specific hyperparameter grids.

All preprocessing operations are included within the cross-validation pipelines.

### 7. Model Comparison and Evaluation

Tuned models are evaluated on the same validation partition.

The final candidate is selected using the highest validation ROC-AUC.

The selected model is subsequently evaluated on the held-out test partition using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Confusion Matrix

The test partition is reserved for final evaluation and is not used for model selection or hyperparameter tuning.

## Repository Structure

```text
Titanic-Survival-Prediction/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   └── titanic_survival_analysis.ipynb
│
└── data/
    └── raw/
        └── train.csv
```

The dataset is supplied separately and is not committed to the repository.

## Installation and Usage

### 1. Clone the repository

```bash
git clone https://github.com/bitanyabdemissie-web/Titanic-Survival-Prediction.git
```

### 2. Navigate to the project directory

```bash
cd Titanic-Survival-Prediction
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Download the dataset

Download `train.csv` from the [Kaggle Titanic Competition](https://www.kaggle.com/competitions/titanic/data).

Place the file inside:

```text
data/raw/train.csv
```

The notebook also searches several conventional dataset locations. Update the configured data path if necessary.

### 5. Run the notebook

Open the notebook using Jupyter:

```bash
jupyter notebook
```

Navigate to `notebooks/titanic_survival_analysis.ipynb` and execute the cells.

## Reproducibility

The notebook incorporates several measures to support reproducibility:

- Fixed random seed (`42`).
- Stratified training, validation, and test partitions.
- Stratified five-fold cross-validation.
- Pipeline-based preprocessing.
- Separation of model selection and final test evaluation.

Results may vary slightly across software versions and execution environments.

## Limitations and Future Improvements

- The dataset is a historical passenger sample and is not representative of a contemporary population.
- Exploratory relationships are descriptive and do not establish causation.
- Passengers sharing family or ticket information may appear across different data partitions.
- Further experiments could investigate group-aware validation and more advanced feature engineering.
- Additional model configurations and feature selection techniques could be explored.

## Project Status

**Initial implementation completed.**

The project establishes a reproducible baseline for exploratory analysis, feature engineering, and comparative classification. Further experimentation and improvements are planned.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
