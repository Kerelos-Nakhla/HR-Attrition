# 👥 HR Attrition & Workforce Risk Intelligence Dashboard

<p align="center">
  <b>Predictive Talent Analytics, Turnover Root-Cause Modeling & Retention Intelligence in Power BI</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black" alt="Power BI" />
  <img src="https://img.shields.io/badge/DAX-People_Analytics-blue?style=for-the-badge" alt="DAX" />
  <img src="https://img.shields.io/badge/Retention-Risk_Modeling-critical?style=for-the-badge" alt="Retention Risk" />
  <img src="https://img.shields.io/badge/Data_Modeling-Star_Schema-success?style=for-the-badge" alt="Star Schema" />
</p>

---

## 📌 Executive Overview
The **HR Attrition & Workforce Intelligence Dashboard** is an executive people-analytics system built to uncover the hidden drivers behind employee departures, benchmark compensation competitiveness, and quantify turnover financial risk.

### 📊 Core Key Performance Indicators (KPIs)
- 👥 **Total Monitored Workforce:** **1,470 active & departed employees**
- 🚪 **Total Departures (Attrition):** **237 employees**
- ⚠️ **Overall Attrition Rate:** **16.12%** (237 departed / 1,470 total)
- 🛡️ **Retained Workforce:** **1,233 employees** (83.88% retention rate)
- ⏰ **Primary Risk Catalysts:** OverTime exposure, job role satisfaction gradients, commute distance, and promotion latency

---

## 🎯 Business Problem & Objectives
1. ⏰ **OverTime Disproportionate Impact:** Measure the turnover multiplier among employees working frequent overtime compared to standard-schedule peers.
2. ⏳ **Tenure & Promotion Latency:** Analyze career milestone drop-offs, especially role stagnation during the critical 2–4 year tenure window.
3. 🎯 **Multi-Factor Satisfaction Drivers:** Quantify how environmental, work-life balance, and relationship satisfaction compound to elevate flight risk.
4. 💼 **Departmental & Role Exposure:** Isolate departments with elevated turnover (Sales, R&D, HR) to enable proactive retention interventions.

---

## 💡 In-Depth Data Analysis & Business Insights
- 🚨 **OverTime as the Primary Flight Trigger:** Employees working overtime experience an attrition rate of **30.5%**, compared to just **10.4%** for non-overtime staff—a **nearly 3x turnover multiplier**.
- ⏳ **The 2–4 Year Danger Zone:** Departures peak sharply between years 2 and 4. Employees with 3+ years since their last promotion have a **2.4x higher probability** of exiting.
- 🧭 **Commute Distance Friction:** Staff commuting more than 15 miles exhibit a 22.4% attrition rate versus 13.1% for those living closer, underscoring the retention power of flexible/hybrid work.
- 💰 **Compensation vs. Role Engagement:** Departure rates for entry-to-mid roles (Sales Representatives and Laboratory Technicians) are significantly more sensitive to pay equity than senior engineering roles.

---

## 🖼️ Dashboard Visual Tour & Storytelling

### 1. Landing Page
<p align="center">
  <img src="./Dashboard%20Previews/Landing%20Page.png" alt="HR Attrition — Landing" width="95%">
</p>

### 2. Executive Overview
<p align="center">
  <img src="./Dashboard%20Previews/Overview%20Page.png" alt="HR Attrition — Overview" width="95%">
</p>

### 3. Drivers Analysis
<p align="center">
  <img src="./Dashboard%20Previews/Drivers%20Page.png" alt="HR Attrition — Drivers" width="95%">
</p>

### 4. Demographic Breakdown
<p align="center">
  <img src="./Dashboard%20Previews/Demographic%20Page.png" alt="HR Attrition — Demographics" width="95%">
</p>

### 5. Career Progression & Compensation
<p align="center">
  <img src="./Dashboard%20Previews/Career%20%26%20Pay%20Page.png" alt="HR Attrition — Career & Pay" width="95%">
</p>

### 6. Risk Intelligence Suite (Multi-Angle Deep Dives)
<p align="center">
  <img src="./Dashboard%20Previews/1-%20Risk%20Intelligence%20Page.png" alt="Risk Intelligence — Executive Summary" width="95%">
</p>
<p align="center">
  <img src="./Dashboard%20Previews/2-%20Risk%20Intelligence%20Page.png" alt="Risk Intelligence — Tenure & Stagnation" width="95%">
</p>
<p align="center">
  <img src="./Dashboard%20Previews/3-%20Risk%20Intelligence%20Page.png" alt="Risk Intelligence — Departmental Exposure" width="95%">
</p>
<p align="center">
  <img src="./Dashboard%20Previews/4-%20Risk%20Intelligence%20Page.png" alt="Risk Intelligence — Compensation & Commute" width="95%">
</p>
<p align="center">
  <img src="./Dashboard%20Previews/5-%20Risk%20Intelligence%20Page.png" alt="Risk Intelligence — Predictive Cohorts" width="95%">
</p>

---

## 🏗️ Data Architecture & Star Schema
The data model connects employee profiles to key workplace and organizational dimensions:

- **Fact Table:**
  - `fact_attrition` — Employee records, attrition status (Yes/No), salary, overtime indicator, performance rating, tenure, and satisfaction scores
- **Dimension Tables:**
  - `dim_employee` — Demographic details, marital status, gender, age cohorts
  - `dim_department` — Organizational units (Research & Development, Sales, Human Resources)
  - `dim_job` — Job roles, job levels, and compensation bands
  - `dim_education` — Academic field, education level achieved
  - `dim_business_travel` — Travel frequency (Non-Travel, Travel_Rarely, Travel_Frequently)

### 📐 Model Representation
<p align="center">
  <img src="./Dashboard%20Previews/Model.png" alt="HR Attrition Analytics — Data Model" width="95%">
</p>

---

## 🛠️ Tools & Technologies
- 📊 **Power BI Desktop:** Interactive HR dashboards, cohort decomposition trees, scenario slicers
- 📐 **DAX (Data Analysis Expressions):** Attrition Rate %, Flight Risk Index, Promotion Latency Cohorts, Average Tenure
- 🧹 **Power Query (M):** Survey data encoding, categorical grouping, demographic profiling
- 🎯 **People Analytics:** Talent retention modeling, compensation benchmarking, workload stress metrics

---

## 📜 License & Author
- **Author:** Kerelos Nakhla ([GitHub](https://github.com/Kerelos-Nakhla))
- **License:** MIT License
