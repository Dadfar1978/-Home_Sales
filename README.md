# Home_Sales
PySpark Home Sales Data Analysis

Project Overview

This project uses Apache Spark and PySpark to perform data analysis on a home sales dataset. The analysis includes loading data from a CSV file hosted on an AWS S3 bucket, filtering based on home attributes (like number of bedrooms, bathrooms, floors, square footage), calculating average prices, and storing and reading from Parquet format.

⸻

Tools & Technologies
    •    Apache Spark 3.5.5
    •    PySpark
    •    AWS S3 (for CSV file)
    •    Parquet (for optimized data storage)

⸻

Setup Instructions
    1.    Install Spark and Java:
    •    Set the Spark version.
    •    Install Java (OpenJDK 11).
    •    Download and extract Spark binaries.
    •    Set environment variables (JAVA_HOME, SPARK_HOME).
    2.    Initialize Spark:
    •    Use findspark to start a Spark session.
    3.    Import necessary packages:
    •    SparkSession, SparkFiles, and time.

⸻

Steps Performed

1. Load Data
    •    The CSV file was loaded using a public AWS S3 URL and added to Spark using SparkFiles.
    •    It was read into a DataFrame and displayed using .show().

2. Temporary View Creation
    •    Created a temporary view of the DataFrame for running SQL queries:
home_sales_df.createOrReplaceTempView("home_sales")

3. SQL Queries & Analysis

Query 1:
    •    Find the average price of four-bedroom houses sold per year.

Query 2:
    •    Average price of 3 bed / 3 bath homes by year built.

Query 3:
    •    Average price of 3 bed / 3 bath homes with two floors and more than 2000 sqft by year built.

Query 4:
    •    Average price by view for homes priced over $350,000 (with runtime comparison).

4. Parquet Usage
    •    Data was saved in Parquet format, partitioned by date_built.
    •    Read from Parquet and queried again for performance comparison.

⸻

Caching
    •    Demonstrated use of caching and un-caching:
    •    Cached temporary table home_sales.
    •    Measured performance.
    •    Uncached and checked if cache was cleared.

⸻

Results Highlights
    •    Spark SQL efficiently calculated average home prices under multiple filtering conditions.
    •    Using Parquet significantly improved query performance.
