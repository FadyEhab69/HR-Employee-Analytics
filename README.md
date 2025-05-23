# HR Analytics Dashboard Project

# Overview

This project leverages the HR Analytics dataset to analyze employee demographics, performance, and promotion eligibility within an organization. As a data analyst, I cleaned the dataset, created custom measures in Power BI, and developed an interactive dashboard to visualize key HR metrics. The dashboard provides actionable insights into employee distribution, promotion readiness, and gender diversity across departments and job roles

# Dataset

The dataset, HR Analytics Data.csv, contains approximately 1,000 employee records with attributes such as Age, Attrition, BusinessTravel, Department, EducationField, Gender, JobLevel, JobRole, YearsAtCompany, YearsSinceLastPromotion, and more. The data reflects employee profiles across departments like Human Resources, Research & Development, and Sales, with additional metrics like MonthlyIncome and TotalWorkingYears.

# Measure Creation in Power BI

I developed custom DAX measures to enrich the analysis:

Total Employees: Total Emp = COUNT('HR Analytics'[EmployeeNumber]) - Calculated the total number of employees (1,000).

Employees Not Due for Promotion:

Logic: Employees with YearsSinceLastPromotion ≥ 3 and YearsAtCompany ≥ 5 were considered not due for promotion.

Measure: Not Due for Promotion = CALCULATE(COUNT('HR Analytics'[EmployeeNumber]), FILTER('HR Analytics', 'HR Analytics'[YearsSinceLastPromotion] >= 3 && 'HR Analytics'[YearsAtCompany] >= 5)) - Resulted in 95.1% of employees.

Due for Promotion: Due for Promotion = Total Emp - [Not Due for Promotion] - Identified 4.9% of employees eligible for promotion.

Gender Distribution by Department: Aggregated counts of Male and Female employees per Department using CALCULATE and SUMMARIZE.

Employee Count by Job Level: Summarized EmployeeNumber grouped by JobLevel for distribution analysis.

These measures enabled dynamic and precise visualizations tailored to HR needs.

# Dashboard Creation in Power BI

I designed an interactive Power BI dashboard to visualize the cleaned data and measures:


Total Employees: Displayed as "1K" for a quick overview.

Employees Not Due for Promotion by Service Years and Department: A stacked bar chart showing distribution across Human Resources, Research & Development, and Sales, with 5+ years of service having the highest count (e.g., 130 in HR at 5 years).

Employee by Education Field: A donut chart highlighting the predominance of Life Sciences (41.2%) and Medical (31.6%) fields.

Male and Female in Department: A pie chart showing a 58% male and 42% female split across departments.

Employee by Job Level: A bar chart indicating a balanced distribution (e.g., 543 at Level 1, 534 at Level 2).

Department by Job Role and Gender: Stacked bar charts detailing gender distribution in roles like Sales Executive (132 Female, 194 Male) and Laboratory Technician (85 Female, 174 Male).

Slicers: Added filters for Department (e.g., Human Resources, Sales) and JobRole to enable user interaction.

The dashboard uses a dark theme with rich colors for visual appeal and includes tooltips for detailed data points.

# Key Insights

Promotion Eligibility: 95.1% of employees are not due for promotion, with the majority having 5+ years of service, suggesting a need for reviewing promotion policies.

Education Distribution: Life Sciences (41.2%) and Medical (31.6%) dominate the education field, indicating a strong technical workforce.

Gender Balance: A 58% male and 42% female split across departments, with Sales showing higher male representation (e.g., 194 vs. 132 in Sales Executive roles).

Job Level Distribution: Levels 1 and 2 are the most populated (543 and 534 employees), reflecting a broad base of entry-to-mid-level staff.



Departmental Insights: Research & Development has the highest employee count, with roles like Laboratory Technician showing significant gender disparity (174 Male vs. 85 Female).

Interesting Fact: Despite 95.1% of employees not being due for promotion, those with 0-2 years since their last promotion (e.g., 27 in HR at 0 years) could indicate rapid initial growth or potential oversight in promotion tracking.

These insights showcase my ability to extract actionable HR strategies from complex data.
