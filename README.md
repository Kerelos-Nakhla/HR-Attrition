# HR Attrition Analytics Dashboard | Power BI

An interactive **HR Analytics and Employee Attrition Dashboard** developed as part of the **GBS BI HUB – BI Developer HR Attrition Case Study** interview challenge.

The project analyzes employee attrition, workforce characteristics, job information, satisfaction, compensation, business travel, overtime, and career-related factors to identify patterns associated with employee turnover.

---

## 📌 Project Overview

Employee attrition can create significant operational and financial challenges for organizations. Understanding **who is leaving, where attrition is concentrated, and which employee characteristics are associated with higher turnover** can help HR teams investigate potential retention issues.

This project transforms employee-level data into an interactive Power BI solution that allows users to move from an executive-level overview to detailed employee analysis.

The final report contains three main sections:

* **Landing Page**
* **Executive Page**
* **Employee Details**

The dashboard was designed with a strong focus on both **analytical functionality and visual storytelling**, using **Figma for UI/dashboard design** and custom **HTML/CSS-based visuals inside Power BI** to create a more engaging user experience.

---

## 🎯 Business Problem

The objective is to analyze employee attrition and identify workforce segments with relatively high turnover.

The analysis focuses on questions such as:

* How many employees have left the organization?
* What is the overall attrition rate?
* Which job roles and departments have higher attrition?
* How does overtime relate to employee turnover?
* Does business travel appear to be associated with attrition?
* How do compensation and satisfaction differ between employees who stayed and those who left?
* Which employee characteristics require deeper investigation?

The dashboard is designed to support **exploration and investigation rather than simply displaying HR statistics**.

---

## 🎯 Project Objectives

* Measure overall employee attrition.
* Analyze attrition across departments and job roles.
* Investigate relationships between attrition and overtime.
* Analyze business travel patterns.
* Compare compensation between employees who stayed and employees who left.
* Evaluate employee satisfaction and performance indicators.
* Provide employee-level details for deeper investigation.
* Build an interactive, decision-oriented Power BI experience.
* Create a visually consistent dashboard interface using Figma.
* Enhance standard Power BI reporting with custom HTML/CSS visuals.

---

## 🛠️ Tools & Technologies

| Tool / Technology | Purpose                                                                            |
| ----------------- | ---------------------------------------------------------------------------------- |
| **Power BI**      | Data modeling, analytics, interactive dashboard development                        |
| **DAX**           | KPI calculations, analytical measures, calculated columns, and custom HTML content |
| **Power Query**   | Data preparation, transformation, table merging, and model preparation             |
| **Excel**         | Source dataset                                                                     |
| **Figma**         | Dashboard UI/UX design, layout planning, and visual design                         |
| **HTML/CSS**      | Custom visual presentation inside Power BI                                         |

---

## 📊 Dataset

The project uses an Excel dataset containing **1,470 employee records and 35 columns**.

The dataset contains employee demographic, organizational, compensation, satisfaction, performance, and employment-history attributes.

### Main Data Categories

| Category           | Examples                                                                                 |
| ------------------ | ---------------------------------------------------------------------------------------- |
| **Employee**       | Employee Number, Age, Gender, Marital Status                                             |
| **Organization**   | Department, Job Role, Job Level                                                          |
| **Compensation**   | Monthly Income, Monthly Rate, Daily Rate, Hourly Rate                                    |
| **Satisfaction**   | Environment Satisfaction, Job Satisfaction, Relationship Satisfaction, Work Life Balance |
| **Career History** | Total Working Years, Years at Company, Years in Current Role                             |
| **Employment**     | Attrition, Over Time, Business Travel                                                    |
| **Performance**    | Performance Rating, Job Involvement                                                      |
| **Development**    | Training Times Last Year, Percent Salary Hike                                            |

The source Excel file contains **no missing values** across the 1,470 records.

---

## 🔄 Data Preparation & Transformation

The data preparation process was implemented in **Power Query**.

Key transformations included:

