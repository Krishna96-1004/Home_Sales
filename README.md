# Home_Sales

This code is performing data analysis on a dataset of home sales using PySpark, a Python library for Apache Spark. Here's a summary of what each step accomplishes:

1. **Initialize findspark and create a SparkSession**: This sets up the environment for running PySpark code.

2. **Read the home sales data from the AWS S3 bucket into a DataFrame**: This loads the data into a PySpark DataFrame, which iss a distributed collection of data organized into named columns.

3. **Create a temporary view of the DataFrame**: This allows you to query the DataFrame using SQL syntax.

4. **Perform various SQL queries to analyze the data**: These quereis calculate average home prices based on various criteria, such as the number of bedrooms, bathrooms, floors, and square footage. The results are rounded to two decimal places for readability.

5. **Cache the temporary table 'home_sales' and check if it's cached**: Caching stores the table in memory fro faster access in subsequent queries.

6. **Using the cached data, run the query that filters out the view ratings with an average price greater than or equal to $350,000**: This query calculates the average home price for homes with different view ratings. The runtime for this query is also calculated to measure performance.

7. **Write the DataFrame to parquet format, partitioned by the "date_built" field**: Parquet is a columnar storage file formmat that is optimized for use with big data processing frameworks like Apache Spark. Partitioning by "date_built" organized the data in a way that can improve performance for queries that filter by this field.

8. **Read the parquet data into a new DataFrame and create a temporary view of it**: This allows you to query the parquet data using SQL syntax.

9. **Run the query that filters out the view ratings with an average price greater than or equal to $350,000 on the parquet DataFrame**: This repeats one of the earlier queries but on the parquet data instead of the original DataFrame. The runtimes for this query is also calculated to compare performance with the original query.

10. **Uncache the 'home_sales' temporary table and check if it's no longer cached**: This frees up memmory resources when you're done with the table.

In summary, this code demonstrates how to use PySpark and SQL to perform data analysis on a large dataset, and how to use techniques like caching and partitioning to improveb performance.
