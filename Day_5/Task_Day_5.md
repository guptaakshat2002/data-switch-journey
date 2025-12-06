# Day 5 — ML Model That Wins Offers 

## 📅 Agenda

  * Load & clean the Telco Customer Churn dataset
  * Reuse + extend Day-4 feature engineering
  * Build a high-AUC XGBoost model (<50 lines, production-ready)
  * Evaluate performance using ROC–AUC
  * Generate SHAP explainability plots
  * Commit & push final results to GitHub

<br>

## ✅ What Has Been Done (Summary of Completed Work)

### 1. Data Preparation
    
  * Loaded the Telco Churn dataset (WA_Fn-UseC_-Telco-Customer-Churn.csv)
  * Cleaned the TotalCharges column (converted to numeric + filled missing values)

### 2. Feature Engineering (10+ Pro Features)

  Created a high-signal feature set including:
        
  * Tenure, monthly charges, total charges
  * Tenure-per-charge ratio
  * Lifetime value ratio
  * High-value customer flag
  * New-customer risk score
  * Contract scoring (Month-to-month → highest risk)
  * Service combination count
  * Payment method risk
  * Fiber optic churn indicator
  * No-support flag
  * Binary target encoding

### 3. Train/Test Split
  
  80/20 split with class stratification

### 4. XGBoost Churn Model

Tuned for stability and performance:

  * 500 trees
  * Depth 4
  * LR = 0.02
  * Subsample = 0.85
  * AUC metric

### 5. Model Performance
  
  * Achieved AUC ≥ 0.875 consistently
  * High predictive stability across splits

### 6. SHAP Explainability
  
  * Generated SHAP values with TreeExplainer
  * Produced a global feature importance bar chart
  * Identified top churn drivers (Contract, Fiber, Tenure, Service Combo, etc.)

<br>


## 🧠 Summary: What You Learned

  * How to transform raw business data into predictive features that boost model AUC
  * Why ratio features and behavioral heuristics often outperform raw variables
  * How to train a production-ready XGBoost churn model in under 50 lines
  * How AUC reflects ranking performance for churn prediction
  * How to use SHAP to interpret tree-based models and explain predictions to stakeholders
  * How to produce portfolio-ready visualizations and code for interviews
  * How to maintain clean, version-controlled ML work using Git
