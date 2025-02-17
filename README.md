# QRT2020
QRT Data Challenge ENS 2020 - Stock Return Prediction
This repository contains the solution approach to the QRT Data Challenge ENS 2020. The solution is divided into three main notebooks: data preprocessing, feature selection, and model tuning.

## Notebooks

### 1. Data Preprocessing

This notebook is the base for:
- Data cleaning
- Data Imputation
- Feature Engineering

#### Main Tasks
- **Load train and test data**: The train and test datasets are loaded with 46 features each.
- **Drop rows with no observed returns**: All rows with no observed returns over the past 5 days are removed to clean the dataset.
- **Impute missing values**: Missing values in `RET_x` and `VOLUME_x` columns are imputed using the median to handle incomplete data.
- **Generate new features**: New features are created based on statistical aggregations and transformations to enhance the dataset for better model performance.

### 2. Data Features Selection

This notebook is the base for feature selection.

#### Main Tasks
- **Load data**: Load the train and test cleaned and extended datasets (from Data Preprocessing part).
- **Remove highly correlated features**: Identify and remove features that are highly correlated to reduce redundancy.
- **Feature selection through models**: Use models like RandomForest and XGBoost to select important features based on their importance scores.
- **Feature selection through statistics**: ANOVA F-value (f_classif), Estimate mutual information (mutual_info_classif) for a discrete target variable
- **Other Feature selection Advanced Methods** : Feature ranking with recursive feature elimination (RFE, RFECV), SequentialFeatureSelector (forward/backward)
- **Save selected features**: Save the selected features to CSV files for further use.

### 3. Model Tuning

This notebook shows my approach to optimize the hyperparameters and the machine learning models used to predict the target.

#### Main Tasks
- **Load data**: Load the train and test datasets. Loading differents selection of features made in the Data Features Selection part.
- **Define ML pipeline**: Create a machine learning pipeline that includes steps for feature selection and classification.
- **GridSearchCV for model comparison**: Use GridSearchCV to compare the performance of different imputation methods and feature selections.
- **Tune hyperparameters**: Tune hyperparameters for models like Random Forest and CatBoost to optimize their performance.
- **Evaluate model performance**: Evaluate the model performance using cross-validation and select the best model.

## Getting Started

To get started with the notebooks, ensure you have the required libraries installed. You can use the provided `requirements.txt` file to install them.

```bash
pip install -r requirements.txt
