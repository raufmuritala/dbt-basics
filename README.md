DBT Basics — End-to-End dbt + BigQuery Project

This repository contains my first complete analytics engineering workflow using dbt (Data Build Tool) connected to Google Cloud Platform (GCP).
The project includes ingestion of raw data, modeling, transformation, testing, documentation, and materialization of final tables into a dedicated BigQuery dataset: dbt_rmuritala.

Project Overview

Objective:

To build a structured, production-ready dbt project demonstrating:

Data transformation using SQL

Model organization (staging, intermediate, final)

Automated testing

Use of macros and snapshots

Deployment of transformed data into BigQuery

Environment Setup
Tools Used:

dbt Cloud

Google BigQuery

GCP Service Account for authentication

GitHub for version control



The project is configured to write all transformed tables into:

lofty-defender-389421.dbt_rmuritala

Project Structure
dbt-basics/
│
├── analyses/
├── macros/
├── models/
├── seeds/
├── snapshots/
├── tests/
├── dbt_project.yml
└── README.md

Key Components

models/
Contains staging, intermediate, and final models. These handle cleaning, transformation, and preparation of raw data.

tests/
Includes schema tests for uniqueness, not-null, and accepted values.

macros/
Contains reusable SQL functions for cleaner and more maintainable logic.

snapshots/
Tracks historical changes in selected tables.

What Was Implemented
1. BigQuery Connection

Configured authentication using a GCP service account JSON key.
dbt Cloud successfully connected to BigQuery and targeted the dataset dbt_rmuritala.

2. Data Modeling

Built the following model layers:

Staging models:
Cleaned raw tables, standardized naming conventions, casted data types, and applied initial transformations.

Intermediate models:
Applied business logic transformations, joins, and aggregations.

Final models:
Materialized analysis-ready tables back into BigQuery.

3. Tests

Added tests to ensure data quality:

Unique constraints

Not-null constraints

Accepted values

4. Snapshots and Macros

Created snapshots to capture slowly changing records.

Wrote macros to eliminate repetitive SQL logic and enforce consistency.

How to Run This Project

To build the models:

dbt run


To execute all tests:

dbt test



### Resources:
- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
- Check out [Discourse](https://discourse.getdbt.com/) for commonly asked questions and answers
- Join the [dbt community](https://getdbt.com/community) to learn from other analytics engineers
- Find [dbt events](https://events.getdbt.com) near you
- Check out [the blog](https://blog.getdbt.com/) for the latest news on dbt's development and best practices