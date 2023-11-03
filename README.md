### Project-4-BUILDING-DATA-BUILD-TOOL-DBT-MODELS
# **BUILDING DATA BUILD TOOL (DBT) MODELS**


**Introduction**
DBT is an open-source tool that enables data teams to transform data using analytics engineering best practices
It automatically generates documentation around descriptions, models dependencies, model SQL, sources, and tests. dbt creates lineage graphs of the data pipeline, providing transparency and visibility into what the data is describing, how it was produced, as well as how it maps to business logic. 
In this project, we will build a time series model Using the Craigslist Vehicles Dataset

**The Data**
We are using data from (https://www.kaggle.com/datasets/mbaabuharun/craigslist-vehicles)

**Installation**
Installing PostgreSQL, Snowflake, DBT, and Power BI in my machine. 
I have used DB Browser for SQLite since my machine hasn’t installed PostgreSQL

**Importation of data into DB Browser for SQLite**
I have created a database and a table in SQL to store Craigslist Vehicles Dataset. 
I have then imported the dataset in to the database

**Setting up Snowflake Account**
I have created a free trial snowflake account 

**Transfer of data to Snowflake**
I have transferred the data using the Snowflake web interface to transfer data from DB Browser for SQLite.

```python 
DBT Data Transformation
After setting us a DBT account, I have used SQL to do data preprocessing, i.e. handling missing information, .

SQL Queries to address missing information
-- Replace missing values with the mean for numeric columns
WITH column_median AS (
  SELECT
    AVG(CASE WHEN price IS NOT NULL THEN price END) AS median_ price,
    AVG(CASE WHEN year IS NOT NULL THEN year END) AS median_year,
    AVG(CASE WHEN odometer IS NOT NULL THEN odometer END) AS median_ odometer,
  FROM craigslist_vehicles.csv)
 
SELECT
  -- Use COALESCE to replace missing values with the calculated means
  COALESCE(price, median_price) AS price,
  COALESCE(year, median_year) AS year,
  COALESCE(odometer, median_odometer) AS odometer,
```

**Power BI Visualization**

I have connected Power BI to Snowflake database to access the transformed data. Then created reports and dashboards in Power BI to visualize and analyze the data.
I have selected the data from your Snowflake database, "craigslist_vehicles.csv" transformed data. 
I have built interactive dashboards by creating visualizations by dragging and dropping fields pane into report canvas. 
I have created scatter charts, ribbon Chart and matrix tables.  

