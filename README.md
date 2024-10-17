# Power BI Dashboard for Customer Service KPIs

![Power BI Dashboard](https://user-images.githubusercontent.com/118357991/227788348-b988c4df-7923-46d6-8af7-102b8042f721.png)

## Table of Contents:
- [Problem Statement](#problem-statement)
- [Datasource](#datasource)
- [Data Preparation](#data-preparation)
- [Data Modeling](#data-modeling)
- [Data Analysis (DAX)](#data-analysis-dax)
- [Data Visualization (Dashboard)](#data-visualization-dashboard)
- [Insights](#insights)
- [Recommendations](#recommendations)

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

## Data Preparation:
Data transformation was performed to ensure the dataset was clean and usable in Power BI. Steps taken include:
- Importing the dataset into Power Query for transformation.
- Removing any duplicate records and unnecessary columns.
- Validating data types for each column to ensure accurate analysis.
- Creating new calculated columns as needed, such as call volume per time segment and customer satisfaction ratings.

## Data Modeling:
After data cleaning, the dataset was structured into appropriate tables for analysis. Key tables include:
- **Call Data Table**: Contains call records with fields for call duration, call status (answered/abandoned), and timestamps.
- **Customer Satisfaction Table**: Includes satisfaction ratings linked to specific calls or agents.

## Data Analysis (DAX):
Key DAX measures used in the dashboard include:
- **Overall Customer Satisfaction**:
  ```dax
  Overall Satisfaction = AVERAGE('Customer Satisfaction'[Rating])
