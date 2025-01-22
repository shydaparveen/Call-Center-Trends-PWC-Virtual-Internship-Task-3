# Call-Center-Trends-PWC-Virtual-Internship-Task-3
# PWC Power BI Virtual work experience - Customer Churn Retention

# Table of Contents:
Problem Statement
Datasource
Data Preparation
Data Modeling
Data Analysis (DAX)
Data Visualization (Dashboard)
Insights
Recommendation
Problem Statement :
The purpose of this task is to:

# Define proper KPI's
Create a dashboard for the retention manager reflecting the KPI's
Write a short email to him (the engagement partner) explaining your findings, and include suggestions as to what needs to be changed
Customers who left within the last month
Services each customer has signed up for: phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies
Customer account information: how long as a customer, contract, payment method, paperless billing, monthly charges, total charges and number of tickets opened in the categories administrative and technical
Demographic info about customers – gender, age range, and if they have partners and dependents
Datasource :
Dataset used for this task was presented by Pwc and customer churn Retention dataset:

## Dataset: Customer Churn Retention

## Data Preparation:
Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

## Customer Churn dataset is give table named:

Customer churn dataset which has 23 columns and 7043 rows of observation
Data Cleaning for the dataset was done in the power query editor as follows:

Replaced the value is SeniorCitizen N coverted No and Y converted Yes
In the new table, one additional conditional columns were added using M-formula:

loyalty = SWITCH(TRUE(),'01 Churn-Dataset'[tenure]<=12,"< 1 year",'01 Churn-Dataset'[tenure]<=24,"< 2 years",'01 Churn-Dataset'[tenure]<=36,"< 3 years",'01 Churn-Dataset'[tenure]<=48,"< 4 years", '01 Churn-Dataset'[tenure]<=60,"< 5 years",'01 Churn-Dataset'[tenure]<=72,"< 6 years")

Removed Unnecessary columns

Removed Unnecessary rows

Each of the columns in the table were validated to have the correct data type

## Data Modeling:
And then dataset was cleaned and transformed, it was ready to the data modeled.

The customer churn tables as show below:
Screenshot (39)

## Data Analysis (DAX):
Measures used in all visualization are:

Average MonthlyCharges = AVERAGE('01 Churn-Dataset'[MonthlyCharges])

Average TotalCharges = AVERAGE('01 Churn-Dataset'[TotalCharges])

churn count = CALCULATE(COUNT('01 Churn-Dataset'[Churn]), ALLSELECTED('01 Churn-Dataset'[Churn]),'01 Churn-Dataset'[Churn] = "Yes")

churn rate % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Churn]), '01 Churn-Dataset'[Churn] = "yes" ), COUNT('01 Churn-Dataset'[Churn]), 0)

Dependent in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Dependents]), '01 Churn-Dataset'[Dependents]="Yes",'01 Churn-Dataset'[Churn]="Yes"), CALCULATE(COUNT('01 Churn-Dataset'[Dependents]),'01 Churn-Dataset'[Churn]="Yes"), 0)

Device protection in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]), '01 Churn-Dataset'[DeviceProtection] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]),'01 Churn-Dataset'[Churn]="Yes"),0)

Online backup in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]), '01 Churn-Dataset'[OnlineBackup] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]),'01 Churn-Dataset'[Churn]="Yes"),0)

Online security in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]), '01 Churn-Dataset'[OnlineSecurity] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]),'01 Churn-Dataset'[Churn]="Yes"),0)

Partner in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Partner]),'01 Churn-Dataset'[Partner]="Yes",'01 Churn-Dataset'[Churn]="Yes"), CALCULATE(COUNT('01 Churn-Dataset'[Partner]), '01 Churn-Dataset'[Churn]="Yes"), 0)

Phone service in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]), '01 Churn-Dataset'[PhoneService] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]),'01 Churn-Dataset'[Churn]="Yes"),0)

SenioCitizen in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[SeniorCitizen]=1,'01 Churn-Dataset'[Churn]="Yes"), CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[Churn]="Yes"), 0)

Streaming Movies in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]), '01 Churn-Dataset'[StreamingMovies] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]),'01 Churn-Dataset'[Churn]="Yes"),0)

Streaming TV in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]), '01 Churn-Dataset'[StreamingTV] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]),'01 Churn-Dataset'[Churn]="Yes"),0)

Tech Support in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]), '01 Churn-Dataset'[TechSupport] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]),'01 Churn-Dataset'[Churn]="Yes"),0)

Data Visualization (Dashboard):
Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

