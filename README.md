#  Customer Conversion Prediction using Machine Learning

##  Project Overview

This project focuses on predicting whether a customer will convert using machine learning classification algorithms.

The objective is to estimate customer conversion probability based on demographic information, marketing campaign characteristics, customer engagement metrics, and historical purchasing behavior.

Six different machine learning models were implemented and compared to identify the most effective approach for customer conversion prediction.

The project emphasizes not only prediction accuracy but also proper evaluation using ROC-AUC, Precision, Recall, F1-Score, and Confusion Matrix analysis due to class imbalance.

---

# Problem Statement

Marketing campaigns often target thousands of customers, but only a small percentage ultimately convert.

Accurately predicting customer conversion enables businesses to:

- Improve marketing efficiency
- Reduce customer acquisition costs
- Prioritize high-value leads
- Increase conversion rates
- Improve campaign ROI
- Allocate advertising budgets more effectively

The objective is to build predictive models capable of estimating customer conversion likelihood before launching marketing campaigns.

---`

---

#  Technologies Used

- Python
- Pandas
- NumPy
- Scikit-Learn
- XGBoost
- Matplotlib
- Seaborn

---

#  Data Preprocessing

The following preprocessing steps were performed:

- Missing value inspection
- Label Encoding
- One-Hot Encoding
- Feature Selection
- Train-Test Split
- Feature Scaling (Logistic Regression & SVM)

### Removed Features

```
CustomerID
AdvertisingPlatform
AdvertisingTool
```

These columns either acted as identifiers or provided little predictive value.

---

# 📈 Exploratory Data Analysis

The following analyses were performed:

- Conversion Distribution
- Correlation Heatmaps
- Confusion Matrix Analysis
- ROC Curve Evaluation
- Feature Relationship Analysis

---

#  Machine Learning Models

## 1. Logistic Regression

Used as the baseline classification model.

### Performance

| Metric | Value |
|---------|------:|
| Accuracy | ~89% |
| ROC-AUC | ~0.79 |

### Observations

- Fast and interpretable
- Strong baseline model
- Produced calibrated probability estimates

---

## 2. Decision Tree Classifier

Used to capture nonlinear decision boundaries.

### Performance

| Metric | Value |
|---------|------:|
| Accuracy | ~87% |
| ROC-AUC | ~0.74 |

### Observations

- Easy to interpret
- Captured nonlinear relationships
- Lower generalization performance than ensemble models

---

## 3. Random Forest Classifier

Random Forest combined multiple decision trees using bagging.

### Performance

| Metric | Value |
|---------|------:|
| Accuracy | ~90% |
| ROC-AUC | 0.815 |

### Observations

- Strong predictive performance
- Reduced overfitting
- Excellent performance on the majority class

---

## 4. AdaBoost Classifier ⭐

AdaBoost sequentially improved weak learners by focusing on previously misclassified observations.

### Performance

| Metric | Value |
|---------|------:|
| Accuracy | ~90% |
| ROC-AUC | **0.842** |

### Observations

- Highest ROC-AUC score
- Best probability ranking
- Strongest overall classifier on this dataset

---

## 5. XGBoost Classifier

Extreme Gradient Boosting was implemented to compare boosting techniques.

### Performance

| Metric | Value |
|---------|------:|
| Accuracy | ~91% |
| ROC-AUC | 0.812 |

Minority Class Performance

```
Precision : 0.74
Recall    : 0.46
F1 Score  : 0.57
```

### Observations

- Highest classification accuracy
- Significantly improved minority-class recall
- Better at identifying non-converting customers than AdaBoost
- Slightly lower ROC-AUC than AdaBoost

---

## 6. Support Vector Machine (SVM)

SVM was implemented after feature scaling to compare a kernel-based classifier against tree-based methods.

### Performance

| Metric | Value |
|---------|------:|
| Accuracy | ~89% |
| ROC-AUC | 0.781 |

### Observations

- Required feature scaling
- Competitive baseline performance
- Underperformed compared to ensemble learning methods on this high-dimensional tabular dataset

---

#  Model Comparison

| Model | Accuracy | ROC-AUC |
|---------|---------:|---------:|
| Logistic Regression | ~89% | ~0.79 |
| Decision Tree | ~87% | ~0.74 |
| Random Forest | ~90% | 0.815 |
| AdaBoost | ~90% | **0.842** ⭐ |
| XGBoost | **~91%** | 0.812 |
| SVM | ~89% | 0.781 |

---

#  Handling Class Imbalance

The dataset contained a significantly larger number of converted customers than non-converted customers.

Because of this imbalance, model evaluation relied on multiple metrics rather than accuracy alone.

Evaluation included:

- ROC-AUC
- Precision
- Recall
- F1-Score
- Confusion Matrix

This provided a more reliable assessment of model performance on both classes.

---

#  Conclusion

### Customer Engagement Drives Conversion

Features related to customer interaction demonstrated strong predictive power.

Examples include:

- Email Opens
- Email Clicks
- Website Visits
- Time On Site

---

### Previous Customer Behaviour Matters

Customers with previous purchases and higher loyalty engagement were more likely to convert.

---

### Ensemble Learning Outperformed Traditional Models

Random Forest, AdaBoost, and XGBoost consistently outperformed Logistic Regression and Decision Trees.

---

### Different Models Excelled at Different Objectives

AdaBoost achieved the highest ROC-AUC score, making it the strongest model for ranking customer conversion probabilities.

XGBoost achieved the highest classification accuracy while substantially improving recall for the minority class, making it more suitable when identifying non-converting customers is a business priority.

---



