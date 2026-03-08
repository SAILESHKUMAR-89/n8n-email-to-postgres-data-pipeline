📊 Automated Email-to-PostgreSQL Data Pipeline using n8n
🚀 Project Overview

This project demonstrates an automated data pipeline that processes daily sales reports received via email. The workflow uses n8n automation to monitor incoming emails, extract CSV datasets, and load them into a PostgreSQL database hosted on Supabase.
The stored data is then connected to Quadratic AI Spreadsheet for further data analysis and table creation.
This project simulates a real-world data engineering workflow where operational data is automatically ingested, stored, and analyzed.

🏗️ Pipeline Architecture
Email (Daily Sales Reports)
        │
        ▼
n8n Gmail Trigger
        │
        ▼
CSV File Extraction
        │
        ▼
Supabase PostgreSQL Database
        │
        ▼
Quadratic AI Spreadsheet Analysis
⚙️ Workflow Explanation

1️⃣ Email Data Ingestion
The system monitors incoming Gmail messages with the subject "Daily Sales" using an n8n Gmail Trigger.
Whenever a new email arrives:
1. n8n automatically downloads the attached datasets
2. The automation workflow processes the files

2️⃣ Data Extraction
The incoming email contains four datasets:
1. fact_aggregate_india
2. fact_aggregate_usa
3. fact_order_line_india
4. fact_order_line_usa
These CSV files represent daily operational sales reports.

3️⃣ Data Loading into PostgreSQL
The extracted data is inserted into Supabase PostgreSQL tables.
Fact Tables
1. fact_aggregate
2. fact_order_line
Dimension Tables
1. dim_customers
2. dim_products
3. dim_targets_orders
The database automatically updates whenever a new sales report email arrives.

📊 Data Analysis using Quadratic AI Spreadsheet

The PostgreSQL database is connected to Quadratic AI Spreadsheet using Supabase session credentials.
Within Quadratic, additional analytical tables were created:
1. dim_date
2. exchange_rate
3. fact_aggregate
These tables allow further data exploration and analysis.

🛠️ Technologies Used
Tool Purpose
1. n8n	Workflow automation
2. Gmail API Email trigger for pipeline
3. Supabase PostgreSQL database hosting
4. PostgreSQL Data storage
5. Quadratic AI Spreadsheet Data analysis
CSV Files Input data format


📂 Project Structure

The repository is organized into the following folders:
n8n/
Contains the automation workflow used to ingest data from Gmail and load it into PostgreSQL.
postgres_data_ingestion_workflow.json – n8n workflow configuration file.

data/
This folder contains datasets used in the pipeline.
        incoming_mail_data/
        Contains sample datasets that simulate daily sales reports received through email.
                1. fact_aggregate_india_2025-05-17.csv
                2. fact_aggregate_usa_2025-05-17.csv
                3. fact_order_line_india_2025-05-17.csv
                4. fact_order_line_usa_2025-05-17.csv
        postgres_input_files/
        Contains datasets used to initialize database tables in Supabase PostgreSQL.
                1. dim_customers.csv
                2. dim_products.csv
                3. dim_targets_orders.csv
                4. fact_aggregate.csv
                5. fact_order_line.csv

quadratic/
Contains datasets generated and exported from the Quadratic AI Spreadsheet during analysis.
        1. dim_date.csv
        2. exchange_rate.csv
        3. fact_aggregate.csv

screenshots/
Contains images demonstrating the project workflow and outputs.
        1. n8n workflow automation screenshot
        2. Supabase database tables screenshot
        3. Quadratic spreadsheet analysis screenshot

README.md
Contains documentation describing the project, pipeline workflow, technologies used, and project structure.

🔗 Project Access Links
Supabase Database

Supabase PostgreSQL Project
[Supabase project link here](https://jmblbqjvygoxdmseinsk.supabase.co)

Quadratic Spreadsheet

Quadratic AI Spreadsheet (View Only)
[Quadratic view link here](https://app.quadratichq.com/file/786b73f5-5e8f-4a67-85a7-bb96831a7b82)

📸 Screenshots

Added screenshots of:
1. n8n workflow automation
2. Supabase database tables
3. Quadratic spreadsheet tables

🎯 Key Features

✔ Automated email-based data ingestion
✔ Workflow automation using n8n
✔ PostgreSQL database integration via Supabase
✔ Fact and dimension table modeling
✔ AI-assisted analysis using Quadratic Spreadsheet

📚 Key Learnings
-Building automated ETL pipelines
-Email-based data ingestion
-PostgreSQL database integration
-Workflow orchestration using n8n
-AI-assisted spreadsheet analytics

⭐ If you found this project useful

Feel free to star the repository ⭐
