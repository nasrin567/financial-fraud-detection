# 💳 Financial Fraud Detection and Risk Analysis

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![Streamlit](https://img.shields.io/badge/Streamlit-Dashboard-red?logo=streamlit)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?logo=numpy)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?logo=scikit-learn)
![Joblib](https://img.shields.io/badge/Joblib-Model%20Persistence-green)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-orange?logo=jupyter)

A machine learning-based application for detecting potentially fraudulent financial transactions and analyzing transaction risk through an interactive Streamlit dashboard.

The project covers the complete machine learning workflow, including data understanding, data cleaning, exploratory data analysis (EDA), feature engineering, preprocessing, model training, model evaluation, and interactive deployment.

---

## 📌 Project Overview

Financial fraud detection is an important classification problem where the objective is to identify transactions that may be fraudulent based on transaction, account, device, location, merchant, and user-behavior information.

This project develops a binary classification system that predicts whether a transaction belongs to one of two classes:

- `0` → Legitimate Transaction
- `1` → Fraudulent Transaction

The trained model is integrated into a Streamlit dashboard where users can enter transaction details and receive a fraud-risk prediction.

---

## 🎯 Project Objectives

- Analyze financial transaction data and identify patterns related to fraudulent activity.
- Clean and prepare the dataset for machine learning.
- Perform exploratory data analysis (EDA).
- Engineer meaningful transaction and user-behavior features.
- Build and compare multiple classification models.
- Select the best-performing model based on F1-Score.
- Evaluate the selected model using classification metrics and a confusion matrix.
- Build an interactive Streamlit application for fraud-risk prediction.
- Provide a clear view of model performance and preprocessing information.

---

## 📊 Dataset

The project uses a synthetic financial transaction dataset.

The repository contains the following data stages:

```text
data/
├── raw/
│   └── synthetic_fraud_dataset.csv
│
└── processed/
    ├── cleaned_fraud_dataset.csv
    ├── feature_engineered_fraud_dataset.csv
    ├── X_train.csv
    ├── X_test.csv
    ├── y_train.csv
    └── y_test.csv
```

The dataset contains transaction-level information including attributes related to:

- Transaction amount
- Account balance
- Previous fraudulent activity
- Daily transaction count
- Card age
- Transaction type
- Device type
- Location
- Merchant category
- Card type
- Date
- User and transaction information

### Dataset Distribution

The dataset contains:

- **Total Transactions:** 50,000
- **Legitimate Transactions:** 33,933
- **Fraudulent Transactions:** 16,067
- **Fraud Rate:** 32.13%

---

## 🔄 Machine Learning Workflow

The project follows the following workflow:

```text
Raw Dataset
     ↓
Data Understanding
     ↓
Data Cleaning
     ↓
Exploratory Data Analysis
     ↓
Feature Engineering
     ↓
Train/Test Split
     ↓
Preprocessing
     ↓
Model Training
     ↓
Model Comparison
     ↓
Model Evaluation
     ↓
Streamlit Deployment
```

---

## 🛠️ Feature Engineering

Additional features were created to capture temporal, transaction-level, and user-level behavior.

### Date-Based Features

The transaction date is converted into:

- `Year`
- `Month`
- `Day`
- `Day_of_Week`

### Transaction Amount Binning

Transaction amounts are categorized into:

- `micro`
- `low`
- `medium`
- `high`
- `very_high`
- `extreme`

### Balance-to-Amount Ratio

A ratio between account balance and transaction amount is calculated:

```text
Balance_to_Amount_Ratio =
Account_Balance / Transaction_Amount
```

Special handling is applied for zero transaction amounts and invalid values.

### User Behavior Features

The following user-level features are generated:

- `User_Transaction_Count`
- `User_Avg_Transaction_Amount`
- `User_Total_Transaction_Amount`
- `User_Amount_Deviation`

These features provide additional information about transaction behavior for individual users.

---

## ⚙️ Data Preprocessing

The preprocessing pipeline handles numerical and categorical variables separately.

### Numerical Features

The numerical preprocessing pipeline consists of:

```text
Numerical Features
       ↓
Median Imputation
       ↓
StandardScaler
```

Numerical features include:

- `Transaction_Amount`
- `Account_Balance`
- `Previous_Fraudulent_Activity`
- `Daily_Transaction_Count`
- `Card_Age`
- `Year`
- `Month`
- `Day`
- `Day_of_Week`
- `Balance_to_Amount_Ratio`
- `User_Transaction_Count`
- `User_Avg_Transaction_Amount`
- `User_Total_Transaction_Amount`
- `User_Amount_Deviation`

### Categorical Features

The categorical preprocessing pipeline consists of:

```text
Categorical Features
       ↓
Most-Frequent Imputation
       ↓
One-Hot Encoding
```

Categorical features include:

- `Transaction_Type`
- `Device_Type`
- `Location`
- `Merchant_Category`
- `Card_Type`
- `Amount_Bin`

The preprocessing pipeline is saved separately and reused by the Streamlit application during prediction.

---

## 🤖 Machine Learning Models

Three classification algorithms were trained and compared:

1. **Logistic Regression**
2. **Random Forest**
3. **Gradient Boosting**

The models were evaluated using F1-Score and ROC-AUC.

### Model Comparison

| Model | F1-Score | ROC-AUC |
|---|---:|---:|
| **Logistic Regression** | **0.3823** | 0.4922 |
| Gradient Boosting | 0.0025 | 0.4924 |
| Random Forest | 0.0000 | 0.5023 |

### Selected Model

**Logistic Regression** was selected because it achieved the highest F1-Score among the evaluated models.

The selected model is stored as:

```text
models/best_fraud_model.joblib
```

The preprocessing pipeline is stored as:

```text
models/preprocessor.joblib
```

---

## 📈 Model Evaluation

The selected Logistic Regression model was evaluated on the held-out test dataset.

### Test Set Performance

| Metric | Score |
|---|---:|
| Accuracy | 0.4972 |
| Precision | 0.3158 |
| Recall | 0.4843 |
| F1-Score | 0.3823 |
| ROC-AUC | 0.4922 |

### Confusion Matrix

The Streamlit application provides a confusion matrix showing:

- True Negatives
- False Positives
- False Negatives
- True Positives

This helps analyze how the model classifies legitimate and fraudulent transactions.

---

## 🖥️ Streamlit Application

The project includes an interactive Streamlit dashboard for exploring the fraud detection system.

### Dashboard Pages

#### 📊 1. Dashboard

Provides an overview of the dataset, including:

- Total transactions
- Fraudulent transactions
- Legitimate transactions
- Fraud rate
- Transaction class distribution

---

#### 🔍 2. Fraud Risk Prediction

Allows users to enter transaction information such as:

- User ID
- Account balance
- Transaction amount
- Transaction date
- Transaction type
- Device type
- Location
- Merchant category
- Card type
- Previous fraudulent activity
- Daily transaction count
- Card age

The application processes the entered transaction using the saved preprocessing pipeline and trained model.

The prediction page provides a fraud-risk prediction and probability based on the model output.

---

#### 📈 3. Test Set Analysis

Displays model performance on the held-out test dataset.

It includes:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC
- Confusion Matrix
- Prediction breakdown

---

#### 🤖 4. Model Information

Provides information about:

- Selected model
- Model comparison
- Preprocessing pipeline
- Feature engineering
- Numerical features
- Categorical features
- Model input features

---

## 📁 Project Structure

```text
financial-fraud-detection/
│
├── app.py
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   ├── raw/
│   │   └── synthetic_fraud_dataset.csv
│   │
│   └── processed/
│       ├── cleaned_fraud_dataset.csv
│       ├── feature_engineered_fraud_dataset.csv
│       ├── X_train.csv
│       ├── X_test.csv
│       ├── y_train.csv
│       └── y_test.csv
│
├── models/
│   ├── best_fraud_model.joblib
│   └── preprocessor.joblib
│
└── notebooks/
    ├── Data Understanding
    ├── Data Cleaning & EDA
    ├── Feature Engineering
    ├── ML Preparation
    ├── Model Training
    └── Model Evaluation
```

---

## 💻 Technologies Used

- **Python**
- **Pandas**
- **NumPy**
- **Scikit-learn**
- **Joblib**
- **Streamlit**
- **Jupyter Notebook**

### Machine Learning

- Logistic Regression
- Random Forest
- Gradient Boosting
- One-Hot Encoding
- Standard Scaling
- Median/Most-Frequent Imputation
- Classification metrics
- Confusion Matrix
- ROC-AUC

---

## 🚀 Run the Project Locally

### 1. Clone the Repository

```bash
git clone https://github.com/nasrin567/financial-fraud-detection.git
```

### 2. Navigate to the Project

```bash
cd financial-fraud-detection
```

### 3. Create a Virtual Environment

```bash
python -m venv .venv
```

### 4. Activate the Virtual Environment

#### Windows PowerShell

```bash
.venv\Scripts\Activate.ps1
```

### 5. Install Dependencies

```bash
pip install -r requirements.txt
```

### 6. Run the Streamlit Application

```bash
python -m streamlit run app.py
```

The application will open in your browser.

---

## 🌐 Live Demo

**Streamlit App:**  
`[LIVE_STREAMLIT_URL]`

> The live Streamlit URL will be added after deployment.

---

## 📦 Model Files

The trained machine learning artifacts are included in the repository:

```text
models/
├── best_fraud_model.joblib
└── preprocessor.joblib
```

The Streamlit application loads these files to perform predictions.

---

## 🔮 Future Improvements

The project can be further improved by:

- Improving the quality and representativeness of the training data.
- Performing more extensive hyperparameter tuning.
- Testing additional classification algorithms.
- Applying appropriate class-imbalance handling techniques where required.
- Performing feature selection and feature importance analysis.
- Improving probability calibration.
- Exploring threshold optimization for fraud detection.
- Adding model explainability using techniques such as SHAP.
- Adding stronger validation and monitoring for deployment.
- Evaluating the system on more realistic financial transaction data.

---

## 👥 Contributors

- **Nasrin Khatoon** — Streamlit application and dashboard integration
- **Pinkey Kavar Bika**
- **Moin Sheikh**

---

## 📄 License

This project is intended for educational and project-development purposes.
