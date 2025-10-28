# Uber Data Engineering Pipeline

An end-to-end ETL pipeline to process Uber trip data, model it into a star schema, and load it into a data warehouse for analytics.

## Problem Statement
To enable business intelligence and data analysis on Uber trip data, a robust pipeline was needed to process raw data from various sources, transform it into a structured format, and load it into a central data warehouse.

## Objective
To design and implement an ETL (Extract, Transform, Load) pipeline that:
- Extracts Uber trip data from a source.
- Transforms the raw data into a star schema dimensional model.
- Loads the transformed data into Google BigQuery.
- Allows for analytical queries on the processed data.

## Data Collection & Summary
The dataset used is the TLC Trip Record Data, which contains information about taxi trips in New York City. The data includes fields like pickup and drop-off times and locations, trip distances, fares, payment types, and passenger counts.
A sample of 100,000 records was used for this project.

## Project Workflow
The project follows a standard ETL workflow orchestrated by Mage:
1.  **Extract**: Data is extracted from a `.csv` file hosted on Google Cloud Storage.
2.  **Transform**: The raw data is transformed using Python and Pandas into a **Star Schema**. This involves creating a central `fact_table` and six dimension tables (`datetime_dim`, `passenger_count_dim`, etc.).
3.  **Load**: The transformed tables are loaded into Google BigQuery, making them available for analysis.
4.  **Analyze**: A SQL query is run in BigQuery to join the tables and create a final denormalized analytics view.

## Key Metrics
- **Total Trips Analyzed**: 100,000
- **Average Trip Distance**: 3.03 miles
- **Average Fare Amount**: $13.25

## Tools and Technologies
- **Programming Language**: Python (with Pandas)
- **Orchestration**: Mage.ai
- **Cloud Platform**: Google Cloud Platform (GCP)
  - Google Cloud Storage
  - Google BigQuery
  - Compute Instance
- **Analytics**: SQL

## Data Model
The project uses a star schema data model to organize the data for efficient querying and analysis.

<img src="data_model.jpeg" alt="Data Model">

## Conclusion
This project successfully built a modern, scalable data engineering pipeline. The resulting data model in BigQuery allows analysts to easily query key business metrics. The choice of a star schema is well-suited for the analytical queries required by the business, demonstrating an understanding of data warehousing principles.
