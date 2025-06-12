# POWERBI_HR_ANALYTICS
# 🧑‍💼 HR Analytics Dashboard – Power BI Project

This repository showcases an interactive **HR Analytics Dashboard** built using **Power BI**. It leverages a structured HR dataset and addresses real-world business questions using **DAX (Data Analysis Expressions)**, including **measures**, **calculated columns**, and **calculated tables**.

---

## 📁 Dataset Information

- **Source**: [GitHub Dataset – hr_employee_data_with_nationality.csv](https://github.com/slidescope/data/blob/master/hr_employee_data_with_nationality.csv)
- **Rows**: 300
- **Format**: CSV

### 📌 Columns Description:

| Column | Description |
|--------|-------------|
| EmployeeID | Unique identifier |
| Name | Mock full name |
| Department | HR, Sales, IT, Finance, Marketing, R&D |
| Gender | Male, Female, Other |
| Age | Age (20–60) |
| Education | Bachelor’s, Master’s, PhD, Diploma |
| JobRole | Analyst, Manager, Developer, Executive, etc. |
| MonthlyIncome | 20,000 to 120,000 |
| YearsAtCompany | 0–40 |
| Attrition | Yes / No |
| PerformanceRating | Scale of 1–5 |
| OverTime | Yes / No |
| MaritalStatus | Single / Married / Divorced |
| WorkLifeBalance | Scale of 1–4 |
| TrainingTimesLastYear | 0–10 |

---

## 🎯 Business Questions Answered

| # | Question | Visualization Type | Example Insight |
|---|----------|--------------------|------------------|
| 1 | What is the overall attrition rate? | Card / KPI | e.g., 18% attrition |
| 2 | Which departments have the highest attrition? | Bar Chart | Sales = 30%, IT = 12% |
| 3 | Attrition vs. Years at Company? | Line / Scatter Chart | High attrition < 3 years |
| 4 | Income by Department? | Bar / Box Plot | Finance has highest avg salary |
| 5 | Do overtime employees report poor WLB? | Matrix / Stacked Bar | Mostly WLB ratings 1–2 |
| 6 | Gender distribution by department? | Donut / Stacked Column | Detect imbalance |
| 7 | Attrition vs Performance rating? | Clustered Bar Chart | Rating 2 has high attrition |
| 8 | Avg training hours per department? | Bar Chart | R&D = 8 hrs, HR = 3 hrs |
| 9 | Age group with highest attrition? | Histogram | 25–35 age group highest |
| 10 | Marital status vs Attrition/Income? | Pie / Bar Charts | Singles show higher attrition |

---

## 🧠 DAX: Measures, Columns & Tables

This project uses the full power of DAX to compute insights dynamically.

### ✅ When to Use What

| Type | Purpose |
|------|---------|
| **Calculated Column** | Row-level static data (e.g., Age Band) |
| **Measure** | Dynamic aggregations (e.g., Avg Income) |
| **Calculated Table** | Filtered/aggregated table for relationships or summaries |

---

## 📌 Sample DAX Formulas

 1. 🔢 **Attrition Rate (Measure)**

```dax
Attrition Rate = 
DIVIDE(
    CALCULATE(COUNTROWS(EmployeeData), EmployeeData[Attrition] = "Yes"),
    COUNTROWS(EmployeeData)
)
 2🎯 Age Band (Calculated Column)
dax
Copy
Edit
Age Band = 
SWITCH(TRUE(),
    EmployeeData[Age] <= 30, "20-30",
    EmployeeData[Age] <= 40, "31-40",
    EmployeeData[Age] <= 50, "41-50",
    "51+"
)
3. 💰 Average Income (Measure)
dax
Copy
Edit
Avg Income = AVERAGE(EmployeeData[MonthlyIncome])
4. 📄 Attrited Employees Table
dax
Copy
Edit
Attrited Employees = 
FILTER(EmployeeData, EmployeeData[Attrition] = "Yes")
5. 🏷️ Tenure Category (Column)
dax
Copy
Edit
Tenure Category = 
SWITCH(TRUE(),
    EmployeeData[YearsAtCompany] <= 2, "New",
    EmployeeData[YearsAtCompany] <= 5, "Mid",
    "Experienced"
)
6. ⏱️ Total Overtime Employees (Measure)
dax
Copy
Edit
Total Overtime = 
CALCULATE(
    COUNTROWS(EmployeeData),
    EmployeeData[OverTime] = "Yes"
)
7. 📉 % of Poor WLB Who Do Overtime (Measure)
dax
Copy
Edit
Poor WLB Overtime % = 
DIVIDE(
    CALCULATE(COUNTROWS(EmployeeData), 
              EmployeeData[WorkLifeBalance] <= 2,
              EmployeeData[OverTime] = "Yes"),
    CALCULATE(COUNTROWS(EmployeeData), EmployeeData[WorkLifeBalance] <= 2)
)
8. 🥇 Income Rank Within Department (Calculated Column)
dax
Copy
Edit
Income Rank = 
RANKX(
    FILTER(EmployeeData, EmployeeData[Department] = EARLIER(EmployeeData[Department])),
    EmployeeData[MonthlyIncome],
    ,
    DESC,
    Dense
)
9. 🌟 High Performers by Age Band (Measure)
dax
Copy
Edit
High Performers by Age Band = 
CALCULATE(
    COUNTROWS(EmployeeData),
    EmployeeData[PerformanceRating] >= 4
)
10. 🧾 Department Summary Table
dax
Copy
Edit
Dept Summary = 
SUMMARIZE(
    EmployeeData,
    EmployeeData[Department],
    "Avg Income", AVERAGE(EmployeeData[MonthlyIncome]),
    "Avg Tenure", AVERAGE(EmployeeData[YearsAtCompany])
)
🛠 Tools & Technologies Used
Tool	Purpose
Power BI Desktop	Report building, DAX calculations
Power Query	Data transformation
DAX	Calculated fields, measures, KPIs
GitHub	Project versioning and documentation

📁 Project Files
bash
Copy
Edit
/HR-Analytics-PowerBI
│
├── HR_Analytics_Dashboard.pbix        # Power BI report file
├── HR_Employee_Data.csv               # Raw dataset (300 rows)
├── README.md                          # Project documentation
🎓 Learning Outcomes
Real-world HR KPI dashboard development

Mastery of DAX: measures, calculated columns, and tables

Data modeling and filtering in Power BI

Deriving insights from employee attrition trends, income, and demographics

📜 License
This project is created for educational and portfolio purposes. Dataset belongs to the original ColorsTech article and GitHub-hosted dataset.

🙌 Acknowledgements
Dataset and questions by ColorsTech

Tutorial inspiration: YouTubeChannel: https://www.youtube.com/@Colorstech
Video:https://www.youtube.com/watch?v=bQOPKpT0xa8
