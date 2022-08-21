# CodingNomads Deep Learning Project 1: Fundamentals
## Problem statement
Two datasets are used for learning purposes on this repository: Titanic dataset to understand the basics of pytorch and neural networks and House Prices to understand how to use fast ai.
The objective of the titanic dataset is to determine if some passangers survided or not given different features such as class, number of partners in the ship, etc.
The objective of the House Price dataset is to determine the price of houses given general information such as location, size, etc (More of the datasets in Data folder).

## Data
### Titanic dataset
The original dataset can be found at: [Kaggle](https://www.kaggle.com/competitions/titanic/data)
It consist on a practice dataset to study and get comfortable applying ml algorithms. The data has 9 features and a target.
The features are divided as follows:
survival: Target variable, Binary output (1 or 0)

Continuous features:
- Age
- Fare
- Cabin
- -Ticket number
- pach
- sibsp

Categorical feature:
- Pclass (Ordinal feature)
- Sex
- embarked

The dataset was relatively simple.Some feature engineering was required to handle the categorical data, some entries were missing but the process to leave the data ready for a model was not complicated.

### House Price dataset
This dataset can be found at: [Kaggle](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data?select=train.csv)
This dataset is more complex since it has more features (categorical and continuous).
A detailed explanaion can be found in the data_description.txt file at the data section of this repository.
The data required a lot of feature engineering. Missing entries and some columns highly imbalanced were found.


