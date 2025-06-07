# 🏦 Loan Prediction Dashboard & Machine Learning Model

## 📌 Project Overview
This project focuses on **analyzing, visualizing, and predicting loan approval** status using both **interactive Power BI dashboards** and a **machine learning classification model (Random Forest)**. The aim is to help financial institutions make better, data-driven decisions about **who qualifies for a loan**, based on demographic and financial attributes.

## ❓ Problem Statement
Financial institutions often struggle with identifying the right candidates for loan approvals. Manual loan processing is:
* Time-consuming
* Error-prone
* Biased without data support

This project solves that by:
* **Analyzing loan applicant data** through visuals and insights
* **Predicting loan approval** based on historical data using a machine learning model

## 📂 Dataset Details
The datasets (`loan_dataset.xlsx` and `loan_dataset26.xlsx`) contain information about 5,000+ customers with fields like:

* `Loan` – Whether the person has taken a loan (Yes/No)
* `Age` – Applicant’s age
* `Income` – Total annual income
* `Mortgage` – Mortgage amount
* `Education` – UG/PG/Graduate
* `Experience` – Years of working experience
* `Fixed Deposit` – Has FD? (Yes/No)
* `Demat` – Has Demat account? (Yes/No)
* `Net Banking` – Uses Net banking? (Yes/No)

Irrelevant fields such as `Serial`, `Fam Members`, `Pin-code`, and `ID` were removed for cleaner analysis and modeling.

## 📊 Power BI Dashboard
### 🖼️ Dashboard Visual
![Dashboard](./8071cdfc-955b-4dc2-9479-402e787625fa.png)

### ✅ Insights Derived from the Dashboard
* 📌 **Total Customers:** 5,000
* 💰 **Average Mortgage:** ₹451.99K
* 🎓 **Education vs Mortgage:**

  * Postgraduates hold the **highest average mortgage**
  * Graduates and Undergraduates follow
* 👥 **Loan Distribution by Age Group:**

  * Most loans are concentrated in the **30–59 age** group
* 🌐 **Net Banking Usage:**

  * Heavily used by **middle-aged (30–59)** customers
* 🏦 **Fixed Deposit & Demat Trends:**

  * Senior, experienced customers are more likely to have these
* 💵 **Income Trends:**

  * **Highest income** bracket observed in **40–49 years** age group
* 📊 **Segment Analysis:**

  * Categories like education, age group, and digital adoption (net banking) reveal key targeting opportunities for banks

### 🧠 How the Dashboard Helps:
* Identifies customer profiles with **higher approval rates**
* Helps financial institutions **target digital banking promotions**
* Highlights **under-served age groups** with fewer loans
* Assists product planning by showing usage of **fixed deposits and demat accounts**

## 🧪 Exploratory Data Analysis (Python)
The `loan_prediction_analysis.py` script performs:
### 🔹 Preprocessing:

* Dropped irrelevant columns
* Created bins for `Age` and `Income` to classify user segments
* Cleaned missing values and standardized categorical fields

### 🔹 Visual Analysis:

* Pie chart: Mortgage by Education
* Count plots: Net Banking, Loan status
* Age group analysis for Net Banking and Loan
* Income bin-wise loan status
* Age-wise analysis for Fixed Deposits and Demat

These insights **validate** what is observed in Power BI and help us further refine the model's input features.

## 🤖 Machine Learning Model

### 🔍 Model Used: **Random Forest Classifier**
**Random Forest** is an ensemble model that builds multiple decision trees and combines their outputs to reduce overfitting and improve accuracy.

### 🎯 Why Random Forest?
* Handles **categorical and continuous features**
* Deals well with **imbalanced data**
* Provides **feature importance** insights
* High accuracy without complex tuning

### 🛠 Model Development Steps:
1. **Preprocessing**:

   * Removed columns not contributing to prediction (`ID`, `Education`, `Fixed Deposit`, `Demat`, `Net Banking`)
2. **Feature Selection**:

   * `Age`, `Income`, `Mortgage`, `Experience` used as predictors
3. **Train-Test Split**:

   * 80% training, 20% testing
4. **Training**:

   ```python
   model = RandomForestClassifier()
   model.fit(X_train, y_train)
   ```
5. **Evaluation**:

   * **Accuracy Score**: \~85%
   * **Classification Report**: Includes precision, recall, and F1-score
   * **Confusion Matrix**: Visualized true positives and false negatives
   * **Feature Importance** and **Mutual Information**: Help identify impactful variables

### 📌 Model Output:
Accuracy: 0.85
Precision, Recall, F1: High for both classes

## 🔍 Correlation Analysis

A correlation heatmap was plotted to analyze relationships between features, aiding in selecting impactful variables for modeling.

sns.heatmap(data1.corr(),annot=True).set_title('Correlation Heatmap')

## 💡 How This Project Helps
* **Financial Institutions**: Predict loan approvals with higher confidence
* **Loan Officers**: Understand customer behavior through visual summaries
* **Product Teams**: Tailor banking products to target age, income, and education segments
* **Data Scientists**: Learn how to combine dashboarding with ML modeling for end-to-end solutions

## 🚀 Future Improvements
* Hyperparameter tuning (GridSearchCV)
* Compare with other models: Logistic Regression, XGBoost
* Feature engineering (credit score, dependents, CIBIL history)
* Deploy model as a REST API or Streamlit Web App
* Integrate dashboard with live prediction interface

## 📁 Directory Structure
```
📁 Loan-Prediction-Project
│
├── 📊 loan_dataset.xlsx
├── 📊 loan_dataset26.xlsx
├── 🧠 loan_prediction_analysis.py
├── 🖼️ Loan Prediction Dashboard.png
└── 📄 README.md
```

## 👤 Author
**Sanchit Singh**
