# Power BI Dashboard for Customer Service KPIs

## Problem Statement:
The purpose of this task is to:
- Create a comprehensive Power BI dashboard for Claire that reflects relevant Key Performance Indicators (KPIs) and metrics.
- The dashboard should aid in analyzing customer service performance and support data-driven decision-making.
- Key metrics to include are:
  - Overall customer satisfaction
  - Total calls answered vs. abandoned
  - Call volume by time
  - Average speed of answer
  - Agent performance quadrant: average handle time vs. calls answered

## Datasource:
The dataset used for this task includes customer service metrics, which can be sourced from internal CRM systems or customer support logs.
click the ##"01 Call-Center-Dataset" to view the DataSet.


## Data Analysis (DAX):
Key DAX measures used in the dashboard include:
- **Overall Customer Satisfaction**:
  ```dax
  Answered = CALCULATE(COUNT(Sheet1[Call Id]),FILTER(Sheet1, Sheet1[Answered (Y/N)]="Y"))
  DayOfWeek = FORMAT(Sheet1[Date],"dddd")
  Resolved (Y) = CALCULATE(COUNT(Sheet1[Call Id]),FILTER(Sheet1,Sheet1[Resolved]="Y"))
