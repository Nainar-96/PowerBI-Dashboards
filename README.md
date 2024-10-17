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
Click the **"01 Call-Center-Dataset"** to view the DataSet.


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
Click the **"02 Churn-Dataset"** to view the DataSet

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

# Task 3
## Power BI Dashboard for Diversity and Inclusion in Human Resources

## Problem Statement
Human Resources at our telecom client is highly focused on improving diversity and inclusion, particularly in achieving a better gender balance at the executive management level. Despite their efforts, they are not seeing significant progress and have reached out for assistance.

### Suggested KPIs to Measure Progress

To define proper KPIs, the following measures could be calculated:

- **Number of Men**: Total number of male employees.
- **Number of Women**: Total number of female employees.
- **Number of Leavers**: Total number of employees who left the organization.
- **Percentage of Employees Promoted (FY21)**: Proportion of employees promoted during fiscal year 2021.
- **Percentage of Women Promoted**: Proportion of promotions awarded to female employees.
- **Percentage of Hires that are Men**: Proportion of new hires that are male.
- **Percentage of Hires that are Women**: Proportion of new hires that are female.
- **Percentage Turnover**: Overall employee turnover rate.
- **Average Performance Rating (Men)**: Average performance rating for male employees.
- **Average Performance Rating (Women)**: Average performance rating for female employees.

### Data Source

The data for these KPIs will be sourced from:

- **HR Management System**: The internal database containing employee records, including demographics, promotions, and turnover.
- **Employee Performance Reviews**: Documentation of performance ratings that can provide insights into employee evaluations.

Click the **"03 Diversity-Inclusion-Dataset"** to view the DataSet

## Data Analysis (DAX):
Key DAX measures used in the dashboard include:

```dax
  # Avg Men Rating = CALCULATE(AVERAGE(Pharma[FY20 Performance Rating]),FILTER(Pharma,Pharma[Gender]="Male"))
  
  # Female = CALCULATE(DISTINCTCOUNT(Pharma[Employee ID]),FILTER(Pharma,Pharma[Gender]="Female"))
  
  # male = CALCULATE(DISTINCTCOUNT(Pharma[Employee ID]),FILTER(Pharma,Pharma[Gender]="Male"))
  
  # Promoted FY20 = CALCULATE(COUNT(Pharma[Employee ID]),Pharma[Promotion in FY20?]="Y")+CALCULATE(COUNT(Pharma[Promotion in FY21?]),Pharma[Promotion in FY21?]="Yes")
  
  #Avg Female Rating = CALCULATE(AVERAGE(Pharma[FY20 Performance Rating]),FILTER(Pharma,Pharma[Gender]="Female"))
  
  #Employee Turnover = DIVIDE(Pharma[#Leaver],COUNT(Pharma[Employee ID]),0)
  
  #Leaver = CALCULATE(COUNT(Pharma[FY20 leaver?]), Pharma[FY20 leaver?]="Yes")
  
  % Female = DIVIDE(Pharma[# Female],Pharma[# Female]+Pharma[# male])
  
  % Male = DIVIDE(Pharma[# male],Pharma[# Female]+Pharma[# male])
