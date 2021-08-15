# Credit_Risk_Analysis


## Overview 
The purpose of this analysis is to generate a predictive model of credit risk using historical loan data. Because credit risk is inherently an unbalanced classification problem (low risk loans greatly outnumber high risk loans), we need to employ various resampling methods and various machine learning concepts in order to find the optimal predictive model. 

## Results 
Below are the balanced accuracy scores, precision scores, and recall scores for each machine learning model employed. 

### Logistic Regression + Naive Random Oversampling
* Balanced Accuracy Score: 0.655
* Precision Score (High Risk): 0.01
* Recall Score (High Risk): 0.71
### Logistic Reression + SMOTE Oversampling
* Balanced Accuracy Score: 0.655
* Precision Score (High Risk): 0.01 
* Recall Score (High Risk): 0.62
### Logistic Regression + Cluster Centroids Undersampling
* Balanced Accuracy Score: 0.547
* Precision Score (High Risk): 0.01 
* Recall Score (High Risk): 0.68
### Logistic Regression + Combination Over/Under Sampling (SMOTEENN)
* Balanced Accuracy Score: 0.664
* Precision Score (High Risk): 0.01 
* Recall Score (High Risk): 0.76
### Balanced Random Forest Classifier
* Balanced Accuracy Score: 0.788
* Precision Score (High Risk): 0.03
* Recall Score (High Risk): 0.70
### Easy Ensemble AdaBoost Classifier
* Balanced Accuracy Score: 0.931
* Precision Score (High Risk): 0.09 
* Recall Score (High Risk): 0.92

## Summary 
Looking over the results, it's clear that precision is one of the big issues with this unbalanced dataset. Because low risk loans outnumber high risk loans by such a wide margin, the model ends up being really good at finding and evaluating low risk loans, but not so good at finding the high risk loans (which is our target). Despite all models having an overall precision score of 0.99, none of the model's High Risk precison scores made it above 0.1. The high number of false positives for high risk loans must be deflating the precision score. That being said, the random forest/ensemble models did exemplify slightly higher precision than the logistic regressions. 

There was a wider distrobution in recall scores between the models. despite low precision scores across the board, all of the models do a better job of at least correctly idenifying the truely high risk loans as high risk. All of the models have recall scores >.60, meaning at least 60% of the high risk loans were correctly identified in each model. The only issue is, all of these models have a ton of false positives identified as high risk as well, given their low precision scores. Still, this is valueable because at least the models can flag the loans that are possibly high risk, allowing the user to review a more targeted list of loans. 

There is still, however, a very clear winner based on the results, and that is the Easy Ensemble AdaBoost Classifier. This model has the highest precision score of high risk loans at 0.09, as well as a VERY high recall score of 0.92. This model can correctly identify ~92% of high risk loans in the data set. It also is the most precise of the models, with the fewest perentage of false positives. While close to 9 out of the 10 loans this model will flag as "hgih risk" will actually be low risk, not a lot of high risk loans are slipping through the cracks. The balanced accuracy score also gives the AdaBoost model a score of 0.93, by far the highest of the group. 


