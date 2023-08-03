# ETL Orchestration in a Datalake

The goal of this project is to build a datalake on S3 with medallion architecture: Bronze, Silver, and Gold. The ETLs are implemented on AWS Lambda and orchestrated with Prefect. The data that has been used refers to the Nobel prizes celebrations by extracting the information from the nobelprize.org API.

![image](https://github.com/ivangprado/ETL_orchestration-Medallion_datalake/assets/6001254/d4176093-5d55-490a-ab09-4ed9512ebaf8)


### Steps

1. Create the bucket in S3 for the data lake. This bucket will have the prefixes: raw, bronze and silver.
2. Create the lambdas that make the API calls. The information obtained is transformed into a Pandas dataframe and saved in parquet format into the S3 bucket ("raw" prefix).
3. Create the lambda function for the ETL bronze that performs transformations on the raw data and stores the transformed data into the S3 bucket ("bronze" prefix).
4. Create the lambda function for the silver ETL that performs transformations on the bronze data and stores the transformed data into the S3 bucket ("silver" prefix).
5. Develop the flow and tasks to orchestrate ETLs with Prefect Core.
6. Answer analytical questions about the data stored in "silver".
