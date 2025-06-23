📂 Project: Multi-Step Regression + Classification for Employee Attrition & Salary Estimation

Tech Stack: Python, Scikit-learn, Pandas, Matplotlib
Dataset: IBM HR Analytics Attrition Dataset

📌 Objective
This project solves a real-world HR analytics challenge by combining classification and regression to not only identify which employees
are at risk of leaving but also estimate the financial impact of losing top talent.

🎯 Key Goals
Predict Employee Attrition
Use classification models to predict whether an employee is likely to leave.

Predict Future Salaries
Estimate next year’s salary for employees likely to stay based on performance and role.

Quantify Business Risk
Combine attrition risk and salary predictions to estimate potential financial loss.

📊 Dataset Summary
Source: Kaggle (IBM HR Analytics)

Rows: 1470 employees

Features: Job role, department, performance rating, salary, and more

Target: Attrition (Yes/No)

  Methodology
 Preprocessing
One-hot encoded categorical variables using ColumnTransformer and OneHotEncoder.

Normalized features using StandardScaler.

Handled class imbalance using class_weight='balanced' in classification.

🔍 Classification: Predicting Attrition
Models Used: Logistic Regression, SVM

Metrics: Accuracy, F1-Score, ROC AUC

Added P_Stay and P_Leave (probabilistic predictions)

 Salary Simulation
Simulated FutureSalary based on PerformanceRating:


df['Increment'] = df['PerformanceRating'].apply(lambda x: 1.10 if x == 4 else 1.05)
df['FutureSalary'] = df['MonthlyIncome'] * df['Increment']
📈 Regression: Predicting Future Salary
Trained only on employees with P_Stay > 0.5

Models Used: Random Forest Regressor

Metrics: R² Score, Mean Squared Error (MSE)

📉 Visualizations
Bar chart of predicted attrition

Histogram of P_Stay distribution

Top 10 likely leavers and loyal employees listed

✅ Results
Task	Model	Key Metric	Score
Attrition	Logistic Regression	ROC AUC	~0.80+
Salary Prediction	Random Forest	R² Score	~0.85+
Attrition Risk	P_Leave Distribution	Top 10 leavers	Identified

📈 Business Value
This project simulates how HR departments can:

Proactively identify high-risk employees.

Estimate retention costs.

Focus retention efforts on employees with high predicted salaries and high attrition risk.

Author: Yashika Gupta
Institution: Mahindra University, Hyderabad
