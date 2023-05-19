# Module 20 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.

* Explain what financial information the data was on, and what you needed to predict.

----------------------------------------------------------------------

    The purpose of this analysis is to see if there is a correlation that can be found between the features of a loan and whether or not the loan will default to help create a model to predict loan behavior moving forward. 

    The features of the loan data include: 
        - loan size
        - interest rate
        - borrower income
        - debt to income
        - number of accounts
        - derogatory marks
        - total debt

    This is then compared to the loan status:
        - Goodstanding
        - Defaulted

    All of the data points are numerical. 

1. Read in the data through the lending_data.csv file. 
2. Seperate the data into the target labels (y) and the features (X).
3. There is a total value_count of 77536 loans. The majority of the loans are in goodstanding. 75036 loans are in goodstanding. 2500 loans are in default. 
4. Seperate the data into training and testing data. 
5. Create a logistic regression model with the training data. 
6. Save the prediction data with the actual loan status data labels. 
7. Accuracy score between the target data (y), and the predictions to determine how accurate the model fits the data. 
8. Random oversampling is then applied. This allows for randomly selected samples to be picked from the minority class, and added to the training data set. This means data from high risk loans would be added to the training data. 
9. A logistical regression is then run on this oversampled data to predict the outcome of the loan in comparison to the actual loan status in the testing data. 

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

---------------------------------------------------------------------

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.
---------------------------
Accuracy:
0.9924164259182832

Confusion Matrix:
[[18679    80]
 [   67   558]]

Precision and Recall Scores:
              precision    recall  f1-score   support

           0       1.00      1.00      1.00     18759
           1       0.87      0.89      0.88       625

    accuracy                           0.99     19384
   macro avg       0.94      0.94      0.94     19384
weighted avg       0.99      0.99      0.99     19384

This model is 99.2% accurate in predicting the loan status based on features of the loan. The data does a better job of predicting good loans than it does predicting bad loans. It has a 100% accuracy on the good loans, and a 87% accuracy on the bad loans. In the confusion matrix, there is more confusion with false negatives than there was false positives in terms of rate of accuracy. 


* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
---------------------------
Accuracy:
0.9945026387334079

Confusion Matrix:
[[74614   422]
 [  403 74633]]

Precision and Recall Scores:
              precision    recall  f1-score   support

           0       0.99      0.99      0.99     75036
           1       0.99      0.99      0.99     75036

    accuracy                           0.99    150072
   macro avg       0.99      0.99      0.99    150072
weighted avg       0.99      0.99      0.99    150072

The accuracy score of the resampled data went up only slightly to 99.4%. The resampled data has a higher false positive and false negative number. However, the data has a 99% accuracy rate for both healthy loans and high risk loans with the resampled data. 

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.

----------------------------------------------------------------------

The two models both have pros and cons to them. The first machine learning model does a better job of predicting the good loans with an almost 100% precision and recall. However, this isn't the loan that is important to predict. It is more important to predict the loans with 1. These are the high risk loans. The second machine learning model is the best option for predicting high risk loans. Therefore, the second model is more beneficial to the question and problem we are trying to answer than the first machine learning model. Overall, the second model has a 99% precision and recall on both good loans and high risk loans, whereas the the first model only predicts one group of loans well. 
