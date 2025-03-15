# Identifying and Predicting Fraudulent Transactions in Financial Payment Service Data

We are leveraging simulated financial payment services data to build a predictive model capable of identifying fraudulent transactions.  Our methodology will encompass two key phases: conducting a comprehensive exploratory data analysis and feature engineering to uncover transaction patterns and anomalies, followed by implementing and evaluating a suite of machine learning algorithms to develop an accurate classification model.

![image](https://github.com/user-attachments/assets/7fa87a8d-8526-4dd3-9e1f-050b12c56392)

## Model Information:

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

We ultimately relied most on AUC-PR to evaluate each model.

**Key Takeaways:**

* Models struggled with the imbalanced data (fraud rate <1%).
* Undersampling and oversampling improved performance in the supervised ML Models, but not significantly.
* XGBoost performed best on the oversampled data, and One-Class SVM was the best anomaly detection model.
