# Kultra-Mega-Stores_Project
This is the second official project given by Incubator Hub after Data Analysis Classes.

## Documentation Outline
 - Project Title
 - Project Overview
 - Database Setup
 - Data Exploration & Cleaning
 - Data Analysis
 - Findings
 - Project Overview
   
## Project Title: Kultra Mega Sales Analysis
## Project Overview
   - Database: KMS_Inventory
   - Tool: SQL Server Database
This project aims to generate insights into sales performance of the organization from 2009 to 2012. By analyzing the various parameters in the data received we seek to gather key insight to make decisions which then enable us to tell compelling stories around our data.

## Database Setup
 - Database Creation: The project starts by creating a database named KMS_Inventory.
 - Schema Creation: A database owner called Schema is created named dbo, a default used by SQL Server.
 - Table Creation: A table named [KMS SQL Case Study] was auto-created by the import tool (SSMS Import Wizard).

## Data Exploration & Cleaning
 - Preview the data: This was done during the process of importing the data to see a few rows.
 - Check column types: To find out if columns are INT, VARCHAR, NVARCHAR, etc.
 - Null Value check: Check for any null values in the dataset and delete records with missing data.

## Data Analysis
Data Analysis & Case scenarios & Answers
   ### 1. Which product category had the highest sales?
``` SQL
SELECT TOP 1 Product_Category, SUM (Sales)
As total_sales
FROM [dbo].[KMS SQL Case Study]
GROUP BY product_category
ORDER BY Total_Sales DESC

  ### 2.	What are the Top 3 and Bottom 3 regions in terms of sales?
``` SQL
SELECT TOP 3 REGION, SUM(Sales)
As total_sales
   FROM [dbo].[KMS SQL Case Study]
GROUP BY REGION
ORDER BY Total_Sales DESC
``` SQL
SELECT TOP 3 REGION, SUM(Sales)
As total_sales
FROM [dbo].[KMS SQL Case Study]
GROUP BY REGION
ORDER BY Total_Sales ASC

 ### 3.	What were the total sales of appliances in Ontario?
``` SQL
SELECT SUM(SALES) AS Total_Sales 
FROM [dbo].[KMS SQL Case Study]
WHERE Product_Sub_Category = 'Appliances'
AND Region = 'Ontario'

 ### 4.	Advise the management of KMS on what to do to increase the revenue from the 10 customers
``` SQL
SELECT TOP 10 Customer_Name, 
SUM(Sales) AS Lowest_Customer_Sales, 
SUM(Profit) AS Total_Profit,
SUM(Shipping_Cost) AS Total_Shipping_Cost,
SUM(Discount) AS Total_Discount,
COUNT(Order_ID) AS Total_Order
FROM [dbo].[KMS SQL Case Study]
GROUP BY Customer_Name
ORDER BY Lowest_Customer_Sales ASC
    
 ### 5.	KMS incurred the most shipping cost using which shipping method?
``` SQL
SELECT TOP 1 Ship_Mode, COUNT(Shipping_Cost) AS Highest_Shipping_Cost
FROM [dbo].[KMS SQL Case Study]
GROUP BY Ship_Mode
ORDER BY Highest_Shipping_Cost DESC



