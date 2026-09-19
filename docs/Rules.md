Libraries to Use
Python, FastAPI, Pandas, SQLAlchemy, Prophet, LangChain, Streamlit, Plotly, psycopg2 for Postgres connection

Libraries to Avoid for V1
No MongoDB, no vector databases, no BigQuery or Snowflake SDKs, no Terraform, no Kubernetes, keep it Docker Compose only until V1 is stable

Coding Standards
Every function must have a clear docstring
No hardcoded file paths, use environment variables or a config file
No hardcoded API keys anywhere in code, always use a .env file and add it to .gitignore
Errors must be caught and logged, never let the ingestion script crash silently on a bad file

Boundaries for AI Tools
Do not add new major dependencies without checking back first
Do not skip the schema drift handling even if it seems like extra work
Keep code modular, one responsibility per file, don't cram logic into dashboard/main.py