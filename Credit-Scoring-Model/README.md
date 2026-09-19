# 💳 Credit Scoring Model

A machine learning based credit risk assessment system that predicts whether a loan applicant represents a **Good Credit Risk** or **Bad Credit Risk** based on financial, employment, demographic, and credit-history information.

The project uses multiple classification algorithms, compares their performance, selects the best-performing model, and provides both a **Flask REST API** and a **web-based interface** for making predictions.

> ⚠️ This project is intended for educational and demonstration purposes. It should not be used as the sole basis for real-world lending or financial decisions.

---

## 📌 Project Overview

Credit scoring is a classification problem where information about a loan applicant is used to estimate their credit risk.

This project takes applicant information such as:

- Credit history
- Credit amount
- Loan duration
- Savings status
- Employment duration
- Age
- Housing
- Job
- Existing credits
- Number of guarantors
- Telephone status
- Foreign worker status
- Other financial information

and uses a trained machine learning model to classify the applicant as:

- **Good Credit Risk**
- **Bad Credit Risk**

The system also displays the probability associated with each prediction.

---

# 🎯 Objectives

The main objectives of this project are:

1. Load and analyze structured credit data.
2. Separate numerical and categorical features.
3. Handle categorical variables using One-Hot Encoding.
4. Standardize numerical features.
5. Train multiple machine learning classification models.
6. Compare models using several evaluation metrics.
7. Select the best-performing model.
8. Save the trained model using Joblib.
9. Build a Flask REST API for predictions.
10. Build a web interface for user-friendly credit risk assessment.
11. Validate user input before prediction.
12. Display prediction probabilities and model performance.

---

# 🧠 Machine Learning Approach

## Algorithms Used

Three classification algorithms were trained and evaluated.

### 1. Logistic Regression

Used as a linear classification baseline.

### 2. Decision Tree

A tree-based model that learns decision rules from the training data.

### 3. Random Forest

An ensemble of multiple decision trees that generally provides better generalization than a single decision tree.

---

# 📊 Dataset

The project uses a structured credit dataset containing **1,000 records**.

### Dataset shape

```text
1000 rows × 21 columns
🧾 Features
Numerical Features

The following numerical features are used:

month_duration
credit_amount
payment_to_income_ratio
residence_since
age
n_credits
n_guarantors

These features are standardized using:

StandardScaler

Categorical Features

The following categorical features are processed using One-Hot Encoding:

status_account
credit_history
purpose
status_savings
years_employment
status_and_sex
secondary_obligor
collateral
other_installment_plans
housing
job
telephone
is_foreign_worker

The encoder uses:

OneHotEncoder(handle_unknown="ignore")
This allows the application to safely handle previously unseen categorical values.

🚀 Installation and Setup
1. Clone the Repository
git clone <YOUR_GITHUB_REPOSITORY_URL>

Move into the project:

cd Credit-Scoring-Model
2. Create a Virtual Environment

Create the virtual environment:

python -m venv .venv

3. Activate the Virtual Environment

On Windows PowerShell:

.\.venv\Scripts\Activate.ps1

After activation, the terminal should show:

(.venv)

Example:

(.venv) PS D:\codealpha_tasks\Credit-Scoring-Model>
4. Install Dependencies

Run:

pip install -r requirements.txt
📂 Dataset Setup

Make sure the dataset exists at:

data/credit_data.csv

You can verify it using:

Get-ChildItem data

Expected:

credit_data.csv
🔍 Test Data Preprocessing
Run:

python src\preprocess.py

A successful run should report information similar to:

Dataset loaded successfully.
Dataset shape: (1000, 21)
Feature shape: (1000, 20)
Target shape: (1000,)
Target values: [0, 1]
Transformed feature shape: (1000, 61)
Preprocessing test completed successfully.

The transformed dataset contains 61 features after numerical scaling and categorical encoding.