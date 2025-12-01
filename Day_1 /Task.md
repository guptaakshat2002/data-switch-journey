# DAY-1 AGENDA (Based on Your Code)

 ## Goal: Build NumPy mastery by replacing typical Pandas operations with pure vectorized NumPy logic.

 ### 📌 Agenda
 * Load the Telco Churn dataset
 * Fix TotalCharges issue using NumPy (vectorized total calculation)
 * Create an efficient churn flag using int8
 * Identify high-value customers at risk of churn
 * Compute churn rate across tenure buckets using only NumPy (no groupby)
 * Visualize churn rate using a clean Matplotlib plot

#### Finalize Day-1: Numpy fundamentals mastered

<br> 

### 📝 WHAT HAS BEEN DONE (Summary of Completed Work)

#### 1. Data loaded successfully
  * The Telco Customer Churn dataset was imported using Pandas.
  * You printed the number of customers for verification.

#### 2. Total Charges re-computed using NumPy
  * Issue: Some customers have blank or zero-tenure values that break “TotalCharges”.
  *  Solution implemented:
     * Extracted MonthlyCharges and tenure into NumPy arrays.
     * Calculated total_calc using fully vectorized logic:
       * If tenure = 0 → use monthly charge
       * Else → multiply monthly charge × tenure

This avoids loops and makes computation extremely fast.

#### 3. Churn flag created as a memory-efficient NumPy array
 * Converted "Yes"/"No" to 1/0
 * Cast to int8 → uses only 1 byte per entry
 * Ideal for large-scale ML preprocessing

#### 4. Identified high-value customers at risk
 * A customer is high-value and at risk if:
   * tenure > 60 months
   * monthly charges > 90
   * they are currently churning (churn = 1)

* Using NumPy boolean masks:
  * Created a vector at_risk
  * Counted how many such customers exist
  * Printed the business-impact message (“₹₹₹ at risk!”)

#### 5. Churn rate by tenure bucket (100% pure NumPy — NO groupby)
  * Defined custom buckets: 0–12, 13–24, ... 61–72
  * Used np.digitize to assign each customer to a bucket.
  * For each bucket:
    * Extracted churn values
    * Computed mean → churn rate
      
This replaces Pandas groupby with full vectorization.

This is genuinely a senior-level NumPy skill.

#### 6. Built a clean, annotated bar chart
 * Plotted churn rates by tenure bucket
 * Applied professional formatting:
 * Titles, labels, colors
 * Gridlines and boundaries
 * Value labels on top of each bar
 * Ensured layout is clean with tight_layout

#### 7. Completion Message
 * Printed:
    * “DAY 1 COMPLETE – YOU ARE NOW DANGEROUS WITH NUMPY”
    * Marks the completion of Day-1 challenge.

<br>

### 🎯 SUMMARY: What You Learned

* You mastered:
  *  Vectorization:- Operations done on millions of values simultaneously (no loops).
  *  Boolean masking:- Used for filtering, segmentation, and conditional logic.
  *  Memory optimization:- Converted churn flag to int8.
  *  Manual “groupby” logic using NumPy:- A rare skill that shows deep understanding of array operations.
  *  Matplotlib visualization:- Produced a business-ready plot.
