# California Housing

This project focuses on predicting housing prices in California from 1990 census dataset.


## Implementation Details

- `Dataset`: California Housing Dataset (view below for more details)
- `Model`: [Linear Regressor](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html)
- `Input`: 8 features 
- `Output`:  Median house Value 

## Dataset Details

This dataset was obtained from the StatLib repository ([Link](https://www.dcc.fc.up.pt/~ltorgo/Regression/cal_housing.html))

This dataset was derived from the 1990 U.S. census, using one row per census block group. A block group is the smallest geographical unit for which the U.S. Census Bureau publishes sample data (a block group typically has a population of 600 to 3,000 people).

A household is a group of people residing within a home. Since the average number of rooms and bedrooms in this dataset are provided per household, these columns may take surprisingly large values for block groups with few households and many empty houses, such as vacation resorts.

It can be downloaded/loaded using the sklearn.datasets.fetch_california_housing function.

- [California Housing Dataset in Sklearn Documentation](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.fetch_california_housing.html)
- 20640 samples
- 8 Input Features: 
    - MedInc median income in block group
    - HouseAge median house age in block group
    - AveRooms average number of rooms per household
    - AveBedrms average number of bedrooms per household
    - Population block group population
    - AveOccup average number of household members
    - Latitude block group latitude
    - Longitude block group longitude
- Target: Median house value for California districts, expressed in hundreds of thousands of dollars ($100,000)

## Evaluation and Results

| Metric        | Value         |
| ------------- | ------------- |
| R2 Score      | 0.59          |
| MSE           | 0.53          |

The above quant results show that an R-squared value of 0.59 means that approximately 60% of the variability in housing prices can be explained by the features included in the model and an MSE of 0.5326 indicates the average squared difference between the predicted house prices and the actual prices. 

# Key Takeaways

### `High Positive Correlations`

MedInc and target: Typically, a high positive correlation suggests that as the median income increases, the median house value also tends to increase.

AveRooms and Population: This usually indicates that areas with more average rooms per household also have higher populations.

### `High Negative Correlations`

AveBedrms and target: A high negative correlation here might suggest that areas with a higher average number of bedrooms per household tend to have lower house values. 

## How to Run

Template code is provided in the California_Housing.ipynb file.

In a terminal , navigate to the top-level project directory regression-california-housing (that contains this README) and run one of the following commands:

ipython notebook California_Housing.ipynb

or

jupyter notebook California_Housing.ipynb


## Libraries 

**Language:** ![Python](https://img.shields.io/badge/-Python-43B02A?style=flat&logo=python&logoColor=white)

**Packages:** ![Scikit-Learn](https://img.shields.io/badge/-Scikit%20Learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/-Matplotlib-F05032?style=flat&logo=matplotlib&logoColor=white)
![Seaborn](https://img.shields.io/badge/-Seaborn-3776AB?style=flat&logo=seaborn&logoColor=white)
![Pandas](https://img.shields.io/badge/-Pandas-150458?style=flat&logo=pandas&logoColor=white)

# Acknowledgements

Below references can be used for further exploration: 

 - [California housing dataset - Github](https://inria.github.io/scikit-learn-mooc/python_scripts/datasets_california_housing.html)
 - [Sklearn modules](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.fetch_california_housing.html)
 - [Linear regression on california housing - kaggle](https://www.kaggle.com/code/minamichael/linear-regression-model-in-california-housing-data)
