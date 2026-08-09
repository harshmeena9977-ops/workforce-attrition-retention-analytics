# Workforce Attrition & Retention Analytics

> An interactive Power BI analytics project designed to identify
> workforce attrition patterns, segment employee risk areas, and
> translate workforce data into actionable retention insights.

![Power
BI](https://img.shields.io/badge/Power%20BI-Analytics-F2C811?style=flat&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measures-blue?style=flat)
![Power
Query](https://img.shields.io/badge/Power%20Query-Data%20Transformation-5E5E5E?style=flat)
![Data
Analysis](https://img.shields.io/badge/Data%20Analysis-Workforce%20Analytics-orange?style=flat)

------------------------------------------------------------------------

## 1. Project Overview

Employee attrition is not simply a headcount problem. Understanding
**where employee exits are concentrated, which workforce segments
experience higher attrition, and which employee characteristics are
associated with attrition** is important for developing focused
retention strategies.

This project uses the **IBM HR Analytics Employee Attrition dataset** to
build a multi-page Power BI analytics solution that moves from
high-level workforce monitoring to detailed employee investigation and
executive recommendations.

The dashboard is designed around a simple analytical flow:

**Workforce Overview → Attrition Analysis → Satisfaction & Performance →
Employee-Level Investigation → Executive Insights**

The objective is not to predict future employee exits, but to analyze
historical workforce patterns and identify areas that warrant further
investigation.

------------------------------------------------------------------------

## 2. Business Objective

The primary objective is to answer:

-   How large is the current workforce represented in the dataset?
-   What is the overall observed attrition level?
-   Which departments contribute the most employee exits?
-   Which job roles have the highest attrition counts?
-   Which age groups show higher attrition rates?
-   How does attrition vary across salary, education, travel, overtime,
    and satisfaction segments?
-   Which employee characteristics are highlighted by Power BI Key
    Influencers?
-   Which workforce areas should management prioritize for deeper
    retention analysis?

------------------------------------------------------------------------

## 3. Dataset

**Dataset:** IBM HR Analytics Employee Attrition

**Source:** Kaggle

**Records:** 1,470 employees

**Primary outcome variable:** `Attrition`

The dataset contains employee demographic, compensation, job,
satisfaction, travel, tenure, and performance-related attributes.

### Major analytical dimensions

-   Age
-   Gender
-   Department
-   Job Role
-   Education Field
-   Business Travel
-   Monthly Income
-   Job Satisfaction
-   Environment Satisfaction
-   Work-Life Balance
-   Performance Rating
-   Years at Company
-   Overtime
-   Stock Option Level
-   Total Working Years
-   Attrition

> **Dataset credit:** IBM HR Analytics Employee Attrition (Kaggle)

------------------------------------------------------------------------

## 4. Analytical Approach

The project follows an end-to-end BI workflow:

``` text
Raw Dataset
     ↓
Data Validation & Cleaning
     ↓
Power Query Transformations
     ↓
Calculated Columns / Measures
     ↓
Power BI Data Model
     ↓
Exploratory Workforce Analysis
     ↓
Interactive Dashboard
     ↓
Key Influencers Analysis
     ↓
Executive Insights & Recommendations
```

The analysis focuses primarily on **descriptive and diagnostic
analytics**.

No causal claims are made from the observed relationships.

------------------------------------------------------------------------

## 5. Data Preparation

Data preparation was performed using Power Query before building the
dashboard.

Key preparation activities included:

-   Promoting headers
-   Correcting data types
-   Cleaning text values
-   Trimming and cleaning categorical fields
-   Standardizing categorical values
-   Creating analytical groups
-   Creating age-group classifications
-   Creating salary-band classifications
-   Preparing fields required for dashboard segmentation
-   Validating employee-level records
-   Checking the uniqueness of employee identifiers

The dataset contains **1,470 unique employee records** based on the
employee identifier used in the analysis.

------------------------------------------------------------------------

## 6. Power BI Measures

The dashboard uses DAX measures to calculate core workforce KPIs
dynamically.

Examples include:

### Total Employees

```dax
Total Employees =
DISTINCTCOUNT('HR Analytics'[EmployeeNumber])
```

### Attrition Count

```dax
Attrition Count =
CALCULATE(
    [Total Employees],
    'HR Analytics'[Attrition] = "Yes"
)
```

### Active Employees

```dax
Active Employees =
[Total Employees] - [Attrition Count]
```

### Attrition Rate

```dax
Attrition Rate =
DIVIDE(
    [Attrition Count],
    [Total Employees],
    0
)
```

Additional measures were created for workforce metrics such as:

-   Average Age
-   Average Monthly Income
-   Average Years at Company
-   Average Job Satisfaction
-   Average Environment Satisfaction
-   Average Work-Life Balance
-   Average Performance Rating

The dashboard also includes a refresh timestamp mechanism and page-level
reset-filter functionality.

------------------------------------------------------------------------

## 7. Dashboard Architecture

The Power BI report contains **five analytical pages**, each serving a
different purpose.

------------------------------------------------------------------------

## Page 1 --- Workforce Overview

### Purpose

Provide an executive-level view of workforce composition, attrition, and
employee retention patterns.

### Key KPIs

-   Total Employees
-   Attrition Count
-   Active Employees
-   Attrition Rate
-   Average Age
-   Average Monthly Salary

### Key Visuals

-   Department-wise Attrition
-   Gender Distribution
-   Employees by Education Field
-   Employee Retention by Age Group
-   Job Roles with Highest Attrition
-   Key Insights panel

### Selected findings

-   Total workforce represented: **1,470 employees**
-   Recorded attrition: **237 employees**
-   Active employees: **1,233**
-   Overall observed attrition rate: **16.12%**
-   Research & Development recorded **133 attrition cases**,
    representing approximately **56.1% of recorded exits**
-   Laboratory Technician had the highest attrition count among the
    displayed job roles at **62**
-   The 26--35 age group represents the largest workforce segment
-   Retention varies considerably across age groups

The page is designed to answer:

> **"What does the overall workforce and attrition situation look
> like?"**

------------------------------------------------------------------------

## Page 2 --- Workforce Insights

### Purpose

Explore how attrition varies across major workforce characteristics.

### Key Visuals

-   Attrition by Business Travel
-   Attrition by Salary Band
-   Attrition by Education Field
-   Attrition by Job Satisfaction
-   Attrition by Overtime
-   Executive Workforce Insights

### Observed patterns

#### Business Travel

Recorded attrition counts:

  Business Travel     Attrition Count
  ------------------- -----------------
  Travel_Rarely       156
  Travel_Frequently   69
  Non-Travel          12

Travel_Rarely has the highest attrition count in absolute terms.

However, this should not automatically be interpreted as evidence that
Travel_Rarely causes higher attrition. Segment size and underlying
workforce composition also matter.

#### Salary Band

  Salary Band   Attrition Count
  ------------- -----------------
  Low           163
  Medium        49
  High          20
  Very High     5

The Low salary band contains the largest number of recorded exits.

#### Education Field

The largest attrition count is observed among employees from the Life
Sciences education field.

#### Overtime

  Overtime   Attrition Count
  ---------- -----------------
  Yes        127
  No         110

Attrition is observed in both groups, with a higher absolute count among
employees working overtime.

------------------------------------------------------------------------

## Page 3 --- Satisfaction & Performance

### Purpose

Investigate whether employee satisfaction, work-life balance, workplace
environment, and performance ratings show meaningful differences in
attrition.

### KPI indicators

All satisfaction/performance measures are evaluated on a **1--4 scale**.

-   Average Job Satisfaction: **3.00**
-   Average Environment Satisfaction: **2.72**
-   Average Work-Life Balance: **3.00**
-   Average Performance Rating: **3.15**

### Key Visuals

-   Employee Attrition by Job Satisfaction
-   Attrition by Work-Life Balance
-   Employee Attrition by Relationship Satisfaction
-   Attrition by Environment Satisfaction
-   Employee Performance Rating Distribution
-   Key Employee Experience Insights

### Observed patterns

Job satisfaction does not show a simple linear relationship with
attrition count.

Recorded attrition counts by Job Satisfaction:

  Satisfaction Level   Attrition Count
  -------------------- -----------------
  1                    66
  2                    46
  3                    73
  4                    52

This indicates that employee exits occur across all satisfaction levels
rather than being concentrated exclusively among employees with the
lowest satisfaction score.

Similarly, work-life balance level 3 has the highest recorded attrition
count in this dataset.

These patterns support a broader workforce analysis rather than treating
one satisfaction variable as the sole explanation for employee exits.

------------------------------------------------------------------------

## Page 4 --- Employee Details

### Purpose

Provide an employee-level investigation layer behind the aggregated
dashboard metrics.

The page allows users to filter and inspect individual employee records.

### Available filters include

-   Department
-   Gender
-   Job Role
-   Education Field
-   Attrition

### Employee-level fields include

-   Employee Number
-   Age
-   Gender
-   Department
-   Job Role
-   Education Field
-   Business Travel
-   Monthly Income
-   Years at Company
-   Job Satisfaction
-   Environment Satisfaction
-   Work-Life Balance
-   Performance Rating
-   Attrition

This page provides a bridge between:

**aggregated workforce insights → individual employee records**

It also makes the dashboard more useful for exploratory investigation
rather than limiting it to static executive reporting.

------------------------------------------------------------------------

## 8. Page 5 --- Executive Insights

### Purpose

Translate the analytical findings into areas that management could
prioritize for further investigation.

### Components

-   Departments with Highest Attrition
-   Attrition Rate by Age Group
-   Job Roles with Highest Attrition
-   Key Influencers
-   Executive Recommendations

### Key observations

#### Department

Research & Development records the highest attrition count:

**133 exits**

followed by:

-   Sales: 92
-   Human Resources: 12

#### Age

The highest observed attrition rate occurs among employees under 25.

  Age Group   Attrition Rate
  ----------- ----------------
  Under 25    35.77%
  26--35      19.14%
  36--45      9.19%
  46--55      11.50%
  56          17.02%

This highlights early-career employees as an important segment for
further retention analysis.

#### Job Role

Laboratory Technician has the highest recorded attrition count among the
displayed job roles:

**62 exits**

followed by:

-   Sales Executive: 57
-   Research Scientist: 47
-   Sales Representative: 33
-   Human Resources: 12

------------------------------------------------------------------------

## 9. Key Influencers Analysis

The Executive Insights page uses Power BI's **Key Influencers** visual
to identify employee characteristics associated with an increased
likelihood of the selected attrition outcome.

Examples visible in the dashboard include:

  Factor                         Observed Influence
  ------------------------------ --------------------
  Overtime = Yes                 2.93x
  Monthly Income ≤ 2800          2.60x
  Environment Satisfaction ≤ 1   1.82x
  Job Satisfaction ≤ 1           1.58x
  Age 21--33                     1.77x

These values should be interpreted as **model-identified associations**,
not proof of causation.

For example:

> An observed 2.93x Key Influencer value for Overtime = Yes does not
> mean overtime causes employee attrition.

Instead, it indicates that this segment is associated with a higher
likelihood of the selected outcome within the model's analysis.

------------------------------------------------------------------------

## 10. Executive Recommendations

The dashboard translates observed patterns into areas for further
investigation rather than claiming guaranteed business outcomes.

### 01 --- Prioritize R&D retention analysis

Research & Development accounts for the largest share of recorded
employee exits and should be examined more deeply for role, tenure,
workload, compensation, and employee-experience patterns.

### 02 --- Investigate Laboratory Technician turnover

Laboratory Technician has the highest recorded attrition count among the
displayed job roles. Further investigation should examine workload,
compensation, tenure, overtime, and satisfaction characteristics within
this role.

### 03 --- Strengthen early-career retention

Employees under 25 show the highest observed attrition rate.
Organizations could investigate onboarding, career development, manager
support, workload, and early-career engagement.

### 04 --- Evaluate workforce drivers together

Attrition should not be evaluated through a single variable.

Business travel, salary, overtime, tenure, satisfaction, job role, and
employee demographics should be considered together when investigating
retention risk.

------------------------------------------------------------------------

## 11. Important Analytical Considerations

This project is based on observational employee data.

Therefore:

-   Correlation should not be interpreted as causation.
-   Absolute attrition counts should be interpreted alongside segment
    sizes.
-   Key Influencers identifies statistical/model associations rather
    than causal relationships.
-   Historical patterns do not guarantee future employee behavior.
-   Recommendations represent areas for further investigation rather
    than measured business outcomes.

This distinction is important when using workforce analytics for
decision-making.

------------------------------------------------------------------------

## 12. Dashboard Interactivity

The report includes interactive functionality such as:

-   Department filtering
-   Gender filtering
-   Job Role filtering
-   Education Field filtering
-   Attrition filtering
-   Cross-visual interactions
-   Page-level filter reset
-   Key Influencers exploration
-   Employee-level filtering
-   Dynamic refresh timestamp

The **Reset Filter** functionality is implemented through Power BI
bookmarks to restore the intended default state for each page.

------------------------------------------------------------------------

## 13. Dashboard Design

The dashboard follows a consistent visual system across all five pages.

### Design principles

-   Consistent orange accent color
-   Clear KPI hierarchy
-   Minimal visual clutter
-   Executive-friendly typography
-   Consistent chart layouts
-   Insight text below analytical visuals
-   Dedicated recommendation area
-   Page-specific analytical purpose
-   Interactive filtering

The design intentionally prioritizes **business readability over
decorative visual complexity**.

------------------------------------------------------------------------


## 14. Dashboard Preview

### Workforce Overview

![Workforce Overview](screenshots/Workforce-Overview.png)

Provides a high-level view of workforce size, attrition, demographics, retention, and major workforce patterns.

---

### Workforce Insights

![Workforce Insights](screenshots/Workforce-Insights.png)

Breaks down attrition across business travel, salary, education, job satisfaction, and overtime.

---

### Satisfaction & Performance

![Satisfaction & Performance](screenshots/Satisfaction%20%26%20Performance.png)

Examines the relationship between employee experience indicators, satisfaction, work-life balance, and performance.

---

### Employee Details

![Employee Details](screenshots/Employee%20Details.png)

Provides employee-level filtering and investigation.

---

### Executive Insights

![Executive Insights](screenshots/Executive%20Insights.png)

Combines attrition segmentation, Key Influencers, and executive recommendations.

------------------------------------------------------------------------

## 15. Technology Stack

  Technology           Purpose
  -------------------- -----------------------------------------
  Power BI Desktop     Dashboard development and visualization
  Power Query          Data cleaning and transformation
  DAX                  Measures and analytical calculations
  CSV / Dataset        Source data
  Git / GitHub         Version control and project portfolio
  Power BI Bookmarks   Page-level reset functionality

------------------------------------------------------------------------

## 16. Project Structure

```
workforce-attrition-retention-analytics/
├── README.md
├── data/
│   └── README.md
├── powerbi/
│   └── HR_Analytics_Dashboard.pbix
├── screenshots/
│   ├── workforce-overview.png
│   ├── workforce-insights.png
│   ├── satisfaction-performance.png
│   ├── employee-details.png
│   └── executive-insights.png
└── documentation/
    └── data-dictionary.md
```

> The exact repository structure should reflect the files actually
> committed to the repository.

------------------------------------------------------------------------

## 17. How to Use the Dashboard

1.  Download or clone the repository.
2.  Open the `.pbix` file using Power BI Desktop.
3.  Refresh the dataset if required.
4.  Navigate through the five analytical pages.
5.  Use the available slicers to investigate specific workforce
    segments.
6.  Select visual elements to cross-filter other visuals.
7.  Use **Reset Filter** to return the page to its default state.
8.  Use the Employee Details page for record-level investigation.
9.  Use Key Influencers on the Executive Insights page to explore
    model-identified associations.

------------------------------------------------------------------------

## 18. Key Skills Demonstrated

### Data Analysis

-   Descriptive analysis
-   Workforce segmentation
-   Attrition analysis
-   Comparative analysis
-   KPI development
-   Business-focused interpretation

### Power BI

-   Interactive dashboard development
-   Data modeling
-   DAX measures
-   Power Query transformations
-   Slicers
-   Cross-filtering
-   Bookmarks
-   Key Influencers
-   Drill/interactivity design

### Business Analysis

-   Problem framing
-   KPI definition
-   Workforce risk identification
-   Insight generation
-   Executive communication
-   Recommendation development

------------------------------------------------------------------------

## 19. What This Project Demonstrates

This project demonstrates the ability to move beyond simply creating
charts.

The workflow connects:

Business Problem ↓ Data Preparation ↓ Analytical Questions ↓ KPI
Development ↓ Segmentation ↓ Interactive Visualization ↓ Diagnostic
Analysis ↓ Key Influencers ↓ Business Insights ↓ Executive
Recommendations

The focus is on making analytical findings understandable and actionable
while maintaining appropriate limitations around interpretation.

------------------------------------------------------------------------

## 20. Limitations & Future Improvements

### Current limitations

-   The analysis is based on a historical/static dataset.
-   The dataset represents employee records rather than a live HR
    information system.
-   No causal inference is performed.
-   No predictive attrition model is included.
-   Business outcomes such as retention improvement or cost savings have
    not been measured.

### Potential future improvements

Future versions could incorporate:

-   Predictive attrition modeling
-   Employee attrition risk scoring
-   Time-based HR data
-   Compensation benchmarking
-   Cost-of-attrition analysis
-   Automated data refresh
-   HRIS integration
-   Statistical significance testing
-   Cohort-based retention analysis

These enhancements would require additional data and validation rather
than being inferred from the current dataset.

------------------------------------------------------------------------

## 21. Conclusion

The Workforce Attrition & Retention Analytics dashboard provides a
structured approach to understanding employee attrition across
departments, job roles, demographics, compensation, travel,
satisfaction, overtime, and other workforce characteristics.

The project combines **Power Query, DAX, interactive Power BI
visualizations, Key Influencers, employee-level exploration, and
executive recommendations** into a single analytical workflow.

Rather than treating one variable as the explanation for employee exits,
the dashboard highlights multiple workforce dimensions that can be
investigated together.

------------------------------------------------------------------------

## Dataset Credit

**IBM HR Analytics Employee Attrition --- Kaggle**

This project is intended for educational, portfolio, and analytical
demonstration purposes.

------------------------------------------------------------------------

## Author

**Harsh Meena**

Aspiring Data Analyst \| Power BI \| SQL \| Python \| Excel

GitHub
