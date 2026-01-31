# 📊 Credit Card Default Risk Prediction
## 📌 Project Overview

This project is an end-to-end Machine Learning–based Credit Card Default Risk Prediction system designed to identify customers who are likely to default on their credit card payments in the next billing cycle.

The solution focuses on risk-sensitive modeling for imbalanced financial data, prioritizing the reduction of False Negatives, which represent the highest business risk in banking and credit systems.

The project covers:
- Data analysis and preprocessing
- Model building and evaluation
- Threshold tuning for business optimization
- Experiment tracking using MLflow
- Deployment using Streamlit
- Business insights via an interactive Tableau dashboard

## 🎯 Business Objective
To help banks and financial institutions:

Detect high-risk customers early

Reduce financial losses due to defaults

Make informed credit decisions

Monitor revenue at risk

## 📂 Dataset Description

The dataset contains real-world credit card customer data, including:

Customer Attributes

Credit Limit (LIMIT_BAL)

Demographics (Age, Gender, etc.)

Behavioral Features (Most Important)

Repayment Status (PAY_0 to PAY_6)

Indicates payment delays across multiple months

Strongest predictors of default

Financial Activity

Billing Amounts (BILL_AMT1 to BILL_AMT6)

Payment Amounts (PAY_AMT1 to PAY_AMT6)

Target Variable

default

1 → Default

0 → No Default

## ⚠️ Key Challenge: Imbalanced Data

Majority of customers are non-defaulters

Minority are defaulters (~22%)

This imbalance makes accuracy a misleading metric, as it fails to capture financial risk effectively.

## 🧠 Modeling Strategy
Why False Negatives Matter Most
Error Type	Impact
False Positive	Minor inconvenience
False Negative	Direct financial loss

The entire project is optimized to minimize False Negatives, even at the cost of accepting some False Positives.

## 📐 Evaluation Metrics

Instead of accuracy, the following metrics were used:

Precision

Recall

Confusion Matrix

F1 Score (Primary Metric)

Why F1 Score?

Balances Precision and Recall

Focuses on minority (default) class

Reflects real business decision outcomes

## 🤖 Models Implemented

Logistic Regression (Baseline)

Decision Tree

Random Forest (Final Model)

Why Random Forest?

Handles non-linear relationships

Robust to noise

Works well on tabular financial data

Supports class weighting

Provides feature importance

## 🎚️ Threshold Tuning (Core Innovation)

Default classification threshold (0.5) produced a low F1 score (~0.37).

To improve risk detection:

Threshold was gradually reduced: 0.5 → 0.4 → 0.3 → 0.2

Recall increased

False Negatives reduced

Final F1 Score ≈ 0.5

This reflects real-world credit risk optimization, not textbook modeling.

## 🧪 Experiment Tracking with MLflow

MLflow was used to:

Track multiple experiments

Log model parameters and metrics

Compare model performance

Select the best configuration reproducibly

This introduces MLOps practices into the project.

## 🚀 Deployment (Streamlit Application)

The trained Random Forest model was deployed using Streamlit.

Application Features

User inputs:

Credit limit

Repayment status

Billing and payment amounts

Model outputs:

Probability of default

Risk category: Low / Medium / High

Uses tuned threshold, not default 0.5

This converts the ML model into a usable decision-support system.

## 📊 Dashboard (Tableau)
Purpose

The Tableau dashboard translates ML outputs into business-friendly insights.

Key KPIs

Total Customers

Default Rate

High-Risk Customers

Average Credit Limit

Revenue at Risk

Visual Insights

Default distribution (class imbalance)

Default rate by age group

Payment delay vs default rate

Credit limit vs risk score

Risk category distribution

Credit utilization by risk level

Business Value

Identifies where risk is concentrated

Explains why customers are risky

Helps prioritize customers for intervention

## 🔗 Project Architecture
CSV Dataset
   ↓
Data Cleaning & EDA (Python)
   ↓
Model Training & Evaluation (Scikit-learn)
   ↓
Experiment Tracking (MLflow)
   ↓
Model Persistence (Joblib)
   ↓
Deployment (Streamlit)
   ↓
Business Insights (Tableau Dashboard)

## 🏁 Final Outcome

Built a risk-optimized credit default prediction system

Reduced False Negatives using:

F1 score

Threshold tuning

Applied industry-aligned ML practices

Delivered both technical and business solutions
