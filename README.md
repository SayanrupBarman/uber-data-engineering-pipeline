# Uber Data Engineering Pipeline

An end-to-end data engineering project for processing Uber trip data using Python, Mage, and Google BigQuery.

## Problem Statement
The goal of this project is to build a robust and scalable data pipeline that processes Uber trip data. The pipeline needs to handle data extraction, transformation into a structured format, and loading into a data warehouse for analytics. This will enable business intelligence and data analysis to derive insights from the trip data.

## Objective
To design and implement an ETL (Extract, Transform, Load) pipeline that:
- Extracts Uber trip data from a source.
- Transforms the raw data into a star schema dimensional model.
- Loads the transformed data into Google BigQuery.
- Allows for analytical queries on the processed data.

## Data Collection & Summary
The dataset used is the TLC Trip Record Data, which contains information about taxi trips in New York City. The data includes fields like pickup and drop-off times and locations, trip distances, fares, payment types, and passenger counts.

## Project Workflow
The project follows a standard ETL workflow orchestrated by Mage:
1.  **Extract**: Data is extracted from a `.csv` file hosted on Google Cloud Storage.
2.  **Transform**: The raw data is transformed using Python and Pandas into a star schema. This involves creating a fact table and several dimension tables (datetime, passenger count, trip distance, rate code, location, and payment type).
3.  **Load**: The transformed tables are loaded into Google BigQuery, making them available for analysis.
4.  **Analyze**: SQL queries are run in BigQuery to join the tables and create a final analytics view.

<img src="architecture.jpg" alt="Project Architecture">

## Key Insights (from `uber_data.csv`)
- **Total Trips Analyzed**: 100,000
- **Average Trip Distance**: 3.03 miles
- **Total Passengers Transported**: 192,917
- **Average Fare Amount**: $13.25

## Tools and Technologies
- **Programming Language**: Python (with Pandas)
- **Orchestration**: Mage.ai
- **Cloud Platform**: Google Cloud Platform (GCP)
  - Google Cloud Storage
  - Google BigQuery
  - Compute Instance
- **Analytics**: SQL
- **Visualization**: Looker Studio (or similar BI tools)

## Data Model
The project uses a star schema data model to organize the data for efficient querying and analysis.

<img src="data_model.jpeg" alt="Data Model">

## Conclusion and Recommendations
This project successfully demonstrates the implementation of a modern data engineering pipeline. The choice of a star schema is well-suited for analytical queries. For future work, the pipeline could be extended to handle real-time data streaming, incorporate more complex data quality checks, and automate the entire workflow with more advanced scheduling and monitoring.