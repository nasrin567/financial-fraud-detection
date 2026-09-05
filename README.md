# 💳 Financial Fraud Detection and Risk Analysis

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)
![Streamlit](https://img.shields.io/badge/Streamlit-Dashboard-red?logo=streamlit)
![Scikit--Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange?logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?logo=numpy)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-orange?logo=jupyter)

 A machine learning-based fraud detection system that analyzes financial transactions and provides an interactive risk prediction dashboard using Streamlit.


---

## 🌐 Live Demo

### 🚀 Streamlit Application

**Live App:** https://financial-fraud-detection-b9qhgkecxc7cm89pla4tjl.streamlit.app/
https://financial-fraud-detection-b9qhgkecxc7cm89pla4tjl.streamlit.app/

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

```
📊 Dataset

The project uses a synthetic financial transaction dataset.

Dataset Size
Category	Count
Total Transactions	50,000
Legitimate Transactions	33,933
Fraudulent Transactions	16,067
Fraud Rate	32.13%
Dataset Classes
0 → Legitimate
1 → Fraud
Dataset Attributes

The project works with transaction-level information such as:

Transaction ID
User ID
Transaction amount
Account balance
Previous fraudulent activity
Daily transaction count
Card age
Transaction date
Transaction type
Device type
Location
Merchant category
Card type
Dataset Files
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
⚙️ Feature Engineering

Several additional features were created to capture transaction patterns, temporal information, and user behavior.

📅 Date Features

The transaction date is converted into:

Year
Month
Day
Day_of_Week
💰 Transaction Amount Binning

Transactions are grouped into amount categories:

Category	Range
micro	0–10
low	10–50
medium	50–100
high	100–250
very_high	250–500
extreme	Above 500
⚖️ Balance-to-Amount Ratio

A ratio is calculated between account balance and transaction amount:

Balance_to_Amount_Ratio =
Account_Balance / Transaction_Amount

Zero and invalid values are handled before the feature is passed to the model.

👤 User Behavior Features

User-level transaction behavior is captured using:

User_Transaction_Count
User_Avg_Transaction_Amount
User_Total_Transaction_Amount
User_Amount_Deviation

These features provide additional context about how a transaction compares with the user's transaction history within the available dataset.

🔧 Data Preprocessing

The preprocessing pipeline treats numerical and categorical features separately.

Numerical Features
Numerical Features
       │
       ▼
Median Imputation
       │
       ▼
StandardScaler

The numerical features include:

Transaction_Amount
Account_Balance
Previous_Fraudulent_Activity
Daily_Transaction_Count
Card_Age
Year
Month
Day
Day_of_Week
Balance_to_Amount_Ratio
User_Transaction_Count
User_Avg_Transaction_Amount
User_Total_Transaction_Amount
User_Amount_Deviation
Categorical Features
Categorical Features
       │
       ▼
Most-Frequent Imputation
       │
       ▼
One-Hot Encoding

The categorical features include:

Transaction_Type
Device_Type
Location
Merchant_Category
Card_Type
Amount_Bin

The preprocessing pipeline is saved and reused by the Streamlit application so that prediction inputs undergo the same transformation process used during model development.

🤖 Machine Learning Models

Three classification algorithms were trained and compared:

Logistic Regression
Random Forest
Gradient Boosting

The models were compared primarily using F1-Score and ROC-AUC.

Model Comparison
Model	F1-Score	ROC-AUC
Logistic Regression	0.3823	0.4922
Gradient Boosting	0.0025	0.4924
Random Forest	0.0000	0.5023
Selected Model

Logistic Regression was selected because it achieved the highest F1-Score among the evaluated models.

The trained model is stored as:

models/best_fraud_model.joblib

The preprocessing pipeline is stored as:

models/preprocessor.joblib
📈 Model Evaluation

The selected Logistic Regression model was evaluated on the held-out test dataset.

Test Set Results
Metric	Score
Accuracy	0.4972
Precision	0.3158
Recall	0.4843
F1-Score	0.3823
ROC-AUC	0.4922
Confusion Matrix

The application provides a confusion matrix to show how the model classified legitimate and fraudulent transactions.

The matrix includes:

True Negatives
False Positives
False Negatives
True Positives

This helps analyze the types of classification errors made by the model.

🖥️ Streamlit Application

The trained model and preprocessing pipeline are integrated into an interactive Streamlit application.

Application Pages
1. 📊 Dashboard

The Dashboard provides a high-level overview of the dataset.

It displays:

Total transactions
Fraud transactions
Legitimate transactions
Fraud rate
Transaction class distribution
2. 🔍 Fraud Prediction

The Fraud Prediction page allows users to enter transaction information.

Input fields include:

User ID
Account Balance
Transaction Date
Transaction Amount
Transaction Type
Device Type
Location
Merchant Category
Card Type
Previous Fraudulent Activity
Daily Transaction Count
Card Age

The application then:

User Input
    ↓
Feature Creation
    ↓
Preprocessing Pipeline
    ↓
Trained Logistic Regression Model
    ↓
Prediction Probability
    ↓
Fraud Risk Result
3. 📈 Test Set Analysis

This page presents the performance of the selected model on the held-out test dataset.

It includes:

Accuracy
Precision
Recall
F1-Score
ROC-AUC
Confusion Matrix
Prediction Breakdown
4. 🤖 Model Information

This page explains:

Selected model
Model selection results
Feature engineering
Preprocessing pipeline
Numerical features
Categorical features
Model features
📸 Dashboard Preview
📊 Dashboard

🔍 Fraud Risk Prediction

📈 Test Set Analysis

🤖 Model Information

Add the corresponding screenshots to the images/ folder before finalizing these image paths.

📁 Project Structure
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
💻 Run Locally
1. Clone the Repository
git clone https://github.com/nasrin567/financial-fraud-detection.git
2. Navigate to the Project Directory
cd financial-fraud-detection
3. Create a Virtual Environment
python -m venv .venv
4. Activate the Virtual Environment
Windows PowerShell
.venv\Scripts\Activate.ps1
5. Install Dependencies
pip install -r requirements.txt
6. Run the Streamlit Application
python -m streamlit run app.py

The application will open in your browser.

⚠️ Known Limitations

The current implementation has several limitations that should be considered when interpreting the results.

Model Performance

The current model has:

F1-Score: 0.3823
ROC-AUC: 0.4922
Accuracy: 0.4972

The ROC-AUC is close to 0.50, indicating limited discrimination between the two classes on the current test data.

Therefore, this implementation should be considered an educational/project prototype rather than a production-ready financial fraud detection system.

Synthetic Dataset

The project uses a synthetic dataset. Its patterns may not represent the complexity and behavior of real-world financial transactions.

User Behavior Features

User-level features are calculated from the available dataset. In a real production system, these features would require carefully designed historical transaction windows to avoid data leakage and to reflect information available at prediction time.

Further Validation

A production fraud detection system would require:

Real-world validation data
Stronger cross-validation
Time-based validation
Model monitoring
Probability calibration
Threshold optimization
Careful treatment of class imbalance
Security and privacy controls
🔮 Future Improvements

Potential improvements include:

Improve training data quality and representativeness.
Use more realistic financial transaction datasets.
Perform extensive hyperparameter tuning.
Explore additional classification algorithms.
Apply appropriate class-imbalance handling techniques.
Perform feature selection.
Analyze feature importance.
Optimize the classification threshold.
Improve probability calibration.
Add model explainability using techniques such as SHAP.
Introduce time-based validation for transaction data.
Add model monitoring and performance tracking.
Improve production deployment and security.
👥 Contributors
Contributor	Role
Nasrin Khatoon	Streamlit application, dashboard integration, deployment, and documentation
Pinkey Kavar Bika	Data and machine learning project development
Moin Sheikh	Data and machine learning project development


