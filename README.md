# Customer Conversion Prediction using Logistic Regression 📈

## Overview

This project focuses on predicting customer conversion using demographic, marketing, website engagement, and historical purchase data.

The objective is to identify the factors that influence whether a customer converts and to build a machine learning model capable of estimating conversion probability.

The project explores data preprocessing, feature engineering, logistic regression modeling, class imbalance handling, model evaluation, and business insight generation.

---

## Business Problem

Marketing teams invest significant resources into advertising campaigns and customer acquisition.

A key challenge is identifying:

* Which customers are likely to convert
* Which marketing channels perform best
* Which customer behaviors indicate purchase intent
* How engagement influences conversion outcomes

Accurate conversion prediction enables companies to optimize marketing spend, improve targeting strategies, and increase return on investment (ROI).

---

## Dataset

The dataset contains customer demographic information, marketing campaign attributes, website engagement metrics, and historical purchasing behavior.

### Feature Categories

#### Demographic Features

* Age
* Gender
* Income

#### Marketing Features

* Campaign Channel
* Campaign Type
* Ad Spend
* Click Through Rate (CTR)

#### Customer Engagement Features

* Website Visits
* Pages Per Visit
* Time On Site
* Social Shares
* Email Opens
* Email Clicks

#### Historical Customer Data

* Previous Purchases
* Loyalty Points

#### Target Variable

```text
Conversion

1 = Converted
0 = Did Not Convert
```

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-Learn
* Matplotlib
* Seaborn

---

## Data Preprocessing

The following preprocessing steps were performed:

* Missing value inspection
* Label encoding for binary categorical variables
* One-hot encoding for multi-class categorical variables
* Removal of non-informative identifiers
* Feature scaling using StandardScaler
* Train-test split

---

## Feature Engineering

Several custom features were created to capture customer engagement and marketing effectiveness.

### Email Engagement

```python
email_engagement = EmailClicks / (EmailOpens + 1)
```

Measures how effectively email opens translate into customer interaction.

---

### Website Engagement Score

```python
engagement_score = PagesPerVisit * TimeOnSite
```

Captures overall website engagement intensity.

---

### Customer Value Score

```python
customer_value = PreviousPurchases * LoyaltyPoints
```

Represents long-term customer loyalty and purchasing behavior.

---

### Marketing Efficiency

```python
marketing_efficiency = ClickThroughRate * TimeOnSite
```

Combines advertising effectiveness with on-site engagement.

---

## Exploratory Data Analysis

The following analyses were conducted:

* Conversion rate distribution
* Correlation analysis
* ROC Curve visualization
* Feature importance analysis
* Conversion vs Time On Site
* Conversion vs Previous Purchases
* Conversion vs Email Opens
* Campaign performance comparison
* Customer engagement analysis

---

## Model Development

### Logistic Regression

Logistic Regression was selected as the baseline classification model due to its:

* Interpretability
* Probability estimation capability
* Strong performance on structured tabular data

---

### Class Imbalance Investigation

The dataset contained a significant imbalance:

```text
Converted Customers: ~88%
Non-Converters: ~12%
```

Two model variations were evaluated:

#### Standard Logistic Regression

* Higher overall accuracy
* Better ROC-AUC score

#### Class-Weighted Logistic Regression

```python
class_weight='balanced'
```

* Improved detection of minority class observations
* Increased recall for non-converting customers

---

## Model Evaluation

### Metrics Used

* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC

---

### Best Model Performance

```text
ROC-AUC ≈ 0.79
```

The model demonstrated a strong ability to distinguish between converting and non-converting customers.

Feature scaling improved model performance substantially:

```text
ROC-AUC

Without Scaling: ~0.65
With Scaling:    ~0.79
```

---

## Key Findings

### Customer Engagement Drives Conversion

The strongest predictors of conversion were:

* Email Opens
* Email Clicks
* Time On Site
* Pages Per Visit

Customers who actively engage with marketing content and spend more time exploring the website are significantly more likely to convert.

---

### Customer Loyalty Matters

Historical customer activity showed a strong positive relationship with conversion:

* Previous Purchases
* Loyalty Points

Returning customers demonstrated a higher likelihood of conversion compared to new visitors.

---

### Marketing Campaigns Influence Outcomes

Campaign type had measurable impact on conversion probability.

Conversion-focused campaigns performed better than consideration-focused campaigns, suggesting that campaign intent plays a significant role in customer behavior.

---

### Feature Scaling Was Critical

Standardizing numerical features improved the model's ability to learn meaningful relationships and significantly increased ROC-AUC performance.

---

## Project Structure

```text
customer-conversion-prediction/
│
├── notebooks/
│   └── digital_marketing_customer_conversion.ipynb
│
├── data/
│   └── customer_conversion_data.csv
│
├── README.md
│
└── requirements.txt
```

---

## Future Improvements

Potential next steps include:

* Random Forest Classifier
* XGBoost Classifier
* Hyperparameter tuning
* Feature selection techniques
* SHAP explainability analysis
* Marketing campaign optimization dashboard
* Customer segmentation analysis

---

## Conclusion

This project demonstrates how customer demographics, marketing activity, website engagement, and historical purchasing behavior can be leveraged to predict customer conversion.

The Logistic Regression model achieved a ROC-AUC score of approximately 0.79 while providing interpretable insights into the factors that drive customer conversion.

Beyond predictive performance, the project highlights the importance of customer engagement metrics and loyalty indicators in marketing analytics and customer acquisition strategies.

---

## Author

Built as part of a machine learning learning journey focused on:

* Classification
* Logistic Regression
* Marketing Analytics
* Feature Engineering
* Customer Behavior Modeling
* Business-Focused Data Science
