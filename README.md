# Identifying and Predicting Fraudulent Transactions in Financial Payment Service Data

We are leveraging simulated financial payment services data to build a predictive model capable of identifying fraudulent transactions.  Our methodology will encompass two key phases: conducting a comprehensive exploratory data analysis and feature engineering to uncover transaction patterns and anomalies, followed by implementing and evaluating a suite of machine learning algorithms to develop an accurate classification model.

## Resampling for Modeling Framework

![image](https://github.com/user-attachments/assets/7fa87a8d-8526-4dd3-9e1f-050b12c56392)

## Model Implementation Summary

For each type of sampling, we implemented the following Supervised Machine Learning methods for classification:

* Logistic Regression
* Tree-Based Models (Random Forest, Gradient Boosting, Bagging Classifier, XGBoost)
* Anomaly Detection Models (Autoencoder and One-Class Support Vector Machine)

Each model was evaluated using the following metrics on the Training, Testing, and Validation Datasets:

* Accuracy
* Precision
* Area Under the Curve (AUC)
* Recall
* **Area Under the Curve - Precision Recall (AUC-PR)**
* Specificity
* F1-Score

We ultimately relied most on AUC-PR to evaluate each model, because we want to minimize excessive false positives (which is impractical in real-world fraud detection systems)

## Key Takeaways

* Models struggled with the imbalanced data (fraud rate <1%).
* Undersampling and oversampling improved performance in the supervised ML Models, but not significantly.
* XGBoost performed best on the oversampled data, and One-Class SVM was the best anomaly detection model.

### Validation Metrics for Undersampled Data

![image](https://github.com/user-attachments/assets/bf591828-1b7f-4219-9840-79c05844c122)
![image](https://github.com/user-attachments/assets/4d30ffa8-ec10-4f2f-a43a-2cdd1c8c70f0)

### Validation Metrics for Oversampled Data using SMOTE

![image](https://github.com/user-attachments/assets/ddbcfc7d-0060-4866-bdf1-6a8035a3a7df)
![image](https://github.com/user-attachments/assets/c8e70583-6bd4-4ce0-9b29-d5041c063e16)

### Validation Metrics for Class-Weighted Data

![image](https://github.com/user-attachments/assets/ca26465b-85e5-423a-9c7f-b6827d58074e)
![image](https://github.com/user-attachments/assets/7725fdb6-45b3-4dbb-b9d1-c3b02d8ae641)


