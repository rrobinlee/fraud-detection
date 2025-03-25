# Identifying and Predicting Fraudulent Transactions in Financial Payment Service Data

March 13, 2025 

Felix van Kleef, Kelechi Isiugo, Robin Lee, Sebastian Rivera

<br>

**Data:** 

https://www.kaggle.com/datasets/arunavakrchakraborty/financial-payment-services-fraud-data

**Context:** 

Develop a classifier for predicting fraudulent transactions for a financial company and use insights from the model to develop an actionable plan. Data for the case is available in CSV format having 6362620 rows and 11 columns.


<br>

## Modeling Framework

We are leveraging simulated financial payment services data to build a predictive model capable of identifying fraudulent transactions.  Our methodology will encompass two key phases: conducting a comprehensive exploratory data analysis and feature engineering to uncover transaction patterns and anomalies, followed by implementing and evaluating a suite of machine learning algorithms to develop an accurate classification model.

The workflow details how we handle the highly imbalanced dataset where fraud cases are less than 1% of the total data. The dataset is processed using three different strategies to balance fraud and non-fraud cases before training machine learning models:

1. Undersampling Non-Fraud:
   * The non-fraudulent cases are reduced to increase the fraud rate to approximately 33%.
   * The data is split into training and testing sets.
   * Models are trained and validated on a separate dataset with the original fraud rate (<1%).
   
2. Oversampling using SMOTE:
   * Synthetic Minority Over-sampling Technique (SMOTE) is used to increase fraud cases, raising the fraud rate to about 50%.
   * Data is split into training and testing sets.
   * Models are trained and validated on a dataset with the original fraud rate (<1%).
   
3. Class Weight Adjustment on Complete Data:
   * The entire dataset is used without resampling, but class weights are adjusted to balance fraud cases during model training.
   * Data is split into training and testing sets.
   * Models are trained and validated on a dataset with the original fraud rate (<1%).
  
![image](https://github.com/user-attachments/assets/7fa87a8d-8526-4dd3-9e1f-050b12c56392)

For each type of sampling, we implement the following Supervised Machine Learning methods for classification:

1. **Logistic Regression**
2. **Tree-Based Models**
   * Random Forest
   * Gradient Boosting
   * Bagging Classifier
   * XGBoost
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

<mark>We relied most on AUC-PR to evaluate each model.</mark> 

* AUC-PR focuses only on Precision (how many predicted frauds are actually frauds) and Recall (how many actual frauds were correctly detected).
* The Precision-Recall curve better captures performance when false positives and false negatives matter more than true negatives.

## Key Takeaways

* Models struggled with the imbalanced data (fraud rate <1%).
* Undersampling and oversampling improved performance in the supervised ML Models, but not significantly.
* <mark>XGBoost performed best on the oversampled data, and One-Class SVM was the best anomaly detection model.</mark>

### Validation Metrics for Undersampled Data

![image](https://github.com/user-attachments/assets/4d30ffa8-ec10-4f2f-a43a-2cdd1c8c70f0)

### <mark>Validation Metrics for Oversampled Data using SMOTE</mark>

![image](https://github.com/user-attachments/assets/c8e70583-6bd4-4ce0-9b29-d5041c063e16)

### Validation Metrics for Class-Weighted Data

![image](https://github.com/user-attachments/assets/7725fdb6-45b3-4dbb-b9d1-c3b02d8ae641)


