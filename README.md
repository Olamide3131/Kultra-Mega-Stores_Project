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


![image alt](https://github.com/Olamide3131/Kultra-Mega-Stores_Project/blob/main/Question%201.png?raw=true)

<img width="976" height="280" alt="Image" src="https://github.com/user-attachments/assets/ef01e0ca-a618-43cf-afeb-e74f8c8faf2e" />

https://i.imgur.com/CkV7zhH.png


