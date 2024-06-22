# Environmental Data Pipeline Project

## Introduction

In today's data-driven environment, the capacity to quickly gather, organise, and analyse data is critical for making sound decisions. This project aims to provide a complete data pipeline that easily incorporates diverse technologies for handling environmental data. Using open-source technology, the project intends to create a scalable, dependable, and user-friendly system for data intake, storage, processing, and analysis. The final system will store and manage huge datasets while also providing sophisticated analytical capabilities via interactive dashboards and visualisations.

## Project Overview

The goal of this project is to create a sophisticated system for collecting, processing, and analysing environmental data. It makes use of a variety of free software tools to guarantee that the system can manage massive volumes of data while being dependable and user-friendly.

## High-level Architecture

The system consists of several critical parts:

1. **Data Ingestion (Data Collection):**
    - **Apache Airflow:** Schedules and organises the process of gathering data from numerous sources, such as websites or databases, and storing it in a system called MinIO.

2. **Data Storage (Storing Data):**
    - **MinIO:** A storage solution comparable to Amazon S3. It keeps both raw and processed data organised.
    - **Apache Iceberg:** Manages and organises structured data, such as database tables. It maintains track of data changes, organises it into divisions (parts), and saves versions for easier access and usage.

3. **Data Processing:**
    - **Apache Spark:** A powerful tool for processing and transforming data stored in Apache Iceberg. It can handle enormous datasets fast and execute sophisticated actions on them.

4. **Data Analysis:**
    - **Power BI:** A tool for creating interactive reports and dashboards. It connects to the data and displays a visual interface for analysing it.

## Components

- **Apache Airflow:**
    - Orchestrates or manages the steps required to gather and process data.
    - Schedules when and how data is taken from various sources and stored in MinIO.
    - Uses PostgreSQL to manage operations and metadata (data-related information).

- **MinIO:**
    - Serves as a storage system compatible with S3 (an Amazon storage system).
    - Stores data in an organised format, making it simple to retrieve and administer.

- **Apache Iceberg:**
    - Manages the structured data included in MinIO.
    - Keeps track of the data schema (how the data is organised), splits the data for optimal usage, and keeps many copies of the data.

- **Apache Spark:**
    - Processes and converts data from Iceberg.
    - DataFrame API and SQL are used to perform sophisticated data operations and transformations.

- **Power BI:**
    - A tool for building dashboards and visualising data.
    - Connects to data sources, enabling deep analysis and interactive visualisations.

- **PostgreSQL:**
    - Used by Apache Airflow to store information and monitor the data collecting and processing phases.

- **Dremio:**
    - Offers quick and easy access to data for analysis.
    - Connects to several data sources, including the Iceberg tables in MinIO, and provides a uniform SQL interface for accessing and analysing data.

## Workflow

### Workflow Description

1. **Data Ingestion:**
    - Apache Airflow orchestrates ETL operations using DAGs to retrieve data from APIs at periodic intervals.
    - Initial processing: Handles different data formats (JSON, CSV, and XML) and performs operations such as data type conversion and missing value imputation.
    - MinIO Storage organizes ingested data into organized buckets and directories for simple access.

2. **Data Storage:**
    - MinIO acts as the principal object storage system, organizing raw and processed data.
    - Apache Iceberg manages structured data via schema management, segmentation, and versioning. Enables efficient searching while also supporting schema evolution and time travel queries.

3. **Data Processing:**
    - Apache Spark handles huge datasets efficiently by processing and transforming data from Iceberg tables using distributed computing.
    - Spark Jobs execute cleaning of data, transformations, and complex operations such as aggregation and joining.

4. **Data Analysis:**
    - Dremio offers a quick SQL interface for querying Iceberg tables. Improves performance through data reflection.
    - Power BI connects to data sources to generate interactive dashboards and visualizations, with an easy-to-use interface that improves user experience.

## Key Benefits

- **Scalability:** Iceberg's segmentation and indexing improve scalability, allowing for efficient processing of massive data volumes through distributed computation and storage.
- **Flexibility:** Supports schema evolution and versioning for time travel queries.
- **Efficiency:**
    - Fast object storage with little I/O.
    - Improved data management using Iceberg's segmentation and indexing.
    - Efficient data processing with Spark's distributed computing.
    - Improved query speed using Dremio's data reflection.
- **Easy to use:**
    - Power BI enables intuitive data visualization.
    - Self-service analytics using Dremio's SQL interface.
    - Docker and Docker Compose enable easier deployment and administration.

## Deploying

### Docker and Docker Compose:

- Containerize each component for independent and simple administration.
- Docker Compose handles several containers for easier deployment.

### Component Deployment:

- **PostgreSQL:** Provides persistent data storage for Airflow information.
- **Apache Airflow:** Uses PostgreSQL for metadata and MinIO for logs.
- **MinIO:** Provides S3-compatible storage with key-based access control.
- **Apache Iceberg and Spark:** Deployed as containers to ensure efficient data processing and administration.
- **Power BI with Dremio:** Provides data analysis and visualization, including connections to MinIO and Iceberg.

## Conclusion

### Achievements

- Integrates open-source technologies to create a strong data pipeline.
- Effectively manages enormous data quantities.
- Easy deployment using Docker and Docker Compose.
- Efficient data management using MinIO and Iceberg.
- Spark enables fast data processing.
- Easy data analysis with Dremio and Power BI.

### Future Work

- Integrate more data sources (IoT devices, weather stations).
- Improve analytics with machine learning and predictive analytics.
- Use Kubernetes to automate deployment, improving scalability and dependability.

### Final Thoughts

Utilizes open-source technology to create scalable, flexible, and efficient data pipelines. Offers extensive environmental data monitoring and analysis. Documentation facilitates knowledge of design and workflow, hence facilitating future development and advancements.

