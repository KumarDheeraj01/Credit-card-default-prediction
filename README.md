# Credit-card-default-prediction
This project mainly focus on the default payments made by customers.
# Problem Description
This project is aimed at predicting the case of customers default payments in Taiwan. From the perspective of risk management, the result of predictive accuracy of the estimated probability of default will be more valuable than the binary result of classification - credible or not credible clients. We can use the K-S chart to evaluate which customers will default on their credit card payments.
# Data Description

# Attribute Information:

### This research employed a binary variable, default payment (Yes = 1, No = 0), as the response variable. This study reviewed the literature and used the following 23 variables as explanatory variables:
* ### X1: Amount of the given credit (NT dollar): it includes both the individual consumer credit and his/her family (supplementary) credit.
* ### X2: Gender (1 = male; 2 = female).
* ### X3: Education (1 = graduate school; 2 = university; 3 = high school; 4 = others).
* ### X4: Marital status (1 = married; 2 = single; 3 = others).
* ### X5: Age (year).
* ### X6 - X11: History of past payment. We tracked the past monthly payment records (from April to September, 2005) as follows: X6 = the repayment status in September, 2005; X7 = the repayment status in August, 2005; . . .;X11 = the repayment status in April, 2005. The measurement scale for the repayment status is: -1 = pay duly; 1 = payment delay for one month; 2 = payment delay for two months; . . .; 8 = payment delay for eight months; 9 = payment delay for nine months and above.
* ### X12-X17: Amount of bill statement (NT dollar). X12 = amount of bill statement in September, 2005; X13 = amount of bill statement in August, 2005; . . .; X17 = amount of bill statement in April, 2005.
* ### X18-X23: Amount of previous payment (NT dollar). X18 = amount paid in September, 2005; X19 = amount paid in August, 2005; . . .;X23 = amount paid in April, 2005.
Steps involved :

The following steps are involved in the project

Exploratory Data Analysis :

After loading and reading the dataset in a notebook, we performed exploratory data analysis. The purpose of exploratory data analysis is to identify the variables that impact payment default next month and the correlations between them. We use graphical data exploratory analysis to check every categorical variable. We plot the graph and visualize the data.

Null values Treatment and Outliers:

Dataset contains no null values to disturb the accuracy.

Numerical and categorical Features:

With the help of exploratory data analysis we analyzed the categorical as well as numerical features in the dataset.

Correlation Analysis :

We plot the heatmap to find the correlation between both the dependent variable and independent variables.

Train test Split :

In the train test split, we take x as dependent variables and y take as an independent variable then train the model.

Models :

We use 3 models to train the data and for predicting the accuracy.

Logistic regression
Random forest
SVC
XG boost
Feature Selection

There are 25 columns in this dataset and the target variable is the column is default payment next month. We drop the column ‘ID’ and target variable and save the rest 23 as predictor features. These predictor variables include categorical variables such as sex, age, education marital status along with numerical variables, such as payment status, credit limit, bill amount, etc.

Imbalance data :

An imbalanced dataset will mislead machine learning algorithms and affect their performances so then we apply train test split to balance data.

Split Training and Test Data:

In the train test split, we take two variables ie X and Y where X contains all the independent variables and Y containsthe dependent variable. Here the independent variable is default payment next month and dependent variables areaffecting the default payment next month like age, gender, credit limit, education, bill payment, etc.For the model, we use the ratio for training and test data split by 80% for training, 20% for the test to ensure consistency. After splitting the data, we set the test data aside and leave it for the very end, which is the final testing after hyperparameter tuning

Performance Metrics:

Since this is a classification problem with imbalanced classes, we use performance metrics i.e. accuracy precision and recall is a better choice. However, there is a known trade-off between precision and recall. We can raise recall to arbitrarily high, but the precision will decrease. We use the below metrics to measure model performances.

a. Confusion matrix b. ROC_AUC c. Precision recall curve

SMOTE Oversampling:

In the initial model fitting, we start by using all models’ default parameters. To compensate for the rare classes in the imbalance dataset, we use SMOTE(Synthetic Minority Over-Sampling Technique) method to oversample the minority class and ensure the sampling is not biased. What this technique does under the hood is simply duplicateexamples from the minority class in the training dataset before fitting a model. after SMOTE sampling, the dataset has an equal size of 0s and 1s. To verify if SMOTE improves models’ performance, all 3 models are trained with SMOTE and without SMOTE. The below table shows the ROC_ AUC scores on training data 9 improved significantly with all models after oversampling with SMOTE. This proves SMOTE is an effective method in sampling imbalanced datasets. Models Training AUC Without SMOTE Training AUC With SMOTE Logistic Regression 0.726 0.797 Random Forest 0.764 0.916 XGBoost 0.762 0.899 Table 1: Model ROC_AUC score on training data with default parameters.
Conclusion: In our dataset, We used many algorithm like Logistic Regression,Support vector classsifier,decision tree classifier,XGBoost Classifier,Random Forest Classifier.Random Forest was the best performing algorithm as shown below
Random Forest Classifier has the best value of accuracy score of 84%
Random Forest Classifier has the best value of precision score of 84%
Random Forest Classifier has the best value of recall score of 83%
Random Forest Classifier has the best value of f1 score of 84%
Random Forest Classifier has the best value of Roc_auc score of 84%
Random Forest Classifier gave the highest importance to Dues then to payment value and then to limit balance columns accordingly
Random Forest Classifier had average fitting time of 1.67 according to cross validate method of sklearn This proves Random Forest Classifier algorithm has perfectly fitted all the dataset.
