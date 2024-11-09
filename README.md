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
This Data analysis project aims to analyzes sales data for the LITA boutique. The analysis is made to gain insights on sales performance, identify trends with the aim of giving data driven solution on the problems, if any and to improve sales by making informed decisions.




#### Problem Statement
---
The biggest challenge in the market today is caused basically due to inability of vendors to understand their customers' needs, season and time of specific needs. When supply does not meet demand, there is bound to be waste of time and resources. This Report aims to analyze the sales data to understand patterns, thereby providing actionable insights that can help the management make informed decisions.




#### Data Sources
---
The dataset used for this analysis was provided by the LITA Incubation hub, amd includes
- Sales transactions (Product, Quantity sold, Revenue, Quantity category, Order ID, Order Date)
- Product information (Product, Unit price)
- Customer demographics (Customer ID, Region)
  

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
- Total sales for each product category
- Number of sales in each region
- Highest selling product by total sales value
- Total Revenue per product
- Monthly sales total for the current year
- Top 5 customrs by total purchase amount
- Percentage of total sales contributed by each region
- Products with no sales in the last quarter


![Screenshot 2024-11-09 154334](https://github.com/user-attachments/assets/21d726d4-f22c-4b80-8756-63c559ae35d8)

![Screenshot 2024-11-09 153611](https://github.com/user-attachments/assets/bc259dff-7fac-477d-b3ee-8a084b9616c0)



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
- Total Quantity 
- Total orders
- Revenue by Products
- Products in demand
- Monthly Performance
- Quantity ordered by each region
  

#### Data Analysis
---
```SQL
#Total sales for each product category
SELECT  [product], SUM(Revenue)
FROM LITA_Capstone_Dataset_SalesData
GROUP BY [product];

#Number of sales in each region
SELECT  Region, COUNT(Quantity)
FROM LITA_Capstone_Dataset_SalesData
GROUP BY Region;

#Highest selling product by total sales value
SELECT TOP 1 product, SUM(Revenue) AS Total_Revenue
FROM LITA_Capstone_Dataset_SalesData
GROUP BY product
ORDER BY SUM(Revenue) DESC;

#Total Revenue per product
SELECT  product, SUM(Revenue) AS Total_Revenue
FROM LITA_Capstone_Dataset_SalesData
GROUP BY product;

#Monthly sales total for the current year
SELECT DATENAME(MONTH, OrderDate) AS [Month], SUM(Revenue) AS Total_Sales
FROM LITA_Capstone_Dataset_SalesData
WHERE DATENAME(YEAR, OrderDate) = '2024'
GROUP BY DATENAME(MONTH, OrderDate);

#Top 5 customrs by total purchase amount
SELECT TOP 5 Customer_Id, Quantity, Quantity_Category
FROM LITA_Capstone_Dataset_SalesData
ORDER BY Quantity DESC;

#Percentage of total sales contributed by each region
SELECT Region, SUM(Revenue) AS Total_Revenue, (SUM(Revenue)/(select sum(Revenue) from LITA_Capstone_Dataset_SalesData))*100 AS Percent_Total_sales
FROM LITA_Capstone_Dataset_SalesData
GROUP BY Region

# Products with no sales in the last quarter
SELECT Product, Quantity, OrderDate
FROM LITA_Capstone_Dataset_SalesData
WHERE Quantity IS NULL AND OrderDate BETWEEN '2024-07-01' AND '2024-09-01'

```

#### Data Visualization
---

![Revenue by products and Products in demand](https://github.com/user-attachments/assets/b124b16c-ca17-45aa-976c-13306128dfb4)
![Percentage fo revenue by Region](https://github.com/user-attachments/assets/5e2e33a6-3b0c-4008-bb95-3c38bc907d68) ![Revenue across months](https://github.com/user-attachments/assets/47aa5cb3-f939-47b0-9988-01c16c2539d9)  ![Sales Dashboard using Excel](https://github.com/user-attachments/assets/e0b01d4c-97d4-43ba-b46c-93bf66ef8aac)
![Report on Sales data](https://github.com/user-attachments/assets/9c510a7f-27fa-41d6-aa93-4de2bc04747e)




#### Conclusions and Recommendations
---
After thorough analysis of the data, the following observations were made:
- The North had the lowest sales for jackets. This could be attributed to extreme temperatures in the North.
- The south produced the highest revenue.

Recommendations to boost sales include the following:
- More advertisement should be made in Regions with low sales
- Products with the higest turnovers and revenues for each Region should be made more available
- For the North region, certain products should be available in minimal quantity while others like hats should be made more available.
