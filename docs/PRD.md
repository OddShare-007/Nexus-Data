Project Name: NexusData

Problem Statement
Most personal or small business datasets sit as static CSV or JSON files with no real infrastructure around them. There is no automatic way to store them properly, query them in plain language, or get a forecast on trends without writing custom code every single time. NexusData solves this by giving any dataset an instant, reusable data pipeline the moment it is dropped in.

Target Users
Freelance clients or small businesses who have raw operational data (sales, inventory, logs) and want quick analytics without hiring a data engineer. Secondary audience is hiring managers and recruiters evaluating this as a portfolio piece.

V1 Scope (what we are actually building first)
Ingestion of CSV files through a Python script
Storage in PostgreSQL with automatic table creation based on the data
Analytical layer using DuckDB for fast querying
One forecasting module using Prophet for any dataset with a date column and a numeric target
A simple text to SQL agent so the user can ask questions in plain English
A Streamlit dashboard showing the uploaded data, auto generated charts, and the forecast
Everything running locally through Docker Compose

Out of Scope for V1 (postponed to V2 and beyond)
MongoDB or NoSQL storage
Vector database and semantic search
BigQuery or Snowflake cloud warehouse sync
Terraform cloud deployment
Multi project data ingestion from other portfolio projects

Success Criteria for V1
A user can drop any reasonably clean CSV into the incoming folder, it lands in Postgres automatically, DuckDB can query it fast, Prophet generates a forecast if there is a date column, and the Streamlit dashboard shows all of this without any manual database work.