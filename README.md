# Module 21 Challenge
# Neural Network Model Report

## Overview of the Analysis
In this challenge, a dataset of more than 34,000 organizations that have received funding from Alphabet Soup over the years, where the dataset includes columns comprised of: 

* (1) EIN and NAME: Identification columns;
* (2) APPLICATION_TYPE: Alphasbet Soup application type;
* (3) AFFILICATION: Affiliated setor of industry;
* (4) CLASSIFICATION: Government organization classification;
* (5) USE_CASE: Use case for funding;
* (6) ORGANIZATION: Organization type;
* (7) STATUS: Active Status;
* (8) INCOME_AMT: Income classification;
* (9) SPECIAL_CONSIDERATIONS: Special considerations for application;
* (10) ASK_AMT: Funding amount requested; and
* (11) IS_SUCCESSFUL: Was the money used effectively.

### Results of the Analysis
After being read into a Pandas DataFrame, the original data provided in a .csv was found to comprise the following features: (1) loan_size, (2) interest_rate, (3) borrower_income, (4) debt_to_income, (5) num_of_accounts, (6) derogatory_marks, (7) total_debt, and (8) loan_status.  loan_status feature is comprised of "0" or "1" indicative of "healthy loans" or "high-risk loans," respectively. The loan_status is defined as a label and it was separated from the other features.  There are 2500 rows in which loan_status feature is "1" indicative of a high-risk loan."

### Goal of this Challenge

The goal of this challenge is to employ the stages of the Machine Learning Process to evaluate the performance of a logistic regression model fitted with (1) this original data and (2) a resampled training data of this original data which will allow a user to predict whether the logistic regression model predicts and identifies loans as being either "healthy" or "high-risk" when fitted with either the original data or the resampled data. 

### Stages of the Machine Learning Process

* Split the Data into Training and Testing Sets
  * Read the lending_data.csv data from the Resources folder into a Pandas DataFrame.
  * Create the labels set (y) from the “loan_status” column, and then create the features (X) DataFrame from the remaining columns.
  * Check the balance of the labels variable (y) by using the value_counts function.
  * Split the data into training and testing datasets by employing the train_test_split module imported from sklearn.model_selection.

* Create a Logistic Regression Model with the Original Data
  * Fit a logistic regression model by using the training data (X_train and y_train) by employing the LogisticRegression module imported from sklearn.linear_model.
  * Save the predictions on the testing data labels by using the testing feature data (X_test) and the fitted model.
  * Evaluate the model’s performance with (1) balanced accuracy, (2) a confusion matrix, and (3) a classification report, where the balanced_accuracy_score, confusion_matrix, and classification_report modules have been imported from sklearn.metrics.
  * Discuss how well the logistic regression model predicted both the 0 (healthy loan) and 1 (high-risk loan) labels as a function of (1) a balanced accuracy score, (2) precision scores, (3) recall scores, and f1-scores.

* Predict a Logistic Regression Model with Resampled Training Data
  * Use the RandomOverSampler module from the imbalanced-learn library to resample the data. It was confirmed that the labels had an equal number of data points.
  * Use the LogisticRegression classifier and the resampled data to fit the model and make predictions.
  * Evaluate the model’s performance with (1) balanced accuracy, (2) a confusion matrix, and (3) a classification report from  the modules imported above
  * Discuss how well the logistic regression model -- fitted with the oversampled data -- predicted both the 0 (healthy loan) and 1 (high-risk loan) labels as a function of (1) a balanced accuracy score, (2) precision scores, (3) recall scores, and f1-scores.


## Results (Scores)

* Machine Learning Model 1 (Original Data):
  * Balanced Accuracy: 95.20%
  * Precision: 100% for "healthy loans"; 85% for "high-risk loans"
  * Recall: 99% for "healthy loans"; 91% for "high-risk loans"

* Machine Learning Model 2 (Resampled Training Data):
  * Balanced Accuracy: 99.37%
  * Precision: 100% for "healthy loans"; 84% for "high-risk loans"
  * Recall: 99% for "healthy loans"; 99% for "high-risk loans"

## Summary

For the logistic regression model fit with the original data, the balanced accuracy score of the model is 95.20%.  The precision scores of healthy and high-risk loans are 100% and 85%, respectively.  The recall scores of healthy and high-risk loans are 99% and 91%, respectively.  The f1-scores of healthy and high-risk loans are 100% and 88%, respectively,

For the logistic regression model fit with the oversampled data, the accuracy score of the model is nearly perfect at 99.37%.  The precision scores of healthy and high-risk loans are 100% and 84%, respectively, the latter being a slight decrease of 1%.  The recall scores of healthy and high-risk loans are 99% and 99%, respectively, the latter being a significant increase of 8%.  The f1-scores of healthy and high-risk loans are 100% and 91%, respectively, the latter being an increase of 3%.

In conclusion, it is recommended that the oversampled data should be employed (i.e., fitted) to logistic regression model for the following reasons:

Firstly, accuracy measures how many of the loans have been classified correctly, and 99.37% of the loans have been classified correctly with the oversampled data which is 4.17% better than using the original data.  

Secondly, precision scores measure how many of the loans of the model were predicted as healthy loans and how many were predicted as high-risk loans; although the use of the original data results with a better predictor of high-risk loans, its precision score is merely 1% better when oversampled data is used.  

Thirdly, recall measures how many of the loans of the model were correctly identified as healthy loans and how many were correctly identified as high-risk loans.  With the oversampled data, 99% of the loans were correctly identified as both healthy loans and high-risk loans.

Lastly, the f1-score is the harmonic mean of precision and recall, and higher f1-scores reflect a better balance between precision and recall.  When comparing the f1-scores with the two types of data, the higher f1-score of 91% for high-risk loans produced by the oversampled data reflects a better balance between the precision and recall scores than the f1-score of 88% produced by the original data. 