1. Promoting the first row to column headers.
2. Renaming source columns into more readable business-friendly names.
3. Applying appropriate data types.
4. Creating relationships between the employee-level fact data and dimension tables.
5. Merging the source data with dimension tables using business keys.
6. Expanding the corresponding surrogate keys.
7. Removing redundant attributes from the fact table after the dimension keys were added.
8. Reordering columns to create a cleaner analytical structure.

Examples of renamed fields include:

```text
BusinessTravel      → Business Travel
DailyRate           → Daily Rate
DistanceFromHome    → Distance From Home
EmployeeNumber      → Employee Number
MonthlyIncome       → Monthly Income
OverTime            → Over Time
TotalWorkingYears   → Total Working Years
YearsAtCompany      → Years At Company
```

The transformation process separates descriptive employee attributes from the analytical fact table and prepares the data for the Power BI semantic model.

---

## 🏗️ Data Model

The Power BI model uses a **Snowflake-style dimensional structure**, with `FACT_Atrition` connected to multiple dimension tables.

### Fact Table

**FACT_Atrition**

Contains employee-level analytical attributes including:

* Employee Number
* Attrition
* Monthly Income
* Distance From Home
* Daily Rate
* Hourly Rate
* Monthly Rate
* Percent Salary Hike
* Total Working Years
* Years At Company
* Years In Current Role
* Years Since Last Promotion
* Years With Current Manager
* Training Times Last Year
* Satisfaction metrics
* Performance Rating
* Overtime status
* Stock Option Level

### Dimension Tables

#### DIM_Employee

* Employee Number
* Age
* Gender
* Marital Status

#### DIM_Business Travel

* Business Travel Key
* Business Travel

#### DIM_Department

* Department Key
* Department

#### DIM_Education

* Education Key
* Education
* Education Field

#### DIM_Job

* Job Key
* Job Level
* Job Role

### Relationships

The model connects the fact table to the dimensions through keys such as:

```text
DIM_Employee[Employee Number]
        ↓
FACT_Atrition[Employee Number]

DIM_Business Travel[Business Travel Key]
        ↓
FACT_Atrition[Business Travel Key]

DIM_Department[Department Key]
        ↓
FACT_Atrition[Department Key]

DIM_Education[Education Key]
        ↓
FACT_Atrition[Education Key]

DIM_Job[Job Key]
        ↓
FACT_Atrition[Job Key]
```

This structure allows descriptive attributes to be separated from the employee-level analytical data while maintaining a flexible model for reporting.

---

## 📐 KPIs & DAX Measures

The semantic model contains dedicated DAX measures for workforce and attrition analysis.

### Core KPIs

| KPI                                   | Definition                                            |
| ------------------------------------- | ----------------------------------------------------- |
| **Count Employees**                   | Total number of employees                             |
| **Count Employees Left**              | Employees where Attrition = Yes                       |
| **Employees Left %**                  | Employees who left divided by total employees         |
| **Count Employees Stay**              | Employees where Attrition = No                        |
| **Count Employees Works Over Time**   | Employees where Over Time = Yes                       |
| **Count Employees Works Over Time %** | Employees working overtime divided by total employees |
| **AVG Monthly Salary**                | Average monthly income                                |
| **AVG Overall Satisfaction**          | Average calculated satisfaction score                 |
| **AVG Employee Performance**          | Average performance rating                            |
| **AVG Distance From Home**            | Average employee distance from home                   |

### Example DAX

```DAX
Employees Left % =
DIVIDE(
    [Count Employees Left],
    [Count Employees]
)
```

The model also contains a calculated overall satisfaction score:

```DAX
CC Overall Satisfaction =
DIVIDE(
    FACT_Atrition[Environment Satisfaction]
        + FACT_Atrition[Job Satisfaction]
        + FACT_Atrition[Relationship Satisfaction]
        + FACT_Atrition[Work Life Balance],
    4
)
```

An employee status classification is also created:

```DAX
Employee Status =
IF(
    FACT_Atrition[Attrition] = "Yes",
    "Left",
    "Stay"
)
```

---

## 📊 Dashboard

### 1. Landing Page

The landing page acts as the entry point to the report and provides navigation into the analytical experience.

