# Campus Training Analytics  
**Python • Pandas • SQL • Excel / Google Sheets**

## Project Overview
This project analyzes training performance data for **300 students** across **four engineering colleges** to evaluate learning outcomes, engagement, and participation trends. It simulates a real-world analytics workflow used by campus training providers, EdTech companies, and corporate learning teams.

The project demonstrates a complete **end-to-end analytics pipeline**:
- Data generation
- Data cleaning & transformation (Python, pandas)
- KPI calculation using SQL (SQLite)
- Reporting and visualization in Excel / Google Sheets

---

## Colleges Covered
- **Malla Reddy Engineering College** (80 students)  
- **CMR College of Engineering** (80 students)  
- **Gunupur College of Engineering** (100 students)  
- **Sreedevi Engineering College** (40 students)  

All students belong to **CS or IT** departments and the **2024** batch.

---

## Dataset Description
Each student is enrolled in **1–3 courses**. The dataset tracks:
- Course enrollments
- Modules completed vs. total modules
- Scores (0–100)
- Attendance percentage
- Enrollment status (Completed, In Progress, Dropped)
- Enrollment month

From this data, the following KPIs are computed:
- **Completion Rate**
- **Pass Rate**
- **Average Score**
- **Monthly Participation Trends**

---

## Data Processing (Python & Pandas)
Using Python and pandas, the following transformations were performed:
- Merged student, course, and enrollment data into a single fact table
- Engineered analytical fields:
  - `is_completed`
  - `is_pass`
  - `completion_pct`
  - `month (YYYY-MM)`
- Aggregated performance metrics by:
  - College
  - Course
  - Month

---

## SQL Analytics
The cleaned dataset was loaded into **SQLite**, and SQL was used to compute KPIs such as:

- Completion rate by college  
- Pass rate by college  
- Average score by course  
- Dropout rate by college  
- Monthly enrollment and performance trends  

Example:
```sql
SELECT 
  college, 
  ROUND(AVG(is_completed) * 100, 2) AS completion_rate
FROM enrollments
GROUP BY college;
