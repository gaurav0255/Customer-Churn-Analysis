1. Executive Summary

Customer churn is one of the biggest challenges faced by telecom companies. Every customer lost directly impacts revenue and increases customer acquisition costs. Since retaining an existing customer is considerably less expensive than acquiring a new one, organizations need intelligent systems capable of identifying customers who are likely to leave.

This project aims to analyze customer behavior and develop an Artificial Neural Network (ANN) model capable of predicting customer churn using demographic information, subscription details, and billing data.

Through extensive Exploratory Data Analysis (EDA), data preprocessing, and ANN modeling, this project identifies important factors influencing churn and provides actionable insights that can help businesses reduce customer attrition and improve profitability.

2. Business Problem Statement

The telecom company Leo has observed an increasing number of customers discontinuing their services and moving to competitors. The company currently lacks a data-driven mechanism to identify customers who are likely to churn.

This creates several business challenges:

Revenue loss due to customer attrition
Increased marketing expenses for customer acquisition
Reduced customer lifetime value
Difficulty in designing targeted retention strategies
Inability to proactively address customer dissatisfaction

Therefore, the company requires a predictive system that can:

Predict customers likely to churn
Understand the factors influencing churn
Identify high-risk customer segments
Support proactive retention strategies

This project addresses these challenges by building a machine learning-based customer churn prediction system using Artificial Neural Networks.

3. Business Objectives

The primary objectives of this project are:

Customer Understanding

Analyze customer demographics, services, and billing patterns.

Churn Prediction

Develop a predictive model that accurately identifies customers likely to leave.

Customer Segmentation

Identify high-risk customer groups.

Business Decision Support

Generate actionable insights for customer retention.

Profitability Improvement

Reduce churn and increase customer lifetime value.

4. Project Goals

The project aims to:

✔ Understand customer behavior patterns.

✔ Determine the factors affecting customer churn.

✔ Build and evaluate ANN-based churn prediction models.

✔ Compare different model architectures.

✔ Recommend business strategies for reducing churn.

5. Dataset Description

The dataset contains customer information from a telecom company.

Dataset Features
Variable	Description
customerID	Unique customer identifier
gender	Male or Female
SeniorCitizen	Indicates whether customer is a senior citizen
Partner	Customer has a partner
Dependents	Customer has dependents
tenure	Number of months customer stayed
PhoneService	Customer has phone service
MultipleLines	Customer has multiple lines
InternetService	DSL, Fiber Optic, No Internet
Contract	Month-to-month, One Year, Two Year
PaymentMethod	Customer payment mode
MonthlyCharges	Monthly billing amount
TotalCharges	Total amount paid
Churn	Target variable
6. Data Understanding

The dataset contains four major categories of information:

Demographic Information
Gender
Senior Citizen
Partner
Dependents
Service Information
Internet Service
Phone Service
Multiple Lines
Financial Information
Monthly Charges
Total Charges
Payment Method
Customer Relationship Information
Tenure
Contract Type
7. Exploratory Data Analysis (EDA)

EDA was performed to understand customer behavior and identify factors associated with churn.

Customer Churn Distribution
Observation

Approximately:

73% customers retained
27% customers churned
Business Interpretation

Nearly one out of every four customers leaves the company, indicating a significant churn problem.

Gender Distribution
Observation

The customer base is nearly equally distributed between males and females.

Business Interpretation

Gender alone is not a major indicator of customer churn.

Internet Service Analysis
Observation

Customers are distributed among:

DSL
Fiber Optic
No Internet Service
Business Interpretation

Fiber-optic customers contribute substantial revenue but often exhibit higher churn rates.

Possible reasons:

Expensive plans
Service dissatisfaction
Better competitor offerings
Tenure Analysis
Observation

Customers with lower tenure exhibit higher churn.

Business Interpretation

New customers have lower loyalty and are more likely to leave.

Monthly Charges Analysis
Observation

Higher monthly charges are associated with increased churn probability.

Business Interpretation

Pricing plays a major role in customer retention.

Total Charges Analysis
Observation

Customers with lower lifetime spending tend to churn more.

Business Interpretation

Lower engagement often leads to early customer exit.

8. Data Preprocessing
Missing Value Treatment

