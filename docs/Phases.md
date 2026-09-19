Phase 1: Environment Setup
Docker Compose file with Postgres and app service
Confirm containers can talk to each other

Phase 2: Ingestion Pipeline
Build ingestion.py to watch data/incoming
Build schema_inference.py to detect column types
Build db.py to create tables and insert data automatically

Phase 3: Analytics and Forecasting
Connect DuckDB to read from Postgres
Build forecasting.py using Prophet
Test forecasting on at least two different sample datasets

Phase 4: AI Agent and Dashboard
Build agent.py for text to SQL
Build dashboard/main.py in Streamlit
Wire up the question box in the dashboard to agent.py

Phase 5: Polish and Portfolio Prep
Write the real README with screenshots
Record a short demo video or gif
Push final version, write LinkedIn post