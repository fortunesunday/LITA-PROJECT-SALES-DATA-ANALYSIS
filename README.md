## LITA_Project

#### PROJECT TITLE: Customer Data Analysis
---
[Project Overview](#project-overview)

[Problem Statement](#problem-statement)

[Data Sources](#data-sources)

[Tools Used](#tools-used)

[Data Cleaning and Preparations](#data-cleaning-and-preparations)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Data Analysis](#data-analysis)

[Data Visualization](#data-visualization)

[Conclusions and Recommendations](#conclusions-and-recommendations)


#### Project Overview
---
This Data analysis project aims to analyze the Customer data for the LITA Television. The analysis is made to gain insights on the business performance, identify trends with the aim of giving data driven solution to the problems, if any and to improve the Television performance and customers' satisfaction by making informed decisions.


#### Problem Statement
---
The biggest challenge in the market today is caused basically due to inability of vendors to understand their customers' needs, season and time of specific needs. When Customers' are unsatisfied, there could be low patronage. This Report aims to analyze the Customer data to understand patterns, thereby providing actionable insights that can help the management make informed decisions.


#### Data Sources
---
The dataset used for this analysis was provided by the LITA Incubation hub, amd includes
- Sales transactions (Canceled Subscription Revenue, Subscription start, Subscription end)
- Product information (Subscription type)
- Customer demographics (Customer ID, Customer Name, Region)
  

#### Tools Used
---
 - Microsoft Excel [Download Here](https://www.microsoft.com)
  1.  For Data Cleaning
  2.  For analysis
  3.  For Data Visualization
     
- SQL - Structured Query Language for Querying of Data

- Power BI for visualization
  
- GitHub for Portfolio building
  

#### Data Cleaning and Preparations
---
In the inital phase of the Data cleaning and preparations, we performed the following action:
1. Data Loading and Inspection
2. Handling missing variables
3. Data cleaning and formatting
   

 #### Exploratory Data Analysis
---
EDA involved the exploring of the Data to answer some questions about the Data such as;
- Total number of customers for each region
- customers who cancelled their subscriptins within 6 months
- Most popular subscription type
- Average subscription duration for all customers
- Total Revenue by subscription type
- Top 3 regions by subscription cancellations
- Total number if active and cancelled subscriptions
  

#### Data Transformation
---
Data was thoroughly cleaned and transformed using the Power Query tool in Excel. The following transformations were made:
- Removal of duplicates
- Removal/filling of missing values as required
- Data type adjustments suitable for the columns
The transformed data was then double checked in Power BI query for inconsistencies and was rectified where needed.


#### Analysis and Visualizations
---
The final report includes several visualizations highlighting:
- Total Revenue
- Average Revenue
- Total Subscription count
- Subscription types in each region
- Count of subscription by Region
- Revenue by Subscription type
- Minimum Revenue
- Revenue by Region
- Revenue by month
- Monthly Performance
- Quantity ordered by each region
- Number of active and canceled subscriptions by Region
  

#### Data Analysis
---
```SQL
#Most popular subscription type
SELECT [SubscriptionType], COUNT(CustomerID) AS NumberofSubscriptions
FROM ProjectCustomerData
GROUP BY [SubscriptionType]

#Customers who cancelled their subscriptions within 6 months
SELECT CustomerID, CustomerName
FROM ProjectCustomerData
WHERE Canceled = 1 AND DATEDIFF(MONTH, SubscriptionStart, SubscriptionEnd) <= 6

#most popular subscription type
SELECT [SubscriptionType], COUNT(CustomerID) AS NumberofSubscriptions
FROM ProjectCustomerData
GROUP BY [SubscriptionType]
```

#### Data Visualization
---


![Pie chart](https://github.com/user-attachments/assets/41cee80c-5b85-41ed-9b6e-29dd1c713d61)


![Bar chart](https://github.com/user-attachments/assets/a6f5e678-bf9e-4caa-947d-b1cee1183a1b)


![Report on Customer data](https://github.com/user-attachments/assets/3f379ba6-b4d5-4b2c-aac8-b143d595322e)


#### Conclusions and Recommendations
---
After thorough analysis of the data, the following observations were made:
- There was a 33% decrease in total revenue from 2022 to 2023. Number of subscriptions made were greatly reduced too.
- The Customers in the East and North preferred the **Basic** subscription type, those in the south prefered the **Premium** subscription type while those in the west, the **Standard** subscription type.
- The **Basic** subscription type was the most patronized

Recommendations to boost sales include the following:

Customers should be given some discount as a means of promoting patronage and gaining the customers' trust. This will help keep customers in the business in futeure. Also, competition might be the cause for the decline in revenue from 2022 to 2023, stategies to improve patronage should be put in place.
