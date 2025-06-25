
# End to End Data Analytics Project: Yelp Business Reviews Analysis

This project demonstrates a complete data analytics workflow using Python, Snowflake, and SQL on the Yelp open dataset. It covers data ingestion, transformation, and analysis, including sentiment analysis on Yelp reviews.

## Overview

- **Dataset:** Yelp open dataset (~5GB JSON file with ~7 million reviews)
- **Tools used:** Python, AWS S3, Snowflake, SQL
- **Key steps:**
  - Splitting large JSON files into smaller chunks using Python for faster parallel ingestion
  - Loading data from S3 local machine Snowflake tables with semi-structured JSON data using the VARIANT data type
  - Creating Python User Defined Functions (UDFs) in Snowflake for sentiment analysis of review texts
  - Writing SQL queries to answer medium to hard-level analytical questions on the data

## Dataset Details

- **reviews.json:** Contains review details including review ID, business ID, star rating, review text, and date
- **business.json:** Contains business information including business ID, name, address, city, state, postal code, categories, latitude, longitude, stars, and review count

## Project Workflow

1. **Splitting JSON File:**  
   The large reviews JSON file is split into multiple smaller files (e.g., 20-25 files) using a Python script. This enables faster parallel upload to S3 and ingestion into Snowflake.

2. **Loading Data into Snowflake:**  
   - Create Snowflake tables with a single VARIANT column to store JSON data.  
   - Use Snowflake's `COPY INTO` command to load data from S3 into Snowflake tables in parallel.

3. **Transforming JSON to Tabular Format:**  
   Use Snowflake SQL functions to parse JSON data from VARIANT columns into structured columns for analysis.

4. **Sentiment Analysis with Python UDF:**  
   A Python UDF is created inside Snowflake using the TextBlob library to classify review texts into positive, neutral, or negative sentiments.

5. **SQL Analysis:**  
   Write SQL queries to explore the data and answer interesting business questions, leveraging the structured data and sentiment analysis results.
