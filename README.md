# 💳 Financial Fraud Detection and Risk Analysis

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)
![Streamlit](https://img.shields.io/badge/Streamlit-Dashboard-red?logo=streamlit)
![Scikit--Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange?logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?logo=numpy)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-orange?logo=jupyter)

> A machine learning-based fraud detection system that analyzes financial transactions and provides an interactive risk prediction dashboard using Streamlit.


---

## 🌐 Live Demo

### 🚀 Streamlit Application

**Live App:** [Financial Fraud Detection Dashboard](LIVE_STREAMLIT_URL)

> The live application is deployed using Streamlit Community Cloud.

---

## 📌 Project Overview

Financial fraud detection is a binary classification problem where the objective is to identify transactions that may be fraudulent based on transaction, account, device, location, merchant, and user-behavior information.

This project implements an end-to-end machine learning workflow for detecting potentially fraudulent financial transactions.

The project includes:

- Data understanding
- Data cleaning
- Exploratory Data Analysis (EDA)
- Feature engineering
- Data preprocessing
- Machine learning model training
- Model comparison
- Model evaluation
- Interactive Streamlit dashboard
- Individual transaction fraud-risk prediction

The final application allows users to enter transaction details and obtain a model-based fraud prediction and probability.

---

## 🎯 Project Objectives

The main objectives of this project are:

- Analyze financial transaction data.
- Identify patterns associated with fraudulent transactions.
- Clean and prepare the dataset for machine learning.
- Perform exploratory data analysis.
- Create meaningful transaction and user-behavior features.
- Train multiple classification models.
- Compare models using F1-Score and ROC-AUC.
- Select the best-performing model based on F1-Score.
- Evaluate the selected model using multiple classification metrics.
- Build an interactive Streamlit dashboard.
- Provide a user-friendly interface for transaction risk prediction.

---

## ✨ Key Features

### 📊 Interactive Dashboard

Provides an overview of the transaction dataset, including:

- Total transactions
- Fraudulent transactions
- Legitimate transactions
- Fraud rate
- Transaction class distribution

### 🔍 Fraud Risk Prediction

Users can enter transaction information and receive:

- Fraud prediction
- Fraud probability
- Risk indication based on the model output

### 📈 Test Set Analysis

Provides evaluation results on the held-out test dataset:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC
- Confusion Matrix
- Prediction breakdown

### 🤖 Model Information

Provides information about:

- Selected machine learning model
- Model comparison
- Feature engineering
- Preprocessing pipeline
- Numerical features
- Categorical features
- Model input features

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| **Python** | Core programming and machine learning workflow |
| **Pandas** | Data loading, cleaning, transformation, and analysis |
| **NumPy** | Numerical operations and feature engineering |
| **Scikit-learn** | Preprocessing, model training, and evaluation |
| **Joblib** | Saving and loading trained ML artifacts |
| **Jupyter Notebook** | Data understanding, EDA, feature engineering, training, and evaluation |
| **Streamlit** | Interactive web application and dashboard |

### Machine Learning Techniques

- Logistic Regression
- Random Forest
- Gradient Boosting
- Median Imputation
- Most-Frequent Imputation
- Standard Scaling
- One-Hot Encoding
- Confusion Matrix
- Precision
- Recall
- F1-Score
- ROC-AUC

---

## 🔄 Machine Learning Workflow

The project follows an end-to-end machine learning pipeline:

```text
Raw Dataset
     │
     ▼
Data Understanding
     │
     ▼
Data Cleaning
     │
     ▼
Exploratory Data Analysis
     │
     ▼
Feature Engineering
     │
     ▼
Train / Test Split
     │
     ▼
Data Preprocessing
     │
     ▼
Model Training
     │
     ▼
Model Comparison
     │
     ▼
Model Evaluation
     │
     ▼
Model Selection
     │
     ▼
Streamlit Application
     │
     ▼
Fraud Risk Prediction
