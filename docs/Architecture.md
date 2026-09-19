Tech Stack
Backend: Python with FastAPI and Pandas
Database: PostgreSQL
Analytics Engine: DuckDB
Forecasting: Prophet
AI Agent: LangChain with an LLM API (Claude or Groq)
Dashboard: Streamlit
Containerization: Docker and Docker Compose

Folder Structure
app/ingestion.py - watches data/incoming and loads new files into Postgres
app/db.py - handles the Postgres connection and table creation logic
app/schema_inference.py - detects column types from incoming data
app/forecasting.py - runs Prophet on any dataset with a date column
app/agent.py - the text to SQL logic using LangChain
dashboard/main.py - the Streamlit app, this is what the user actually opens in browser
docker/docker-compose.yml - spins up Postgres and the app together
data/incoming/ - drop zone for raw CSV files
docs/ - all planning docs

Data Flow
A CSV file gets dropped into data/incoming
ingestion.py detects the new file, reads it with Pandas
schema_inference.py figures out column types
db.py creates or updates the matching table in Postgres
DuckDB reads directly from Postgres for fast analytical queries
forecasting.py checks if there's a usable date and numeric column, if yes it runs Prophet and saves the forecast back
agent.py lets the user type a question in English, converts it to SQL, runs it, returns the answer
dashboard/main.py displays the raw data, auto charts, and the forecast, and has a text box wired to agent.py for questions

How Pieces Talk to Each Other
Everything runs inside Docker Compose as separate services, Postgres as its own container, the Python app as another, connected through a shared Docker network so they can reach each other by service name instead of localhost.