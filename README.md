# Sales Insight : Data Analysis Project 
This project showcases the analysis and visualization of sales data from a company. It demonstrates data cleaning using SQL and the creation of an interactive dashboard using PostgreSQL and visualization tools.

## Project Overview
The goal of this project is to transform raw sales data into actionable insights. It starts with importing the data into a database using a SQL script, followed by cleaning and managing it in PostgreSQL, and ends with building a dynamic dashboard.

## key Steps:

1. Data Import:
   * Imported raw sales data into the SQL database using a structured .sql file.
     
2. Data Cleaning:
   * Removed unnecessary strings, duplicates, null values, and unwanted records (e.g., entries with negative salaries) using SQL queries.
    
3. Database Management:
   * The cleaned data was stored in PostgreSQL for structured management.
    
4. Interactive Dashboard:
   * Connected the PostgreSQL database to a visualization tool for building an interactive dashboard.
  
## Tools and Technologies Used
PostgreSQL: For data import, cleaning, and transformations.

Dashboard Tool: Power BI for creating visualizations.

## File Structure 
   * db_dump.sql : SQL file for importing raw data into the database and cleaning it.
     (Note:It's syntax is according to MySQL Environment,For other environment  either convert it or do table creation manually.
   * salesinsight.pbix : Power BI dashboard file
     
## Data Details
The project involves five tables that represent different facets of the company’s sales data:
1. Customers Table
   * `customer_code`,`customer_name` and `customer_type`

2. date
   * `date`,`cy_date`,`year`,`month_name` and `date_yy_mmm`
   * Removed unwanted strings from columns like '/r' from `date_yy_mmm`
   *  SQL Query :```update date
set date_yy_mmm = replace(date_yy_mmm,'\r','')
where date_yy_mmm like '%\r%';```

3. markets
   * `markets_code`,`markets_name` and `zone`
   * Removed null values
   * SQL Query : ```Delete from markets m
where m.zone='';```

4. products
   * `product_code` and `product_type`
   * Removed unwanted strings from columns like '/r' from `product_type`
   * SQL Syntax :```update products
set product_type = Replace(product_type,'\r','')
where product_type like '%\r%';```

5. transactions
   * `product_code`,`customer_code`,`market_code`,`order_date`,`sales_qty`,`sales_amount` and `currency`
   * Removed records with  negative sales_amount
   * SQL Syntax : ```Delete from transactions 
where sales_amount <=0;```
   * Removed duplicates as here `currency` Contains INR/USD and INR/r or USD/r
   * SQL Syntax : ```Delete from transactions
where currency NOT like '%\r%';```


## Dashboard Insights
The interactive dashboard includes:
1. Top Customers: Highlight best customers (in terms of revenue and quantity ordered) through bar chart.
2. Sales Trends: Time-series visualization to track sales performance.
3. Regional Analysis: Showing revenue generation across different regions.

 Dashboard Images:
   ![Screenshot 2024-11-16 002521](https://github.com/user-attachments/assets/4e4cb10d-2778-4df4-9634-163c4ae1e446)
   ![Screenshot 2024-11-16 002550](https://github.com/user-attachments/assets/7f0487dd-f2fb-476f-8d8f-4cf3247c3f28)


## Author 
  * Name : Ankit Rai
  * LinkedIn: [Ankit Rai](www.linkedin.com/in/ankitrai259)

   


   
     

    
