# Problem Set 02: Bank Term Deposit Prediction using Logistic Regression

## Introduction
This project aims to develop a predictive model that can determine whether a customer will subscribe to a term deposit based on their banking behaviour. The dataset contains customer demographic information, account details, and historical marketing campaign data collected by a banking institution.
Predicting customer subscription is important for banks as it helps them target the right customers and improve marketing efficiency. In this project, a machine learning approach is used to analyze customer data and build a classification model that can support data-driven decision making.
The target variable:
- `y = yes (1)` means customer subscribed  
- `y = no (0)`  meansr did not subscribe 

---

## Approach
The dataset was loaded from Google Drive and explored to understand its structure and distribution. The target variable was converted into binary format for classification. Numerical and categorical features were identified and processed separately. A preprocessing pipeline was applied for scaling, encoding, and handling class imbalance using `class_weight='balanced'`.

---

## Methodology
A Logistic Regression model was used for this binary classification task. Numerical features were processed using median imputation and standardization, while categorical features were handled using most frequent imputation and one-hot encoding.The dataset was split into training and testing sets (80%–20%) to evaluate model performance. Since the dataset was imbalanced, class weighting was applied to improve the model’s ability to detect the minority class (yes).

---

## Findings

### Model Performance

| Metric   | Value   |
|----------|--------|
| Accuracy | 0.8457 |

---

### Confusion Matrix

|               | Predicted No | Predicted Yes |
|---------------|--------------|---------------|
| Actual No     | 6786         | 1199          |
| Actual Yes    | 196          | 862           |

**Explanation:**
The model correctly classified 6786 customers who did not subscribe and 862 customers who subscribed. A total of 1199 non-subscribers were incorrectly predicted as subscribers, while 196 actual subscribers were misclassified as non-subscribers. 
This indicates that the model is now able to detect a large portion of actual subscribers, which is important for business applications, although some false predictions still exist.

---

### Classification Report

| Class | Precision | Recall | F1-Score | Support |
|------|----------|--------|----------|---------|
| No   | 0.97     | 0.85   | 0.91     | 7985    |
| Yes  | 0.42     | 0.81   | 0.55     | 1058    |

| Metric        | Value |
|--------------|------|
| Accuracy     | 0.85 |
| Macro Avg    | 0.70 / 0.83 / 0.73 |
| Weighted Avg | 0.91 / 0.85 / 0.87 |

**Explanation:**
The model performs very well for the majority class (no) with high precision and recall. For the minority class (yes), the recall is significantly improved, meaning the model can successfully identify most customers who will subscribe. However, the precision for the yes class is lower, indicating some false positives. Overall, the model shows improved and more balanced performance after handling class imbalance.

---

## Conclusion
The Logistic Regression model was successfully developed to predict customer subscription to term deposits. The model achieved good overall accuracy and improved detection of the minority class after handling imbalance. It demonstrates that customer data can be effectively used for predictive modeling in banking. Overall, the model provides a simple and interpretable solution for classification tasks.
