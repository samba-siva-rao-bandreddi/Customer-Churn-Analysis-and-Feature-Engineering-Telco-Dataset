#📝 Project Report: Customer Churn Prediction (Telco Dataset)
📊 1. Exploratory Data Analysis (EDA)
Data Summary:
Rows: 7,043 customers

Features: 21 variables (categorical and numerical)

Target Variable: Churn (Yes/No → Converted to 1/0)

Key Class Distribution:
Churned: ~26.5%

Not Churned: ~73.5%
✅ Class imbalance detected — potential need for resampling techniques during model training.

🧹 2. Data Cleaning & Preparation
TotalCharges was converted to numeric (had nulls & strings).

11 missing values were found in TotalCharges for customers with 0 tenure → filled with 0.

Converted Churn to binary (0/1).

📈 3. Univariate & Bivariate Analysis
Key Insights:
Tenure:

Churned: Avg ~18 months

Non-Churned: Avg ~37.6 months
👉 Newer customers are more prone to churn.

MonthlyCharges:

Churned customers pay more on average.

Positive correlation (+0.19) with churn.

TotalCharges:

Negatively correlated (-0.20) with churn.

Long-term customers contribute more revenue.

Contract Type:

Month-to-month contracts show significantly higher churn.

Payment Method:

Electronic check users churn the most.

Services:

Fiber optic users churn more than DSL.

Customers with no technical support or online security churn more.

🔍 4. Correlation & Statistical Tests
Top Correlated with Churn:

Tenure (-0.35)

MonthlyCharges (+0.19)

TotalCharges (-0.20)

Statistical Testing:

T-tests show tenure, monthly, and total charges differ significantly between churned vs. non-churned customers.

Chi-square tests found most categorical features (e.g., Contract, TechSupport) to be statistically associated with churn.

Gender and PhoneService were not statistically significant.

🧠 5. Feature Engineering
Created several new features:

ServiceCount: Count of services used

CostPerService: MonthlyCharges / ServiceCount

CustomerLifetimeValue: MonthlyCharges × Tenure

ChargeToTenureRatio: MonthlyCharges / Tenure

TenureGroup: Quartile-based tenure segmentation

Binary flags for combined services:

HasTechAndSecurity

HasAllStreamingServices

✅ Several engineered features showed strong correlation and distributional separation with churn.

📉 6. Outlier Detection
IQR method applied.

No significant outliers detected in tenure, MonthlyCharges, or TotalCharges.

🌟 7. Feature Importance (Random Forest)
Top 10 Important Features (Random Forest Classifier):

tenure

MonthlyCharges

Contract_Two year

Contract_One year

OnlineSecurity_No

TechSupport_No

InternetService_Fiber optic

TotalCharges

PaymentMethod_Electronic check

PaperlessBilling_Yes

These confirm the EDA findings and support their inclusion in modeling.

✅ Summary of Key Drivers of Churn
Short Tenure

High Monthly Charges

Month-to-Month Contracts

Lack of Tech Support / Online Security

Fiber Optic Users

Electronic Check Payment

Paperless Billing

🔄 Next Recommended Steps
Model Building:

Try multiple models (Random Forest, XGBoost, Logistic Regression, etc.)

Address class imbalance using SMOTE or class weights.

Model Evaluation:

Use ROC-AUC, Precision-Recall, and F1-score.

Hyperparameter Tuning:

Apply Grid Search / Random Search.

Deploy and Monitor:

Use in a production environment to score new customers.
