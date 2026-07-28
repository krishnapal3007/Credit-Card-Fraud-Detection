# Credit Card Fraud Detection using Machine Learning

## Project Overview

This project focuses on detecting fraudulent credit card transactions using Machine Learning. The objective is to build a classification model that can identify whether a transaction is **normal or fraudulent**.

A **Random Forest Classifier** was trained and evaluated on a large credit card transaction dataset.

---

## Objectives

* Detect fraudulent credit card transactions.
* Perform data preprocessing and feature engineering.
* Analyze fraud patterns using Exploratory Data Analysis (EDA).
* Train a Machine Learning classification model.
* Evaluate the model using suitable classification metrics.
* Generate fraud predictions for unseen test data.

---

## Dataset

The dataset contains transaction-related information such as:

* Transaction amount
* Merchant
* Transaction category
* Gender
* Location
* City population
* Job
* Transaction time
* Customer age
* Merchant location
* Fraud status

### Dataset Size

| Dataset          |   Records |
| ---------------- | --------: |
| Training Dataset | 1,296,675 |
| Test Dataset     |   555,719 |

The target variable is:

`is_fraud`

Where:

* `0` = Normal transaction
* `1` = Fraudulent transaction

The dataset is highly imbalanced because fraudulent transactions represent a small portion of all transactions.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Joblib
* Jupyter Notebook

---

## Data Preprocessing

The following preprocessing steps were performed:

1. Loaded the training and testing datasets.
2. Removed unnecessary columns.
3. Converted transaction date/time into useful time-based features.
4. Extracted transaction hour, day, month and day of week.
5. Converted date of birth into customer age.
6. Removed high-cardinality features that could create excessive memory usage.
7. Converted categorical variables into numerical features using one-hot encoding.
8. Removed the transaction number because it is an identifier rather than a useful predictive feature.
9. Used a representative sample for model training to manage computational resources.

---

## Exploratory Data Analysis

Several visualizations were created to understand fraud patterns:

### 1. Normal vs Fraud Transactions

A comparison of the number of normal and fraudulent transactions.

### 2. Fraud Transaction Amount Distribution

Analyzed the distribution of transaction amounts among fraudulent transactions.

### 3. Fraud Transactions by Hour

Analyzed how fraudulent transactions vary according to the hour of the day.

### 4. Fraud Transactions by Category

Analyzed which transaction categories contain more fraudulent transactions.

---

## Machine Learning Model

### Random Forest Classifier

The Random Forest algorithm was selected because it:

* Works well for classification problems.
* Can capture non-linear relationships.
* Handles multiple features effectively.
* Provides feature importance information.
* Performs well on structured/tabular data.

The model was trained using a sample of **100,000 transactions** to reduce memory requirements.

---

## Model Evaluation

The model was evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix
* Classification Report

### Validation Results

| Metric    |  Score |
| --------- | -----: |
| Accuracy  | 99.13% |
| Precision | 38.46% |
| Recall    | 75.00% |
| F1 Score  | 50.85% |

### Final Test Results

| Metric    |      Score |
| --------- | ---------: |
| Accuracy  | **99.23%** |
| Precision | **29.24%** |
| Recall    | **70.77%** |
| F1 Score  | **41.38%** |

The model achieved approximately **70.77% recall**, meaning it successfully detected a substantial portion of fraudulent transactions.

Because the dataset is highly imbalanced, accuracy alone is not sufficient for evaluating fraud detection performance. Precision, recall and F1-score are therefore also considered.

---

## Confusion Matrix

The final test confusion matrix was:

```text
[[549901   3673]
 [   627   1518]]
```

Interpretation:

* **549,901** normal transactions were correctly classified.
* **3,673** normal transactions were incorrectly classified as fraud.
* **1,518** fraudulent transactions were correctly detected.
* **627** fraudulent transactions were missed by the model.

---

## Prediction Output

The trained model was used to generate predictions for the test dataset.

The prediction file was saved as:

```text
DATA/fraud_predictions.csv
```

The trained model was saved as:

```text
DATA/fraud_detection_model.pkl
```

---

## Project Structure

```text
Credit_Card_Fraud_Detection/
│
├── DATA/
│   ├── fraudTrain.csv
│   ├── fraudTest.csv
│   ├── fraud_predictions.csv
│   └── fraud_detection_model.pkl
│
├── Credit_Card_Fraud_Detection.ipynb
│
└── README.md
```

---

## Conclusion

This project demonstrates how Machine Learning can be applied to credit card fraud detection.

The Random Forest model achieved **99.23% accuracy** and **70.77% recall** on the final test dataset. The results show that the model can identify a significant number of fraudulent transactions while maintaining high overall classification performance.

Fraud detection is a highly imbalanced classification problem, so future improvements can focus on increasing precision and recall through advanced techniques such as SMOTE, XGBoost, threshold tuning, feature engineering and ensemble methods.

---

## Future Scope

Possible improvements include:

* Hyperparameter tuning.
* Testing XGBoost and other advanced models.
* Applying SMOTE or other imbalance-handling techniques.
* Optimizing the classification threshold.
* Improving feature engineering.
* Deploying the model using Flask or FastAPI.
* Creating a real-time fraud detection dashboard.
* Monitoring model performance on new transactions.

---

## Author

**Krishna**

### Project Type

**Machine Learning Internship Project**

### Domain

**Fraud Detection / Machine Learning / Classification**
