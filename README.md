Business Problem Statement

Telecom company Leo is experiencing customer attrition. The company wants to:

Analyze customer behavior
Identify high-risk customers
Understand factors affecting churn
Build predictive models to forecast churn
Design customer retention strategies
3. Project Objectives
Primary Objectives
Analyze customer demographics and service usage.
Identify patterns associated with churn.
Build machine learning models to predict customer churn.
Evaluate model performance.
Generate actionable business insights.
4. Dataset Description

The dataset contains customer demographic information, subscription details, billing information, and churn status.

Important Features
Feature	Description
customerID	Unique customer ID
gender	Male/Female
SeniorCitizen	Whether customer is senior citizen
tenure	Number of months customer stayed
InternetService	DSL, Fiber Optic, No Internet
MonthlyCharges	Monthly bill
TotalCharges	Total amount spent
PaymentMethod	Payment mode
Churn	Target Variable
5. Data Understanding

The dataset contains information related to:

Demographic Features
Gender
Senior Citizen
Service Features
Internet Service
Phone Service
Multiple Lines
Financial Features
Monthly Charges
Total Charges
Payment Method
Customer Relationship Features
Tenure
Contract Type
6. Data Preprocessing
Step 1: Import Libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

For model building:

from sklearn.model_selection import train_test_split
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense, Dropout
Step 2: Missing Value Handling

The project identified blank values in:

TotalCharges

Actions performed:

Checked missing values
Converted blank values into numeric values
Removed or handled missing records appropriately
Why?

Neural networks cannot process missing values.

Step 3: Data Type Conversion

Converted:

TotalCharges

from object datatype to numeric datatype.

Step 4: Label Encoding

Target Variable:

Churn

Converted:

Original	Encoded
Yes	1
No	0

This transformation allows the ANN model to process categorical outputs.

7. Exploratory Data Analysis (EDA)
A. Gender Distribution
Objective

Find the total number of male customers.

Business Insight
Helps understand customer demographics.
Enables gender-based retention strategies.
B. DSL Internet Users
Objective

Find total customers using DSL service.

Business Insight

Different internet services show different churn patterns.

Generally:

Fiber users generate more revenue.
Fiber users often exhibit higher churn rates.
C. Female Senior Citizens using Mailed Check
Objective

Extract:

Female customers
Senior citizens
Payment Method = Mailed Check
Business Insight

This segment often:

Uses traditional payment methods
May have higher service dissatisfaction
Requires personalized retention programs
D. New Customers

Criteria:

tenure < 10
OR
TotalCharges < 500
Business Insight

New customers generally:

Have lower loyalty
Are more likely to churn
Require onboarding campaigns
8. Data Visualization
Churn Distribution (Pie Chart)
Findings

Approximately:

73% customers retained
27% customers churned
Interpretation

A churn rate of 27% is significant.

This means:

For every 100 customers:

73 remain
27 leave

The company is losing nearly one-fourth of its customer base.

Internet Service Distribution (Bar Plot)
Findings

Customers are distributed across:

DSL
Fiber Optic
No Internet Service
Interpretation

Fiber users:

Generate higher revenue
Frequently exhibit higher churn

Possible reasons:

High pricing
Service issues
Better competitor offerings
9. Feature Importance Analysis

The project observations indicate:

Tenure

Strong negative relationship with churn.

Meaning:

Low tenure → High churn probability
High tenure → Lower churn probability
Total Charges

Lower spending customers tend to churn more.

Reason:

Lower engagement with company services.

Internet Service

Internet service significantly affects customer behavior.

Fiber customers contribute:

Higher revenue
Higher churn risk
10. Model Building

The project developed three ANN models.

Model 1
Features Used
Tenure
Target
Churn
Architecture

Input Layer:

12 neurons
ReLU activation

Hidden Layer:

8 neurons
ReLU activation

Output Layer:

1 neuron
Sigmoid activation
Why Sigmoid?

Because churn prediction is a binary classification problem.

Output:

0 → No Churn
1 → Churn
Why ReLU?

Advantages:

Faster training
Solves vanishing gradient problem
Computationally efficient
Model 1 Performance

Training Accuracy:

Approximately:

75%

Validation Accuracy:

Approximately:

74-75%
Interpretation

Model learned meaningful patterns.

No major overfitting observed because:

Training Accuracy ≈ Validation Accuracy

Model 2
Features
Tenure
Architecture

Input Layer:

12 neurons
ReLU

Dropout:

30%

Hidden Layer:

8 neurons
ReLU

Dropout:

20%

Output Layer:

Sigmoid
Why Dropout?

Dropout randomly deactivates neurons during training.

Benefits:

Prevents overfitting
Improves generalization
Makes network more robust
Model 2 Performance

Training Accuracy:

73% - 75%

Validation Accuracy:

74%
Interpretation

Slight decrease in training accuracy but improved model robustness.

This indicates:

The model generalizes better on unseen data.

Model 3
Features
Tenure
MonthlyCharges
TotalCharges
Target
Churn
Why These Features?

These variables directly represent:

Customer relationship duration
Monthly spending
Lifetime customer value

These are highly informative variables for churn prediction.

Architecture

Input Layer:

12 neurons
ReLU

Hidden Layer:

8 neurons
ReLU

Output Layer:

Sigmoid
Model Evaluation Metrics

The models were evaluated using:

Confusion Matrix

Measures:

True Positives
True Negatives
False Positives
False Negatives
Accuracy

Formula:

Accuracy=
TP+TN+FP+FN
TP+TN
	​


Measures overall prediction correctness.

Model Comparison
Metric	Model 1	Model 2	Model 3
Features	Tenure	Tenure + Dropout	Tenure + MonthlyCharges + TotalCharges
Accuracy	~75%	~74%	Highest among all models
Overfitting	Low	Very Low	Low
Generalization	Good	Better	Best
Why Model 3 Performs Better

Model 1 only uses:

Tenure

Model 3 uses:

Tenure
MonthlyCharges
TotalCharges

More business information allows the model to identify customer behavior patterns more effectively.

Final Model Selection
Recommended Model

✅ Model 3

Reasons:

Uses multiple informative features
Better predictive capability
More practical for real-world deployment
Better understanding of customer behavior
Business Insights
Insight 1

Customers with:

Low Tenure

have the highest churn probability.

Recommendation

Introduce:

Welcome offers
Early engagement campaigns
Onboarding support
Insight 2

Customers with:

Low Total Spending

show higher churn risk.

Recommendation
Cross-selling
Loyalty programs
Discount bundles
Insight 3

Fiber customers contribute high revenue but also exhibit high churn.

Recommendation
Improve service quality
Provide premium support
Offer retention discounts
Insight 4

Senior citizens using mailed checks may require special attention.

Recommendation
Simplify billing
Personalized support
Dedicated customer service
Business Impact

If implemented, this model can help the company:

Reduce Churn

Even a 5% reduction can significantly increase profits.

Increase Customer Lifetime Value

Retaining customers:

Reduces acquisition costs
Improves revenue stability
Enable Proactive Retention

Instead of reacting after churn occurs, the company can identify at-risk customers beforehand.

Project Conclusion

This project successfully analyzed telecom customer behavior and developed ANN-based churn prediction models.

Major findings:

Churn rate is approximately 27%.
New customers are more likely to leave.
Tenure is one of the strongest churn indicators.
Internet service type influences churn significantly.
Model 3 produced the best predictive performance.

The project demonstrates how Artificial Neural Networks combined with Exploratory Data Analysis can transform customer data into actionable business intelligence and proactive retention strategies.
