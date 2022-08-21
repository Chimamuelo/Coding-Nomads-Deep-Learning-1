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

The different methods used to handle that can be found on the respective notebooks.

## Methods

In order to train the ml models, the given data was splitted using this sklearn method [sklearn](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.train_test_split.html). At the end a 90% was used for training and 10% for validation.

### Feature engineering Titanic: 
Before feeding the neural network, all the categorical variables were transformed into one hot vectors.
For missing entries the fill method used was the replacing them with the most common value of that column (mode).
The model trained were Random forest and XgboostClassifier and a simple neural network.

A grid search was implemented to find the best params for the random forest,
Not much hyperparameters were tuned in the Xgboost model.

Optimizer and loss function.
The optimizer selected was Adam since it is the most common one.
Loss function: Binary crossentropy loss: The loss selected was based on the fact that the target variable is a binary value so based on the input it will output either a 1 or 0 by using the sigmoid activation function. [BCE](https://pytorch.org/docs/stable/generated/torch.nn.BCEWithLogitsLoss.html)

Metrics: The metric selected was F1 score, the reason to use that one is because in a bianry classifier is important to know how many entries were missclassified (combining precision and recall). Also for visual purposes a confusion matrix is displayed at the end of the titanic notebook.

Results:
- Random forest F1_score:0.810126582278481 
- Xgboost: F1_score:0.8157894736842105
- Neural network:  0.7251

These results are as expected since neural networks should not be the first option while dealing with tabular data.
Neural networks should be used in problems that required unstructured data such as images or text.

### House Price Methods
In this notebook fast ai was used to train a regressor model.
See the notebook to see the details, but the architecture of the model was based on the fas ai tutorials [Fastai](https://docs.fast.ai/44_tutorial.tabular.html)

But as the previous titanic model, the results were not better than using traditional ml approaches in sklearn.


