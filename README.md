# Regression study: Implementing Feature Selection & Dimensionality Reduction

Applying Feature Selection and Dimensionality Reduction transformations to map the difference in prediction accuracy on the California housing Dataset, in order to find the best fitting method with minimum computational costs. 

## Result Summary

| *Method*  *(no. of features)*         | *R2 Score*    | *MSE*        |
| ------------------------------------- | ------------- | ------------ |
| Mutual Information Regression     (3) | 0.5720        | 0.5607       |
| f_test Regression                 (6) | 0.5749        | 0.5012       |
| Pearson's Correlation             (5) | 0.5813        | 0.5485       |
| Recursive Feature Elimination     (5) | 0.5811        | 0.5489       |
| Select From Model                 (2) | 0.4940        | 0.6629       |
| Sequential Feature Selection fwd  (4) | 0.5088        | 0.6435       |
| Sequential Feature Selection bkwd (4) | 0.5810        | 0.5489       |
| Intrinsic L1 Regularization       (8) | 0.2841        | 0.9380       |
| Principal Component Analysis LR   (8) | 0.5757        | 0.5558       |
| Principal Component Analysis RFR  (8) | 0.7615        | 0.3124       |   

- The best scores (R² = 0.76, MSE = 0.31) were observed with the Random Forest Regressor trained on 8 features transformed with PCA.
- Considering computational efficiency, accuracy with Linear Regression was maximum (R² = 0.58, MSE = 0.55) when trained on the top 4 features obtained with SFS (direction = "backward", estimator = RidgeCV).
- Using Pearson' Correlation to drop collinear features provided similar results, where Linear Regressor trained on 5 features provided (R² = 0.58, MSE = 0.55).

![Identifying Feature Multicollinearity using Pearson's Correlation](https://github.com/2gitankit/California-housing/blob/main/Pearson's%20Correlation%20heatmap.png)

## Table of Contents
1. [Introduction](#introduction)
2. [Dataset](#dataset)
3. [Preprocessing](#preprocessing)
4. [Feature Selection](#feature-selection)
5. [Model Training](#model-training)
6. [Evaluation](#evaluation)
7. [Conclusion](#conclusion)
8. [Libraries](#libraries)
9. [Acknowledgements](#acknowledgements)

## Introduction
The goal of this project is to apply feature selection methods to enhance the performance of regression models on the California Housing dataset. Feature selection helps in reducing the dimensionality of the data, improving model performance, and reducing overfitting.

## Dataset
The California Housing dataset is used in this project, which includes features such as median income, house age, average rooms, and more, along with the target variable being the median house value.

- `Dataset`: California Housing Dataset (view below for more details)
- `Models`: [Linear Regressor](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html) [Random Forest Regressor](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html)
- `Input`: 8 features 
- `Output`:  Median house Value 

## Preprocessing
Data preprocessing steps include:
- Handling missing values
- Encoding categorical variables
- Normalizing/Standardizing numerical features

## Feature Selection
Different feature selection techniques are explored, including:
- **Univariate Selection**: SelectPercentile and SelectKBest based on **Mutual Information**, **f Test**.
- **Multicollinearity** reduction using Pearson Correlation. 
- **Recursive Feature Elimination**, **SelectFromModel** and **Sequential Feature Selector**: Using Lasso & Ridge regressors as estimators.
- **PCA (Principal Component Analysis)**: To test and reduce dimensionality.

## Model Training
Regression models are trained using the selected features. The models used may include:
- Linear Regression
- Random Forests
- RidgeCV
- Lasso

## Evaluation
Model performance is evaluated using metrics such as R-squared (R²) score and Mean Squared error. The R² score indicates how well the model's predictions match the actual data.

## Conclusion
The best scores obtained from the feature selection methods and model training is:

- **Best R² Score**: `0.7615`
- **Least MSE**: `0.3124`
- **Model**: `Random Forest Regressor`
- **Selector**: `PCA`
- **n_components**: `8`

This score reflects the proportion of variance in the target variable that is predictable from the selected features.


## Libraries 

**Language:** ![Python](https://img.shields.io/badge/-Python-43B02A?style=flat&logo=python&logoColor=white)

**Packages:** ![Scikit-Learn](https://img.shields.io/badge/-Scikit%20Learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/-Matplotlib-F05032?style=flat&logo=matplotlib&logoColor=white)
![Seaborn](https://img.shields.io/badge/-Seaborn-3776AB?style=flat&logo=seaborn&logoColor=white)
![Pandas](https://img.shields.io/badge/-Pandas-150458?style=flat&logo=pandas&logoColor=white)

## Acknowledgements

Below references can be used for further exploration: 

 - [California housing dataset - Github](https://inria.github.io/scikit-learn-mooc/python_scripts/datasets_california_housing.html)
 - [Sklearn modules](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.fetch_california_housing.html)
 - [Linear regression on california housing - kaggle](https://www.kaggle.com/code/minamichael/linear-regression-model-in-california-housing-data)
