# 📋 Agenda — Day 3: SQL God Mode 

1. **Load & Prepare Data**
   - Import Telco churn dataset  
   - Create in-memory SQLite database  
   - Clean and convert missing `TotalCharges`  
   - Add numeric `TotalCharges_Num` column

2. **Build Base Window Functions**
   - `ROW_NUMBER()` for ranking within tenure  
   - `LAG()` to track previous churn  
   - `NTILE(4)` to assign tenure quartiles  

3. **Define High-Value Segment**
   - Filter: `tenure > 60` AND `MonthlyCharges > 90`  
   - Focus on long-tenure, high-revenue customers  

4. **Aggregate Customer Risk Metrics**
   - Total customers per quartile  
   - Total churned  
   - Annual loss per churner  
   - Revenue at risk (annualized)

5. **Add Advanced Window Functions**
   - Cumulative churn  
   - Cumulative revenue at risk (Cr)

6. **Execute Multi-CTE SQL Query**
   - Pipeline: `ranked → high_value → agg → final_select`  
   - Window functions applied on aggregates  
   - Sorted by revenue risk

7. **Visualize Output**
   - Revenue at Risk (Bar Chart)  
   - Cumulative Churn & Revenue Risk (Line Chart)

8. **Extract Insights**
   - Identify high-risk customer segments  
   - Quantify compounding revenue risk  
   - Demonstrate advanced SQL mastery


---

# ✅ WHAT HAS BEEN DONE (Summary of Completed Work)

### **Data Preparation**
- Loaded Telco churn CSV into an in-memory SQLite database  
- Replaced blank `TotalCharges` where tenure = 0  
- Created numeric version: `TotalCharges_Num`  
- Ensured data is clean for SQL analytics

### **SQL Logic Built**
- Added multiple window functions:
  - `ROW_NUMBER()`
  - `LAG()`
  - `NTILE(4)`
- Defined `high_value` segment for deeper churn & revenue analysis
- Added separate aggregation CTE (`agg`) to support window functions on aggregated data

### **Advanced Analytics Implemented**
- **Cumulative churn analysis** per tenure quartile  
- **Cumulative revenue at risk** (in crores)  
- Annualized revenue loss calculations standardized

### **Visualizations Created**
- Revenue at Risk per tenure quartile (bar)  
- Cumulative metrics across quartiles (line)

### **Errors Fixed**
- SQL syntax error inside Python cell  
- Window function over aggregate error (SQLite limitation)  
- Missing columns during plot  
- Moved window ops to final SELECT after aggregation  

---

# 🧠 SUMMARY: What You Learned

### **1. Data Cleaning Techniques**
- Using `NULLIF()` and `CAST()` to convert empty strings  
- How to replace missing values conditionally in SQL  
- Importance of numeric vs text fields for analytics

### **2. Window Function Mastery**
- Ranking customers (`ROW_NUMBER`)  
- Comparing with previous rows (`LAG`)
- - Separating responsibilities:
- CTE 1: Window functions  
- CTE 2: Segmentation  
- CTE 3: Aggregation  
- Final: Window-over-aggregate reporting

### **4. Handling SQLite Limitations**
- SQLite cannot apply window functions directly to aggregates  
- Fix: compute aggregates first in `agg`, then apply window functions

### **5. Python + SQL Integration**
- Running complex SQL inside Pandas  
- Plotting results with `DataFrame.plot()`  
- Working with bar & line charts for analytics reporting

### **6. Business Insight Extraction**
- Finding long-tenure, high-value customers  
- Quantifying annualized churn impact  
- Calculating revenue at risk in crores  
- Understanding compounding loss across quartiles

---


- Creating quartiles (`NTILE`)  
- Building running totals with `SUM() OVER()`

### **3. Multi-CTE Analytical SQL Design**
- How to structure queries like:

