🏥 Healthcare Cost Prediction Using Machine Learning
📌 Project Overview

Rising healthcare costs pose significant challenges for payers and healthcare organizations. Identifying individuals at risk of incurring high medical expenses enables proactive care management, improved resource allocation, and cost containment.

This project develops and evaluates machine learning models to predict individual healthcare costs using demographic and health risk factors. The analysis focuses on model performance, interpretability, and alignment with real-world healthcare cost drivers.

🎯 Business Problem

Healthcare payers need to:

Forecast future medical costs

Identify high-cost members early

Understand the primary drivers of healthcare spending

Objective:
Predict annual healthcare costs and analyze key risk factors that contribute to high medical spending.

📊 Dataset

The project uses a publicly available Medical Insurance Cost dataset (insurance.csv) containing individual-level insurance cost records.

Features

age — age of the insured

sex — biological sex

bmi — body mass index

children — number of dependents

smoker — smoking status

region — geographic region

Target Variable

charges — annual medical insurance cost

⚠️ This dataset is a simplified proxy for real healthcare claims data and does not include diagnoses, procedures, pharmacy data, or longitudinal utilization history.

🧠 Methodology
1. Exploratory Data Analysis (EDA)

Analyzed cost distribution and identified strong right skew

Examined relationships between cost and key risk factors (age, BMI, smoking)

Identified smoking status as a major driver of cost variation

2. Feature Engineering

Log-transformed medical costs to address skewness

Created age groups and BMI categories to reflect clinical risk stratification

Engineered an interaction feature between smoking status and BMI

One-hot encoded categorical variables

3. Modeling

Trained and compared multiple regression models:

Linear Regression

Ridge & Lasso Regression

Random Forest Regressor

Gradient Boosting Regressor

Models were evaluated using a held-out test set.

4. Evaluation & Interpretation

Assessed model performance using MAE, RMSE, and R²

Conducted residual analysis to check for bias

Analyzed performance on high-cost members (top 20%)

Examined feature importance to identify cost drivers

📈 Model Performance

Final Model: Gradient Boosting Regressor

Metric	Value
MAE	~0.185
RMSE	~0.347
R²	~0.87

The final model explains approximately 87% of the variance in log-transformed healthcare costs, demonstrating strong predictive performance for tabular healthcare data.

🔍 Key Insights

Smoking-related risk, especially when combined with high BMI, is the strongest driver of healthcare cost

Age remains a significant predictor of medical spending

BMI and obesity-related features contribute meaningfully to cost prediction

Geographic region has minimal impact compared to behavioral and health risk factors

Prediction error increases for extreme high-cost cases, reflecting the inherent unpredictability of catastrophic healthcare spending

⚠️ Limitations

The dataset does not represent full claims data and lacks diagnoses, procedures, and longitudinal utilization

Results may not generalize directly to real payer systems without richer clinical and utilization features

High-cost outliers remain challenging to predict with simplified feature sets

🔮 Future Improvements

Incorporate longitudinal utilization and claims-level data

Add diagnosis and procedure-based risk features

Build classification models to identify high-cost members

Explore model explainability techniques such as SHAP values

Simulate deployment via an API or dashboard

🛠️ Technologies Used

Python

Pandas, NumPy

Scikit-learn

Matplotlib, Seaborn

Jupyter Notebook

## 📁 Project Structure

healthcare-cost-prediction/
├── data/
│ ├── raw/
│ └── processed/
├── notebooks/
│ ├── 01_eda.ipynb
│ ├── 02_feature_engineering.ipynb
│ ├── 03_modeling.ipynb
│ └── 04_evaluation.ipynb
├── models/
├── src/
├── README.md
└── requirements.txt

👤 Author

Shawn Beere
Healthcare Data Science Portfolio Project