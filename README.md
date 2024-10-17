# Task-1
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
Click the "01 Call-Center-Dataset" to view the DataSet.


## Data Analysis (DAX):
Key DAX measures used in the dashboard include:
- **Overall Customer Satisfaction**:
  ```dax
  Answered = CALCULATE(COUNT(Sheet1[Call Id]),FILTER(Sheet1, Sheet1[Answered (Y/N)]="Y"))
  
  DayOfWeek = FORMAT(Sheet1[Date],"dddd")
  
  Resolved (Y) = CALCULATE(COUNT(Sheet1[Call Id]),FILTER(Sheet1,Sheet1[Resolved]="Y"))


# Task-2
  # Power BI Dashboard for Customer Retention KPIs

## Problem Statement:
The purpose of this task is to:
- Define key performance indicators (KPIs) relevant to customer retention.
- Create a Power BI dashboard for the retention manager that effectively reflects these KPIs.
- Provide an overview of findings and recommendations for potential changes based on the data analysis.

## Datasource:
The dataset used for this task consists of customer retention metrics, which can be obtained from internal databases or customer service logs.
Click the "02 Churn-Dataset" to view the DataSet

## Data Analysis (DAX):
Key DAX measures used in the dashboard include:
- **Total Customers Retained**:
  ```dax
  % Churn Rate = DIVIDE(CALCULATE(COUNT(churn[Churn]), churn[Churn] = "yes" ),COUNT (churn[Churn]), 0)

  % Device protection = DIVIDE(CALCULATE(COUNT(churn[DeviceProtection]), churn[DeviceProtection]="Yes", churn[Churn]="Yes"),CALCULATE(COUNT(churn[DeviceProtection]),churn[Churn]="Yes"),0)

  % NO-Multiple lines = DIVIDE(CALCULATE(COUNT(churn[MultipleLines]), churn[MultipleLines]="No", churn[Churn]="Yes"),CALCULATE(COUNT(churn[MultipleLines]),churn[Churn]="Yes", churn[MultipleLines] <> "No phone service"),0)
  
  % of Dependents = DIVIDE(CALCULATE(COUNT(Churn[Dependents]),Churn[Dependents]="Yes",Churn[Churn]="Yes"),CALCULATE(COUNT(Churn[Dependents]),Churn[Churn]="Yes"),0)

  % of Partner = DIVIDE(CALCULATE(COUNT(Churn[Partner]),Churn[Partner]="Yes",Churn[Churn]="Yes"),CALCULATE(COUNT(Churn[Partner]),Churn[Churn]="Yes"),0)
  
  % of Senior Citizen = DIVIDE(CALCULATE(COUNT(Churn[SeniorCitizen]),Churn[SeniorCitizen]=1,Churn[Churn]="Yes"), CALCULATE(COUNT(Churn[SeniorCitizen]),Churn[Churn]="Yes"),0)
  
  % Online Backup = DIVIDE(CALCULATE(COUNT(churn[OnlineBackup]), churn[OnlineBackup]="Yes", churn[Churn]="Yes"),CALCULATE(COUNT(churn[OnlineBackup]),churn[Churn]="Yes"),0)
  
  % Online Sec. = DIVIDE(CALCULATE(COUNT(churn[OnlineSecurity]), churn[OnlineSecurity]="Yes", churn[Churn]="Yes"),CALCULATE(COUNT(churn[OnlineSecurity]),churn[Churn]="Yes"),0)
  
  % Phone Service = DIVIDE(CALCULATE(COUNT(churn[PhoneService]), churn[PhoneService]="Yes", churn[Churn]="Yes"),CALCULATE(COUNT(churn[PhoneService]),churn[Churn]="Yes"),0)
  
  % Streaming Movies = DIVIDE(CALCULATE(COUNT(churn[StreamingMovies]), churn[StreamingMovies]="Yes", churn[Churn]="Yes"),CALCULATE(COUNT(churn[StreamingMovies]),churn[Churn]="Yes"),0)
  
  % Streaming TV = DIVIDE(CALCULATE(COUNT(churn[StreamingTV]), churn[StreamingTV]="Yes", churn[Churn]="Yes"),CALCULATE(COUNT(churn[StreamingTV]),churn[Churn]="Yes"),0)
  
  % Tech Support = DIVIDE(CALCULATE(COUNT(churn[TechSupport]), churn[TechSupport]="Yes", churn[Churn]="Yes"),CALCULATE(COUNT(churn[TechSupport]),churn[Churn]="Yes"),0)
  
  % Yes-Multiple Lines = DIVIDE(CALCULATE(COUNT(churn[MultipleLines]), churn[MultipleLines]="Yes", churn[Churn]= "Yes"), CALCULATE(COUNT(churn[MultipleLines]), churn[Churn]="Yes", churn[MultipleLines] <> "No phone service"),0)
  
  Churn Count = CALCULATE(COUNT(Churn[Churn]),Churn[Churn]="Yes")

