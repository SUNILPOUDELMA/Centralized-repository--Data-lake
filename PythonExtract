#Import python modules
from datetime import datetime

#Import pyspark modules
from pyspark.context import SparkContext
import pyspark.sql.functions as f

•	def create_spark_session();
•	    spark = SparkSession \
•	        .builder \
•	        .config("", "") \
•	        .getOrCreate()
•	    
•	    return spark
•	    
•	    
•	 def auto_insurance_data(spark, input_data, output_data):
•	     
•	     Description: 
•	         
•	         # get filepath to insurance data file
•	    insurance_data = input_data + "insurance_data/*/*/*/*"
•	    
•	    # read auto insurance data file
•	    df = spark.read.json(song_data, mode='PERMISSIVE', columnNameOfCorruptRecord='corrupt_record').drop_duplicates()
•	    
•	     # extract columns to create auto insurance table
•	    auto_insurance_table = df.select("customer_id","state","city","effective_policy_year","coverage","gender","income","policytype","vehicle").drop_duplicates()
•	    
•	    # write insurance data table to parquet files partitioned by year and customer
•	    auto_insurance_table.write.parquet(output_data + "quotes/", mode="overwrite", partitionBy=["effective_policy_year","customer_id"])
•	
•	    # extract columns to create customer table
•	    customer_table = df.select("customer_id","customer_name","customer_location","customer_state","customer_income").drop_duplicates()
•	
•	    # write customer table to parquet files
•	    customer_table.write.parquet(output_data + "customer/", mode="overwrite")
•	    
•	    def insurance_log_data(spark, input_data, output_data):
•	    """
•	    Description:
•	            Process the insurance log data to extract data for users and insurance from it.   
•	    """
•	
•	    # get filepath to log data file
•	    log_data = os.path.join(input_data, "log-data/")
•	
•	    # read log data file
•	    df = spark.read.json(log_data, mode='PERMISSIVE', columnNameOfCorruptRecord='corrupt_record').drop_duplicates()
•	
•	   
•	    # read in insurance data to use for customer table
•	    song_df = spark.read\
•	                .format("parquet")\
•	                .option("basePath", os.path.join(output_data, "customer/"))\
•	                .load(os.path.join(output_data, "customer/*/*/"))
•	
•	    
•	    def main():
•	    spark = create_spark_session()
•	    input_data = "s3://somedata/"
•	    output_data = "s3://somedata/output/"
•	
•	    auto_insurance_data(spark, input_data, output_data)
•	    insurance_log_data(spark, input_data, output_data)
