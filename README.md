# Cerdit Risk Analysis

This project uses various resampling techniques in coordination with logistic regression in order to create models for predicting the risk of loan applicants.

### Summary
Type of Resampling Techniques used to check the accuracy of model：
Oversampling
SMOTE Oversampling
Unsersampling
Combination (Over and Under) Sampling

We have used LoanStats_2019Q1.csv file for data sampling. Cleaned the data, used 'loan_sample' as y (target) and rest as X. Then trained model on X and y and then used different types of sampling techniques to findout accuracy, cofusion matrix and generate classification report.

#### Oversampling
Using RandomOverSampler from imlearn we resampled the data to match class of less sample data with class of more sample data. According to summary precision is very low (0.01) for high_risk and high (1.00) for low_risk. Recalls are high for high_risk loans that is 0.71 and low for low_risk loans 0.56.

#### SMOTE Oversampling
The SMOTE is increated size of minority is increaed by interpolating new instances. By using this technique model accuracy is 0.66. According to summary precision is very low (0.01) for high_risk and high (1.00) for low_risk, which is same as Oversampling. Difference between Recalls hish_risk and low_risk samples are not much, high_risk is 0.63 and low_righ is 0.68.

#### UnderSampling
In Undersampling instead of increasing the number of the minority class, the size of the majority class is decreased. Original: Counter({'low_risk': 51366, 'high_risk': 246}), After Undersampling Counter({'high_risk': 246, 'low_risk': 246}). By using this technique model accuracy is 0.54. According to summary precision is very low (0.01) for high_risk and high (1.00) for low_risk. Recall for high_risk data samples 0.67 and for low_risk its 0.42 low. f1 score is also very bad 0.01

#### Combination ()
SMOTEENN combines the SMOTE and Edited Nearest Neighbors (ENN) algorithms. First it oversample the minority class with SMOTE, second clean the resulting data with an undersampling strategy. By using this technique model accuracy is 0.64. According to summary precision is very low (0.01) for high_risk and high (1.00) for low_risk. Recalls for high_risk (0.71) higher than low_risk (0.57). f1 score is still bad 0.02 high_risk and good for 0.73 low_risk.

### Summary And Analysis
By looking at the summary for all sampling techniques none of the sampling technique looks clearly better than other. All of them almost equal. Since Accuracy is little bit more for Oversampling model technique. So we can go with Oversamping model technique.

