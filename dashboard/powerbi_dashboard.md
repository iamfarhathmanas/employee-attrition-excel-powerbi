# Power BI Dashboard Specification

## Page 1 — HR Overview
- KPI Card: Total Employees
- KPI Card: Employees Left
- KPI Card: Attrition Rate
- KPI Card: Average Salary
- Bar chart: Attrition Rate by Department
- Column chart: Attrition Rate by Job Level

## Page 2 — Attrition Drivers
- Column chart: Attrition by Tenure Group
- Bar chart: Attrition by Work Mode
- Bar chart: Attrition by Overtime
- Scatter or column comparison: Average Salary vs Attrition
- Slicers: Department, Job Level, Work Mode, Overtime

## Suggested Measures
```DAX
Total Employees = COUNTROWS(EmployeeData)
Employees Left = CALCULATE(COUNTROWS(EmployeeData), EmployeeData[Left_Company] = "Yes")
Attrition Rate = DIVIDE([Employees Left], [Total Employees])
Average Salary = AVERAGE(EmployeeData[Salary])
```
