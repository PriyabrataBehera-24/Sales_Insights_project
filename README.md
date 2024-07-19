# Power BI Project | Sales Insights Data Analysis
Welcome to the "Power BI Sales Insights Data Analysis" project repository! This project aims to provide practical experience in generating sales insights using Power BI and SQL. The project simulates a real-world corporate environment, emphasizing the entire process from problem definition to dashboard creation.

## Project Overview
This project involves analyzing sales data for a computer hardware supplier, AtliQ Hardware, which faces challenges in tracking and understanding their sales data due to inconsistent and fragmented reporting. The goal is to create a comprehensive dashboard to gain actionable insights and make data-driven decisions.

## Problem Statement
AtliQ Hardware supplies computer hardware and peripherals to many clients, including Excel Stores across India. The company's head office is in Delhi, with several regional offices throughout India. The Sales Director is facing challenges in tracking sales in a dynamically growing market, as insights are currently gathered through verbal reports and numerous Excel files from regional managers. This fragmented approach leads to incomplete and sometimes inaccurate insights, making it difficult to identify key areas for improvement and to make informed decisions.

## Getting Started
Follow these instructions to set up the project locally on your machine.

### Prerequisites
1.Power BI Desktop 
2.MySQL Server
3.Basic knowledge of data analysis and visualization

### Instructions to Setup MySQL on Your Local Computer
1.Install MySQL on your local computer.

2.The SQL database dump is in the db_dump.sql file above.

3.Download the db_dump.sql file to your local computer and import it into MySQL.

## Data Analysis Using SQL

1.Show all customer records :
 SELECT * FROM customers;
 
2.Show the total number of customers :
 SELECT COUNT(*) FROM customers;
 
3.Show transactions where the currency is US dollars: 
 SELECT * FROM transactions WHERE currency='USD';
 
4.Show transactions in 2020 joined by the date table: 
 SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date WHERE date.year=2020;
 
5.Show total revenue in the year 2020: 
 SELECT SUM(transactions.sales_amount * CASE WHEN currency='USD' THEN 75 ELSE 1 END) FROM transactions INNER JOIN date ON transactions.order_date=date.date WHERE date.year=2020;

## Data Analysis Using Power BI

1.Formula to create norm_amount column:
= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)

## Usage
1.Open the Power BI file (.pbix) in Power BI Desktop.

2.Explore the different reports and visualizations.

## Acknowledgements
1.Special thanks to Hemanand for his expertise and contributions to the project.

2.Inspired by real-world data analysis projects to provide a practical learning experience.


