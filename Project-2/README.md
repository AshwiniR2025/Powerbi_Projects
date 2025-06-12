# 📊 Insurance Data Analysis - Power BI Project

This project involves analyzing insurance policy data and customer feedback using **Power BI** with integrated sentiment analysis and SQL-based data modeling.

---

## 📁 Project Files

| File Name                        | Description                                                |
|----------------------------------|------------------------------------------------------------|
| `InsuranceData-Project2.csv`     | CSV file containing policy and claims data with the following columns:<br>• PolicyNumber<br>• CustomerID<br>• Gender<br>• Age<br>• PolicyType<br>• PolicyStartDate<br>• PolicyEndDate<br>• PremiumAmount<br>• CoverageAmount<br>• ClaimNumber<br>• ClaimDate<br>• ClaimAmount<br>• ClaimStatus |
| `Insurance Customer Feedback.xlsx` | Excel file with customer feedback data:<br>• Customer Name<br>• Feedback |
| `PROJECT2-INSURANCE.pbix`        | Power BI report file with visuals, transformations, and insights |

---

## 🔁 Project Flow

1. Loaded the CSV file into **SQL Server**, and connected it to **Power BI Desktop**.
2. Validated column data types and performed:
   - Column Profiling  
   - Column Distribution  
   - Column Quality Checks  
   using **Power Query Editor**.
3. Added **dropdown slicers** for `Policy Number`, `Claim Number`, and `Customer ID`.
4. Inserted a report title: **"Prism Insurance Pvt. Ltd."**.
5. Created **card visuals** for:
   - Total `Premium Amount`
   - Total `Claim Amount`
   - Total `Coverage Amount`
6. Used **multi-row cards** to display gender-wise customer count (`Male`, `Female`).
7. Visualized **Claim Status** (`Settled`, `Pending`, `Rejected`) using a **ribbon chart**.
8. Displayed `Premium Amount` by `Policy Type` using a **bar chart**.
9. Created a new **Age Group** column with logic:
   - Young (≤ 25)
   - Adult (> 25)
   - Elder (> 60)
10. Analyzed `Claim Amount` across age groups.
11. Created a new column for **Customer Status**:
    - `Active` if `PolicyEndDate` > today
    - `Inactive` otherwise
12. Compared **Active vs. Inactive customers** using a bar chart.
13. Used a **table visual** to display `Policy Type`, `Coverage Amount`, and `Claim Status`.
14. Configured **scheduled data refresh** at **7:30 PM daily** in Power BI Service.
15. Implemented a **drill-through filter** on `Policy Type` for in-depth data views.
16. For sentiment analysis:
    - Imported feedback data from Excel.
    - Used **AI Insights** → **Text Analytics** to compute sentiment scores.
    - Scores near 1.0 = Positive; near 0 = Negative.
17. Created a new **Sentiment Category** column:
    - `Excellent` (score > 0.8)
    - `Good` (score > 0.6)
    - `Needs Improvement` (≤ 0.6)
18. Visualized customer feedback using:
    - **Word cloud** (frequent terms)
    - **Bar chart** (sentiment category totals)
19. Published the report to **Power BI Service** and built a dashboard focusing on key visuals.

---

## 📈 Key Performance Indicators (KPIs)

### ✅ Business KPIs

1. **Total Premium Collected**  
   - *Metric:* `Sum(PremiumAmount)`  
   - *Insight:* Total revenue from issued policies.

2. **Total Claim Amount Processed**  
   - *Metric:* `Sum(ClaimAmount)`  
   - *Insight:* Payout value of customer claims.

3. **Total Coverage Amount Issued**  
   - *Metric:* `Sum(CoverageAmount)`  
   - *Insight:* Total insured value across all policies.

4. **Claim Status Distribution**  
   - *Metric:* Count of `ClaimStatus` (Settled, Pending, Rejected)  
   - *Insight:* Performance and resolution rate of claims.

5. **Active vs. Inactive Customers**  
   - *Metric:* Count based on policy expiration  
   - *Insight:* Customer engagement and policy renewals.

---

### ✅ Demographic KPIs

1. **Customers by Age Group**  
   - *Metric:* Count by derived column (`Young`, `Adult`, `Elder`)  
   - *Insight:* Age-wise segmentation of policyholders.

2. **Gender Distribution**  
   - *Metric:* Count of `Gender`  
   - *Insight:* Gender demographics of the customer base.

---

### ✅ Sentiment Analysis KPIs

1. **Feedback Sentiment Distribution**  
   - *Metric:* Count of feedback labeled as `Excellent`, `Good`, `Needs Improvement`  
   - *Insight:* Quality of service perception from customers.

2. **Most Frequent Feedback Terms**  
   - *Metric:* Word cloud from feedback text  
   - *Insight:* Common topics, praises, or complaints from customers.

---