**Purpose:**

* Introduce the HR analytics solution.
* Provide a clear starting point for users.
* Navigate users toward the analytical sections.
* Establish the visual identity of the dashboard.

The page design was planned and refined using **Figma** before being implemented in Power BI.

---

### 2. Executive Page

The Executive Page provides a high-level view of the workforce and attrition situation.

It brings together KPIs and analytical visuals to help users understand:

* Overall employee population.
* Employees who left.
* Employee retention.
* Overtime patterns.
* Compensation.
* Satisfaction.
* Workforce characteristics.
* Attrition distribution across organizational dimensions.

The page is designed to help decision-makers identify areas that require deeper investigation.

---

### 3. Employee Details

The Employee Details page provides a more granular view of the employee population.

The report includes a custom employee directory built using a **DAX-generated HTML/CSS visual**.

The table presents information such as:

* Employee ID
* Gender
* Department
* Job Role
* Job Level
* Employee Status

Employee status is visually represented as **Stay** or **Left**, allowing users to scan employee-level information quickly.

The HTML-based approach provides greater control over the presentation than a standard Power BI table visual.

---

## 🎨 Dashboard Design & Visual Development

A major part of the project focused on combining **data analytics with professional dashboard design**.

### Figma

**Figma** was used during the dashboard design process to:

* Plan page layouts.
* Establish visual hierarchy.
* Design UI components.
* Refine spacing and alignment.
* Create a consistent dashboard interface.
* Plan the overall user experience before implementation.

### Custom HTML/CSS Visuals

Custom **HTML/CSS content generated through DAX** was used to create a more customized employee-level experience.

The HTML visual includes elements such as:

* Employee information.
* Employee status badges.
* Job-level indicators.
* Custom table styling.
* Dynamic content generated from Power BI data.

This demonstrates how Power BI can be extended beyond its standard visual library by combining **DAX, HTML, and CSS**.

---

## 🔎 Key Insights

The following findings are calculated directly from the 1,470 employee records.

### 1. Overall Attrition

There are **237 employees who left**, representing an overall attrition rate of approximately **16.1%**.

> **Business Meaning:**
> Attrition affects a meaningful portion of the workforce and provides a clear starting point for identifying higher-risk employee segments.

---

### 2. Overtime Is Strongly Associated With Higher Attrition

Employees working overtime have an attrition rate of approximately **30.5%**, compared with **10.4%** among employees who do not work overtime.

> **Business Meaning:**
> Workload and overtime should be investigated as potential factors contributing to employee turnover.

---

### 3. Frequent Business Travel Shows Higher Attrition

Employees who travel frequently have an attrition rate of approximately **24.9%**, compared with **8.0%** among employees who do not travel.

> **Business Meaning:**
> Frequent travel may represent an employee experience factor worth investigating alongside workload, role, and work-life balance.

---

### 4. Sales Representatives Have the Highest Attrition Rate

The **Sales Representative** role has an attrition rate of approximately **39.8%**, the highest among the job roles in the dataset.

> **Business Meaning:**
> This role represents a high-priority segment for deeper investigation into workload, compensation, career progression, and employee experience.

---

### 5. Employees Who Left Have Lower Average Monthly Income

Average monthly income is approximately:

* **$4,787** for employees who left.
* **$6,833** for employees who stayed.

> **Business Meaning:**
> Compensation appears to be an important factor to investigate, although the analysis alone does not establish causation.

---

## 💡 Business Recommendations

Based on the observed patterns, several areas could be investigated further:

### 1. Investigate Overtime

Review workload distribution and overtime requirements, particularly within teams experiencing elevated attrition.

### 2. Examine High-Attrition Roles

Conduct deeper analysis of roles such as **Sales Representative** to understand whether compensation, workload, career progression, or satisfaction contributes to turnover.

### 3. Review Frequent Business Travel

Evaluate whether frequent travel is affecting employee experience, work-life balance, or retention.

### 4. Analyze Compensation Alongside Other Factors

Employees who left have lower average monthly income, so compensation should be investigated together with job level, tenure, role, and satisfaction rather than treated as an isolated factor.

