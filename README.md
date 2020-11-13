# Centralized-repository--Data-lake

A data lake is a centralized repository that allows you to store all your structured and unstructured data at any scale. You can store your data as-is, without having to first structure the data, and run different types of analytics—from dashboards and visualizations to big data processing, real-time analytics, and machine learning to guide better decisions.-Amazon

This project will focus on Auto Insurance data used by a startup company, 247Insurance. Customer has grown and management decided to move their data warehouse to a data lake. Location of data is in S3 has JSON logs directory and metadata on different quotes in their application.

--CREATE ETL PIPELINE

1. Read data from source aka S3
-- source here
Insurance data: ~/~/~/data
Log file: ~/~/~/file

2. Transform data using migration tool (say spark)

Fact Table

Insurance companies- Sample data collected from five different auto insurance company.
•	Geico
•	Progressive. ...
•	Farmers. ...
•	Liberty Mutual. ...
•	Nationwide

Dimension Tables: Includes different attributes of customer

--YOUR CAR
--Your Driving Record
--How Much You Drive

--DEMOGRAPHIC FACTORS
-Where You Live and Park Your Car
-Your Age and Gender.

THE COVERAGES, LIMITS AND DEDUCTIBLES YOU CHOOSE
-The Type of Coverage
-Your Limits and Deductibles


3. Load data
-Writes to S3(table directories)