The variable:

TotalCharges

contained blank values.

Actions performed:

Identified missing values
Converted data type
Handled blank records appropriately
Data Type Conversion

Converted:

TotalCharges

from Object datatype to Numeric datatype.

Target Variable Encoding

The target variable:

Churn

was converted into binary values.

Original	Encoded
Yes	1
No	0
Feature Encoding

Categorical variables were transformed into numerical representations using encoding techniques suitable for neural networks.

Data Scaling

Feature scaling was performed before model training because neural networks are sensitive to differences in feature magnitudes.

Benefits:

Faster convergence
Stable gradient updates
Better model performance
9. Feature Engineering

The following features were found to be highly informative:

Tenure

Represents customer loyalty.

MonthlyCharges

Represents recurring customer expenditure.

TotalCharges

Represents overall customer value.

These variables significantly contribute to churn prediction.

10. Model Development

The project developed multiple ANN models.

The data was divided into:

Training Data: 80%
Testing Data: 20%
11. Artificial Neural Network Architecture
Model 1
Input Features
Tenure
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
Model 2
Input Features
Tenure
Architecture

Input Layer:

12 neurons
ReLU activation

Dropout Layer:

30%

Hidden Layer:

8 neurons
ReLU activation

Dropout Layer:

20%

Output Layer:

Sigmoid activation
Model 3
Input Features
Tenure
MonthlyCharges
TotalCharges
Architecture

Input Layer:

12 neurons
ReLU activation

Hidden Layer:

8 neurons
ReLU activation

Output Layer:

Sigmoid activation
Why ReLU Activation?

ReLU:

Speeds up training
Reduces vanishing gradient problem
Computationally efficient
Why Sigmoid Activation?

Sigmoid is ideal for binary classification.

Output:

0 = No Churn
1 = Churn
Why Dropout?

Dropout:

Prevents overfitting
Improves model generalization
Creates robust neural networks
12. Model Training and Evaluation

The models were evaluated using:

Accuracy

Measures overall prediction correctness.

Formula

Accuracy = (TP + TN) / (TP + TN + FP + FN)

Confusion Matrix

Measures:

True Positives
True Negatives
False Positives
False Negatives
13. Model Performance Analysis
Model	Features Used	Approx Accuracy	Generalization
Model 1	Tenure	~75%	Good
Model 2	Tenure + Dropout	~74%	Better
Model 3	Tenure + MonthlyCharges + TotalCharges	Highest	Best
Model Selection
Final Selected Model

✅ Model 3

Reasons
Uses multiple informative features
Better predictive capability
Lower bias
Strong business interpretability
Better generalization on unseen data
14. Key Business Insights
Insight 1

Customers with lower tenure exhibit the highest churn probability.

Insight 2

Customers with high monthly charges are more likely to churn.

Insight 3

Customers with low total spending often leave early.

Insight 4

Fiber-optic customers generate high revenue but also show high churn risk.

Insight 5

Month-to-month contract customers are more likely to discontinue services.

15. Business Recommendations
Recommendation 1

Develop onboarding programs for new customers.

Recommendation 2

Offer personalized discounts to high-risk customers.

Recommendation 3

Introduce loyalty rewards for long-tenure customers.

Recommendation 4

Improve service quality for fiber-optic customers.

Recommendation 5

Encourage customers to shift toward long-term contracts.

16. Business Impact

Implementing this predictive system can help the company:

Reduce Customer Churn

Even a small reduction in churn can significantly increase profits.

Increase Customer Lifetime Value

Retaining customers increases long-term revenue.

Reduce Acquisition Costs

Customer retention is cheaper than acquiring new customers.

Enable Proactive Decision-Making

The company can intervene before customers decide to leave.

17. Conclusion

This project successfully developed an Artificial Neural Network-based customer churn prediction system for a telecom company.

The analysis revealed that customer tenure, monthly charges, and total charges are among the most influential factors affecting churn behavior.

Among all models developed, Model 3 demonstrated the best predictive performance because it incorporated multiple business-relevant features.

The project illustrates how machine learning and deep learning techniques can transform raw customer data into actionable business intelligence, enabling organizations to reduce customer attrition and improve profitability.
