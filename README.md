# HR Analytics Dashboard (Power BI)

I built this dashboard to practise turning HR data into something a manager could actually use. It covers headcount, attrition, hiring, attendance and payroll for a fictional company of 800 employees across 7 departments and 5 Indian cities.

The data is synthetic, so nothing here relates to a real organisation. The point of the project was the modelling, the DAX and the design, not the dataset.


## What's in the dashboard

**Page 1: Overview**
The big picture. Total, active and exited headcount, attrition rate, average tenure, headcount by department, location and employment type, hires versus exits by quarter, and attrition by department with a company-average line.

**Page 2: Attendance & Payroll**
Attendance rate by month and department, late and absent days, net payroll, bonuses, payroll cost over time, average salary by department, and a satisfaction and engagement table.

**Page 3: Recruitment** and **Page 4: Training**
Still in progress. I'll update this README when they're done.

## What the data says

- Out of 800 employees, 140 have left, which is an attrition rate of 17.5%.
- Exits have picked up recently. There were 7 in Q1 2025 and 28 in Q3 2026.
- Human Resources (23.3%) and Operations (21.7%) have the highest attrition, and Marketing has the lowest at 10.5%.
- Attendance is steady at about 95.8% across months and departments, so it isn't where the problems are.
- Monthly payroll cost has almost doubled, from about ₹25M in January 2024 to about ₹48M in October 2026.

## How it's built

- **Data model:** Employees is the central table, connected to Attendance, Payroll, Recruitment and Training by employee ID, with a date table for time analysis.
- **Two date roles:** hires and exits both come from the Employees table. Hire date is the active relationship to the date table and exit date is inactive, and a `USERELATIONSHIP` measure switches between them. Without this, hires and exits would show identical bars.
- **DAX measures:** headcount, attrition rate, attendance rate (present days over working days rather than an average of averages), payroll totals, hires and exits by date, and a dynamic chart title.
- **Interactions:** synced slicers across pages, a reset button, and edit-interactions settings so the hire-year slicer only affects the charts it should.

## Repo contents

```
├── HR_Analytics_Dashboard.pbix
├── data/
│   └── PowerBI_Portfolio_Synthetic_HR_Data.xlsx
└── screenshots/
```

## Running it yourself

1. Download `HR_Analytics_Dashboard.pbix` and open it in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (it's free).
2. If Power BI can't find the data, go to **Home → Transform data → Data source settings** and point it at the Excel file in the `data` folder.

## Things I'd improve

- Add a headcount-over-time view. At the moment the time charts show hires and exits, not total headcount month by month.
- Add a forecast for attrition.
- Finish the Recruitment and Training pages.

## About me

I work in HR and I'm building my Power BI skills through projects like this. Feedback is welcome, so feel free to open an issue or get in touch.

- LinkedIn: *add your link*
- Email: *add your email*
