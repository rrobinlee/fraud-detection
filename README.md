# Identifying and Predicting Fraudulent Transactions in Financial Payment Service Data

March 13, 2025 

Felix van Kleef, Kelechi Isiugo, Robin Lee, Sebastian Rivera

<br>

**Data:** 

https://www.kaggle.com/datasets/arunavakrchakraborty/financial-payment-services-fraud-data

**Context:** 

Develop a classifier for predicting fraudulent transactions for a financial company and use insights from the model to develop an actionable plan. Data for the case is available in CSV format having 6362620 rows and 11 columns.

**Handling Imbalanced Data:**

The workflow details how we handle the highly imbalanced dataset where fraud cases are less than 1% of the total data. The dataset is processed using three different strategies to balance fraud and non-fraud cases before training machine learning models:

|Undersampling Non-Fraud|Oversampling using SMOTE|Balanced Class Weight Adjustment|
|:-|:-|:-|
|The non-fraudulent cases are reduced to increase the fraud rate to approximately 33%.|Synthetic Minority Over-sampling Technique (SMOTE) is used to increase fraud cases, raising the fraud rate to about 50%.|The entire dataset is used without resampling, but class weights are adjusted to balance fraud cases during model training.|

**Model Development:**

For each type of sampling, we implement the following Supervised Machine Learning methods for classification:

1. **Logistic Regression**
2. **Tree-Based Models**
   * Random Forest Classifier
   * Gradient Boosting Classifier
   * Bagging Classifier
   * XGBoost Classifier
3. **Anomaly Detection Models**
   * Autoencoder
   * One-Class Support Vector Machine

Each model is evaluated using the following metrics on the Training, Testing, and Validation Datasets:

* Accuracy
* Precision
* Area Under the Curve (AUC)
* Recall
* <mark>**Area Under the Curve - Precision Recall (AUC-PR)**</mark>
* Specificity
* F1-Score

<mark>We relied mostly on AUC-PR to evaluate each model.</mark> 

* AUC-PR focuses only on Precision (how many predicted frauds are actually frauds) and Recall (how many actual frauds were correctly detected).
* The Precision-Recall curve better captures performance when false positives and false negatives matter more than true negatives.

## Key Takeaways

* Models struggled with the imbalanced data (fraud rate <1%).
* Undersampling and oversampling improved performance in the supervised ML Models, but not significantly.
* <mark>XGBoost performed best on the oversampled data, and One-Class SVM was the best anomaly detection model.</mark>

#### Validation Metrics for Undersampled Data

|All Model Diagnostics|Best Model: Random Forest|
|:-|:-|
|![image](https://github.com/user-attachments/assets/e46025d9-e563-4b15-a625-7303aa9964d5)|![image](https://github.com/user-attachments/assets/6ba58ef8-b5d1-42c5-8fb4-47e806d804ab)|


#### <mark>Validation Metrics for Oversampled Data using SMOTE</mark>

|All Model Diagnostics|Best Model: XGBoost|
|:-|:-|
|![image](https://github.com/user-attachments/assets/25a5678b-be28-4464-bb3e-f6dba49806d3)|![image](https://github.com/user-attachments/assets/b672e131-9354-4260-98fe-a90cef2f1187)|

#### Validation Metrics for Class-Weighted Data

|All Model Diagnostics|Best Model: XGBoost|
|:-|:-|
|![image](https://github.com/user-attachments/assets/112ab953-5389-4090-8266-8558d75607ce)|![image](https://github.com/user-attachments/assets/6798d28a-b25c-4e47-b980-d4bdea0c89cf)|



