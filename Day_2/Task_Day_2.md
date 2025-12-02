# 📘 DAY 2 – Pandas God Mode 
---

## 🗂 Agenda for Day 2
- Transform raw Telco churn data into an optimized Pandas DataFrame  
- Apply FAANG-style memory + speed improvements  
- Engineer advanced analytical features using `assign()`  
- Perform tenure-based cohort analysis using `groupby()`  
- Compute revenue-at-risk metrics  
- Build senior-level churn visualization with Seaborn  
- Use `query()` and `eval()` for expressive & performant filtering  
- Produce metrics that demonstrate business impact  

---

## ✅ WHAT HAS BEEN DONE (Summary of Completed Work)

### **1. Data Preprocessing**
- Loaded Telco Customer Churn dataset  
- Converted `TotalCharges` to numeric using `pd.to_numeric(errors='coerce')`  
- Cleaned and validated data for analysis  

### **2. Feature Engineering Using `assign()`**
Created high-value and analytical features:
- `TenureBin`: binned tenure into 6-month groups using `pd.cut`  
- `IsHighValue`: customers with MonthlyCharges > 90 and tenure > 60  
- `ChurnFlag`: numerical churn indicator (1 for Yes, 0 for No)  

### **3. Cohort Analysis with Groupby**
Using an advanced chained pipeline:
- Calculated **ChurnRate**, **Churned count**, and **customer count per bucket**  
- Engineered **RevenueAtRisk** using a lambda inside `.assign()`  
- Rounded output for readability using `.round(3)`  
- Produced an executive-ready churn summary table  

### **4. Query-Based Filtering**
Filtered high-risk customers using:
```python
df.query("tenure > 60 and MonthlyCharges > 90 and Churn == 'Yes'")
