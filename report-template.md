# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
The purpose of this analysis is to create and evaluate the accuracy of a data model that predicts the credity worthiness of potential borrowers from peer-to-peer lending services.

Also, The objective of this analysis is to assess whether the Logistic Regression machine learning model predicts healthy loans versus high-risk loans more accurately when using the original dataset or a resampled dataset designed to augment the size of the minority class.

* Explain what financial information the data was on, and what you needed to predict.
The target financial information in the data is the loan status. The features in the financial data that are used to predict the loan status are loan size, interest rate, borrower income, debt to income ratio, number of accounts, derogatory marks and total debt.

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
For the target values of loan_status there are two variables which I have tried to predict. The first set of variables have a value of '0' (value count of 75036) and these indicate that the loan is healthy. The second set of variables have a value of '1' (value count of 2500) and these mean that the loan has a high risk of defaulting.

* Describe the stages of the machine learning process you went through as part of this analysis.

The machine learning process used to perform the analysis has following stages:

Create label sets and feature Dataframe from the provided dataset.
Split the data into training and testing datasets by using train_test_split.
Create a logistic regression model and fit our original data into the model.
Make predictions on testing data labels by using the testing feature data and the fitted model.
Evaluate the model's performance by calculating accuracy scores, confusion matrix, and classification report.


* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

First method used in this case is the LogisticRegression model on the original fitted data. As the data was highly overweighted towards one of the target variables (healthy loans), so RandomOverSampler was used to reduce the imbalances and LogisticRegression was then applied to the oversampled data.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.
* Balanced Accuracy Score: 95.20% --> this means that when taking into account the sensitivity (recall and/or true positive rate) and specificity (true negative rate) of the model,  the balanced prediction accuracy was 95.2%
* Precision Score: 92% --> This means 92% of predicted positives were correct
* Recall Score: 95% --> this means that the model was 95% precise in measuring true positive values our of all positive predictions made



* Machine Learning Model 1:
* Description of Model 1 Accuracy, Precision, and Recall scores.

This model does a good job in predicting both the healthy and the high-risk loans as can be inferred from the high accuracy score of 99.18% and balanced accuracy score of 95.20%. However, we have to take into consideration that the data is imbalanced as 96.77% of the target values (75036 out of 77536) are for the healthy loans.

This model has a precision score of 100% for the healthy loans and 85% for the high-risk loans. This again can be attributed to the imbalance in the data. The precision scores imply that the healthy loans were classified correctly as positive 100% of the times. However, for the high-risk loans, the classification was correct only 85% of the times.

This model has a recall score of 99% for the healthy loans and 91% for the high-risk loans. The scores imply that for all the instances where the loans were actually healthy, 99% of the times they were classified correctly. However, for all the instances where the loans were actually high-risk, they were classified correctly 91% of the times.


## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

I would recommend using this model to predict the creditworthiness of borrowers, because it has over 95% accuracy in predicting the outcome of the repayment of the initial loan. That accuracy range could be easily molded into a business risk profile to ensure sufficient capital flow for the lenders to remain in business/make a profit.

If you do not recommend any of the models, please justify your reasoning.
