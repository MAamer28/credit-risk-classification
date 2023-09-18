# Credit Risk Classification
Module 20 Challenge

## Overview of the Analysis

The purpose of the analysis done in this project is to determine if a supervised machine learning model can be constructed to predict the creditworthiness of borrowers. 

Using a dataset of historical lending activity from a peer-to-peer lending services company, the model looks at features such as the size of the loan, the interest rate on the loan, the income of the borrower, the debt to income ratio, the number of accounts per borrower, the derogatory marks against the borrower, and the total debt held by the borrower. Each loan in the dataset is then classified as healthy (0) or high-risk (1). In the dataset containing a total of 77536 data points representing individual loans, there were 75,036 healthy loans representing over 96% of the total. Conversely, there were only 2500 loans classified as high-risk.

As per protocols, the dataset was split using a 'train_test_split' function to create a training set to fit the models and a testing set to measure the models' strength. It is important to note that the features were also scaled to account for differences in each feature's raw weight. 

Two algorithms were tested to determine which, if any, would be a suitable model for the project. In the first case, a logistic regression classifier was fitted onto the scaled training data and predictions returned. In the second case, a random forest classifier was fitted on the scaled training data and predictions likewise returned. In both cases, the predictions were compared with the labels in the test group ('y_test'). Classification reports were generated for each model to compare and contrast the effectiveness. 

## Results

* Logistic Regression Model (LRM):
  * The LRM returned an accuracy of 0.99.
  * The LRM returned a precision of 1.00 and a recall of 0.99 for healthy loans.
  * The LRM returned a precision of 0.84 and a recall of 0.98 for high-risk loans.

* Random Forest Model (RFM):
  * The RFM returned an accuracy of 0.99.
  * The RFM returned a precision of 1.00 and a recall of 0.99 for healthy loans.
  * The RFM returned a precision of 0.85 and a recall of 0.90 for high-risk loans.
 
## Summary

Both models displayed excellent accuracy with scores of 0.99 each. Likewise, both models were adept at predicting healthy loans. The difference thus lies in the ability to predict high-risk loans. As such, the LRM offers a more effective option than the RFM due to its higher recall score. 

With models that seek to predict creditworthiness and thus assist in the approval or not of loans to potential borrowers, recall would be a more useful evaluation metric than precision. This is because false negatives, where the model predicts healthy loans for actual high-risk loans, would be more harmful to lending institutions than false positives. While the latter would lead to lost business as a result of classifying healthy loans as risky, the former can lead to more tangible and direct impacts in the form of more frequent defaults and absence of repayment. 

However, the analysis should come with a caveat that the loan status counts in the original dataset skewed heavily in favor of healthy loans. As such, it is likely that both models were not able to learn effectively the correlation between the features and high-risk loans due to the smaller sample set. It would be advisable to retrain the model with more expansive datasets if possible. 

Given the current data, it is thus recommended to use an LRM to assess borrower creditworthiness.