> These recommendations represent areas for further business investigation based on observed patterns in the dataset, not causal conclusions.

---

## 🧠 Key Learnings

This project strengthened several areas of my Power BI and data analytics workflow.

### Data Modeling

* Designing fact and dimension tables.
* Working with a Snowflake-style dimensional model.
* Using keys to connect analytical and descriptive data.

### DAX

* `COUNTROWS`
* `COUNTX`
* `FILTER`
* `DIVIDE`
* `AVERAGE`
* `MAX`
* `MIN`
* `RELATED`
* `RANKX`
* `SWITCH`
* Calculated columns
* Context-aware analytical calculations

### Power Query

* Data type management.
* Column renaming.
* Table merging.
* Dimension key integration.
* Removing redundant attributes.
* Preparing data for the semantic model.

### Data Visualization

* Designing executive-oriented dashboards.
* Moving from high-level KPIs to detailed employee analysis.
* Building a consistent visual hierarchy.
* Using visual indicators to improve interpretation.

### UI/UX & Dashboard Design

* Dashboard layout design using Figma.
* Visual hierarchy and component design.
* Consistent spacing and alignment.
* Designing interfaces before Power BI implementation.

### Advanced Power BI

The project also provided practical experience with **DAX-generated HTML/CSS content inside Power BI**, demonstrating how analytical logic can be combined with custom presentation techniques.

---

## ⚙️ Challenges & Solutions

### Challenge: Creating a Structured Analytical Model

The raw dataset contained employee attributes and analytical fields together.

### Solution

The model was transformed into a dimensional structure with `FACT_Atrition` supported by employee, department, education, job, and business-travel dimensions.

### Result

The resulting model provides a more organized foundation for analytical reporting and allows descriptive attributes to be managed independently from the fact-level data.

---

### Challenge: Creating a More Detailed Employee View

Standard Power BI table visuals can limit the level of customization available for an employee-directory experience.

### Solution

A DAX measure was used to dynamically generate HTML content containing employee information, status badges, job-level indicators, and custom table elements.

### Result

The Employee Details page provides a more customized employee-directory experience while still being driven by the underlying Power BI data model.

---

### Challenge: Balancing Analytics and Visual Design

A dashboard can contain accurate analysis but still be difficult to use if the visual hierarchy and user experience are not carefully designed.

### Solution

Figma was used to plan the dashboard interface and refine the visual structure before implementation in Power BI.

### Result

The final dashboard combines analytical functionality with a more deliberate UI/UX approach.

---

## 💼 Skills Demonstrated

### Data Analytics

* Exploratory Data Analysis
* HR Analytics
* Attrition Analysis
* KPI Development
* Business Insight Generation
* Employee Segmentation

### Power BI

* Data Modeling
* DAX
* Power Query
* Interactive Dashboards
* KPI Design
* Custom HTML/CSS Visual Content
* Report Navigation

### UI/UX & Visualization

* Figma
* Dashboard UI Design
* Visual Hierarchy
* Data Storytelling
* Custom Visual Design
* HTML/CSS

### Business Intelligence

* Business Problem Definition
* Analytical Storytelling
* Executive Reporting
* Insight Interpretation
* Business-Oriented Recommendations

---

## ▶️ How to Explore the Project

### Power BI

1. Clone or download the repository.
2. Open the Power BI project/report.
3. If required, update the source-data path to the included Excel dataset.
4. Refresh the model.
5. Navigate through the Landing Page, Executive Page, and Employee Details sections.
6. Use the available filters and interactions to explore the analysis.

### Important

The original Power Query source references a local Excel file path. When moving the project to another environment, the data source path may need to be updated before refreshing the model.

---

## 📌 Project Context

**GBS BI HUB – BI Developer HR Attrition Case Study**

This project was developed as part of an **interview case study** to demonstrate practical capabilities in:

* Power BI development
* Data modeling
* DAX
* Power Query
* Data visualization
* Figma-based dashboard design
* HTML/CSS custom visuals
* Business-oriented analytics
