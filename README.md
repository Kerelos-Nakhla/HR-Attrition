# HR Attrition & Workforce Risk Intelligence Dashboard

<p align="center">
  <b>Predictive Talent Analytics, Turnover Root-Cause Modeling & Retention Intelligence in Power BI</b>
</p>

---

## Executive Overview
The **HR Attrition & Workforce Intelligence Dashboard** is an executive people-analytics system built to uncover the hidden drivers behind employee departures, benchmark compensation competitiveness, and quantify turnover financial risk. 

### Core Workforce Metrics (Calculated from Actual Dataset)
- **Total Monitored Workforce:** 1,470 active & departed employees
- **Total Departures (Attrition):** 237 employees
- **Overall Attrition Rate:** **16.12%** (237 departed / 1,470 total)
- **Retained Workforce:** 1,233 employees (83.88% retention rate)
- **Key Risk Indicators:** OverTime exposure, job role satisfaction gradients, commute distance, and promotion latency

---

## Business Problem & Key Findings
1. **OverTime Disproportionate Impact:** Employees working overtime experience significantly higher attrition than non-overtime peers.
2. **Tenure & Promotion Latency:** Departures spike sharply between years 2 and 4 at the company when role stagnation and lack of promotions occur.
3. **Single vs. Dual Satisfaction Drivers:** Environmental and relationship satisfaction compound; low satisfaction across multiple facets elevates risk scores exponentially.

---


## Business Questions & Key Analytical Takeaways
- **Attrition scale:** 237 of 1,470 employees left the organization, meaning roughly **1 in every 6.2 employees** in the dataset departed.
- **Retention baseline:** The retained workforce represents **83.88%** of the population, establishing the baseline for comparing departments, roles, tenure bands, and other segments.
- **Risk-driver structure:** The analysis focuses on overtime, satisfaction, commute distance, tenure, and promotion latency, allowing attrition to be examined as a combination of workload, engagement, and career-progression factors.
- **Career-stage focus:** The dashboard specifically examines the 2–4 year tenure window and promotion timing, supporting a targeted investigation of where attrition pressure is concentrated.

## Dashboard Visual Tour & Storytelling

### 1. Landing
<p align="center">
  <img src="./Dashboard%20Previews/Landing%20Page.png" alt="HR Attrition — Landing" width="95%">
</p>

### 2. Overview
<p align="center">
  <img src="./Dashboard%20Previews/Overview%20Page.png" alt="HR Attrition — Overview" width="95%">
</p>

### 3. Driver
<p align="center">
  <img src="./Dashboard%20Previews/Drivers%20Page.png" alt="HR Attrition — Drivers" width="95%">
</p>

### 4. Demographic
<p align="center">
  <img src="./Dashboard%20Previews/Demographic%20Page.png" alt="HR Attrition — Demographics" width="95%">
</p>

### 5. Career & Pay
<p align="center">
  <img src="./Dashboard%20Previews/Career%20%26%20Pay%20Page.png" alt="HR Attrition — Career & Pay" width="95%">
</p>

### 6. Risk Intelligence
<p align="center">
  <img src="./Dashboard%20Previews/1-%20Risk%20Intelligence%20Page.png" alt="Risk Intelligence — Executive Summary" width="95%">
</p>
<p align="center">
  <img src="./Dashboard%20Previews/2-%20Risk%20Intelligence%20Page.png" alt="Risk Intelligence — Tenure & Promotion Matrix" width="95%">
</p>
<p align="center">
  <img src="./Dashboard%20Previews/3-%20Risk%20Intelligence%20Page.png" alt="Risk Intelligence — Departmental Breakdown" width="95%">
</p>
<p align="center">
  <img src="./Dashboard%20Previews/4-%20Risk%20Intelligence%20Page.png" alt="Risk Intelligence — Compensation & Performance Analysis" width="95%">
</p>
<p align="center">
  <img src="./Dashboard%20Previews/5-%20Risk%20Intelligence%20Page.png" alt="Risk Intelligence — Predictive Flight Risk Scores" width="95%">
</p>

---

## Data Architecture & Model
The semantic data model is structured in a Kimball-style Star Schema centered on employee lifecycle records and workplace sentiment.

### Model Representation
<p align="center">
  <img src="./Dashboard%20Previews/Model.png" alt="HR Attrition Analytics — Data Model" width="95%">
</p>

- **Fact Table (`fact_attrition`):** 1,470 records encompassing 30 core features including tenure, salary bands, promotion years, satisfaction indices, and risk score calculations.
- **Dimension Tables:**
  - `dim_department`: R&D, Sales, and Human Resources organizational hierarchies.
  - `dim_job`: Job roles, seniority levels, and responsibilities.
  - `dim_education`: Educational degrees and study fields.
  - `dim_business_travel`: Non-travel, travel frequently, and travel rarely.
  - `dim_employee`: Core demographic profiles.

---

## Tools & Technologies
- **Business Intelligence:** Microsoft Power BI Desktop
- **Data Analytics:** DAX (Dynamic Flight Risk Scores, Attrition Rate % measures, Churn Segments)
- **Data Engineering:** Power Query (M) data cleaning and feature engineering

---

## License & Usage
This repository is released under the [MIT License](LICENSE). Developed by **Kerelos Nakhla** — Data Analyst & BI Developer.
