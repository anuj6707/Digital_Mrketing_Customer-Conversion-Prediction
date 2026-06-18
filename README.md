# Customer Conversion Prediction using Machine Learning

## Project Overview

This project predicts whether a customer will convert based on demographic information, marketing campaign interactions, customer engagement metrics, and historical purchasing behavior.

Multiple machine learning classification algorithms were trained and compared to identify the most effective model for predicting customer conversions.

The project focuses not only on predictive accuracy but also on evaluating model performance under class imbalance using ROC-AUC, precision, recall, and confusion matrix analysis.

---

## Business Problem

Marketing campaigns often reach thousands of customers, but only a portion of them convert into paying customers.

Accurately identifying high-probability customers enables businesses to:

* Improve marketing efficiency
* Reduce acquisition costs
* Increase conversion rates
* Prioritize valuable leads
* Improve campaign ROI

The objective of this project is to build machine learning models capable of predicting customer conversion likelihood before campaign resources are allocated.

---

## Dataset Features

The dataset contains customer demographic, engagement, and marketing information.

### Customer Information

* Age
* Gender
* Income

### Campaign Information

* Campaign Channel
* Campaign Type
* Ad Spend
* Click Through Rate (CTR)

### Customer Engagement

* Website Visits
* Pages Per Visit
* Time On Site
* Social Shares
* Email Opens
* Email Clicks

### Historical Behavior

* Previous Purchases
* Loyalty Points

### Target Variable

```text
Conversion
1 = Converted
0 = Not Converted
```

---

## Data Preprocessing

The following preprocessing steps were performed:

* Missing value inspection
* Label Encoding
* One-Hot Encoding
* Feature Selection
* Train-Test Split
* Feature Scaling (for Logistic Regression)

Removed columns:

```text
CustomerID
AdvertisingPlatform
AdvertisingTool
```

---

## Exploratory Data Analysis

Exploratory analysis was performed to understand conversion behavior and feature relationships.

Visualizations included:

* Conversion Distribution
* Correlation Heatmaps
* Confusion Matrices
* ROC Curves
* Feature Relationship Analysis

---

# Models Implemented

## Logistic Regression

Used as the baseline classification model.

Strengths:

* Fast training
* Probabilistic predictions
* High interpretability

### Performance

| Metric   | Value |
| -------- | ----- |
| Accuracy | ~89%  |
| ROC-AUC  | ~0.79 |

---

## Decision Tree Classifier

Used to capture nonlinear decision boundaries and compare against Logistic Regression.

### Performance

| Metric   | Value |
| -------- | ----- |
| Accuracy | ~87%  |
| ROC-AUC  | ~0.74 |

### Observations

* Easy to interpret
* Captured nonlinear patterns
* Lower generalization performance

---

## Random Forest Classifier

Random Forest was implemented to improve predictive performance through ensemble learning.

### Performance

| Metric   | Value |
| -------- | ----- |
| Accuracy | ~90%  |
| ROC-AUC  | 0.815 |

Confusion Matrix:

```text
[[ 36 158]
 [  9 1397]]
```

### Observations

* Strong predictive capability
* Excellent recall for converted customers
* Reduced overfitting compared to Decision Trees

---

## AdaBoost Classifier

AdaBoost was implemented to improve classification performance by iteratively focusing on difficult observations.

### Performance

| Metric   | Value |
| -------- | ----- |
| Accuracy | ~90%  |
| ROC-AUC  | 0.842 |

Confusion Matrix:

```text
[[ 46 148]
 [  9 1397]]
```

### Observations

* Highest ROC-AUC score
* Strongest ranking performance
* Best-performing model in this project

---

# Model Comparison

| Model               | Accuracy | ROC-AUC |
| ------------------- | -------- | ------- |
| Logistic Regression | ~89%     | ~0.79   |
| Decision Tree       | ~87%     | ~0.74   |
| Random Forest       | ~90%     | 0.815   |
| AdaBoost            | ~90%     | 0.842   |

---

# Class Imbalance Challenge

The dataset contained significantly more converted customers than non-converted customers.

Because of this imbalance:

* Accuracy alone was insufficient
* ROC-AUC became the primary evaluation metric
* Confusion matrices were analyzed to better understand prediction quality

This project highlights the importance of selecting appropriate evaluation metrics for imbalanced classification problems.

---

# Key Findings

### Customer Engagement Strongly Influences Conversion

Features related to customer interaction demonstrated strong predictive power:

* Email Opens
* Email Clicks
* Website Visits
* Time On Site

### Historical Customer Activity Matters

Customers with:

* Previous Purchases
* Loyalty Points

showed a higher likelihood of conversion.

### Ensemble Methods Outperformed Traditional Models

Both Random Forest and AdaBoost outperformed Logistic Regression and Decision Trees.

AdaBoost achieved the highest ROC-AUC score and delivered the strongest overall classification performance.

---

# Business Applications

The final model can be used to:

* Predict customer conversion probability
* Improve campaign targeting
* Reduce marketing costs
* Prioritize high-value leads
* Increase marketing ROI

---

# Technologies Used

* Python
* Pandas
* NumPy
* Scikit-Learn
* Matplotlib
* Seaborn

---

# Skills Demonstrated

* Data Cleaning
* Feature Engineering
* Classification Modeling
* Logistic Regression
* Decision Trees
* Random Forest
* AdaBoost
* Ensemble Learning
* ROC-AUC Analysis
* Confusion Matrix Evaluation
* Handling Class Imbalance
* Business Analytics

---

# Future Improvements

* XGBoost
* LightGBM
* Hyperparameter Optimization
* SHAP Feature Importance Analysis
* Flask Deployment
* Real-Time Lead Scoring Dashboard

---

# Conclusion

This project compared multiple machine learning approaches for customer conversion prediction.

Among the evaluated models, AdaBoost achieved the strongest performance with a ROC-AUC score of 0.842, while Random Forest also demonstrated strong predictive capability with a ROC-AUC score of 0.815.

The results show that customer engagement and historical behavioral data contain strong predictive signals and can be leveraged to improve marketing effectiveness and customer acquisition strategies.


