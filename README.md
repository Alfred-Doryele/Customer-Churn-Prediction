Customer Churn Prediction

NexAfrica Machine Learning Internship — Customer Churn Prediction capstone project.

Project Overview

This project builds a machine learning model to predict whether a telecom customer is likely to churn (leave the service) based on their demographic information, account details, and service usage. The goal is to help the business identify at-risk customers in advance so retention efforts can be targeted effectively.

Business Problem

Customer churn is costly — acquiring a new customer is generally more expensive than retaining an existing one. By predicting which customers are likely to churn, the business can proactively intervene with targeted offers, support, or outreach before a customer actually leaves.

Dataset
Source: Telco Customer Churn dataset (Kaggle, by blastchar)
Size: 7,043 customers, 21 original features
Target variable: Churn (Yes/No)
Tools and Technologies
Python
Pandas, NumPy
Matplotlib, Seaborn
Scikit-learn
Google Colab
Git & GitHub
Project Workflow

Business Understanding → Data Collection → Data Cleaning → Exploratory Data Analysis → Feature Engineering → Model Training → Model Evaluation → Model Optimization → Feature Importance → Business Recommendations

Exploratory Data Analysis

Conducted analysis across 8+ visualizations covering churn distribution, contract type, tenure, monthly charges, payment method, internet service, tech support, and correlations between numerical features. Full details and charts are in the notebook and the visuals/ folder.

Machine Learning Models

Three classification models were trained and compared:

Model	Accuracy	Precision	Recall	F1-Score	ROC-AUC
Logistic Regression	0.803	0.659	0.532	0.589	0.842
Decision Tree	0.735	0.500	0.492	0.496	0.657
Random Forest	0.787	0.629	0.481	0.545	0.822

After addressing class imbalance (73.5% No Churn vs 26.5% Churn) using class weighting, the final model's performance improved significantly:

Model	Accuracy	Precision	Recall	F1-Score	ROC-AUC
Logistic Regression (class-weighted)	0.737	0.503	0.794	0.616	0.842
Evaluation Metrics

The final model was evaluated using accuracy, precision, recall, F1-score, ROC-AUC, and a confusion matrix. Recall was prioritized over accuracy, since missing an actual churner is more costly to the business than a false alarm.

Key Findings
Contract type is the strongest churn driver — month-to-month customers churn far more than those on one/two-year contracts.
New customers are the highest risk group — churn spikes heavily in the first few months of tenure.
Fiber optic internet customers churn significantly more than DSL or no-internet customers.
Customers paying by electronic check churn more than those using automatic payment methods.
Customers without tech support or online security services are more likely to churn.
The model performs best at catching early-stage churn risk, but tends to miss churn among longer-tenured customers.
Business Recommendations
Incentivize longer-term contracts through discounts or loyalty perks.
Implement a structured onboarding/check-in program for customers in their first 3–12 months.
Investigate fiber optic service pricing and reliability to address high churn in this segment.
Encourage automatic payment methods to reduce friction-driven churn.
Bundle or discount tech support and online security services.
Build a long-tenure monitoring system, since churn risk doesn't disappear entirely after the early-risk period.
How to Run the Project
Clone this repository
Open notebooks/customer_churn_analysis.ipynb in Google Colab or Jupyter Notebook
Upload the dataset (or use the cleaned dataset in data/processed_data/)
Run all cells in order
Project Structure
Customer-Churn-Prediction/
│
├── data/
│   ├── raw_data/
│   └── processed_data/
│       ├── cleaned_churn_data.csv
│       └── churn_features_ready.csv
│
├── notebooks/
│   └── customer_churn_analysis.ipynb
│
├── src/
│
├── visuals/
│   └── (EDA charts, confusion matrices, ROC curve, feature importance)
│
├── README.md
├── LICENSE
└── requirements.txt
Author

Alfred Doryele GitHub | LinkedIn
