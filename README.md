# ai-data-engineering-sprint

Here is the 1-Month Aggressive Sprint.
Ground Rules

    6 days/week, 9–11 hours/day. One day off for recovery.
    No passive video-watching. Build code every single day.
    Use Azure free tier + Databricks Community Edition. If you hit credit limits, use local Docker + MinIO + PostgreSQL + pgvector as a free stand-in.
    Ship 3 projects. GitHub portfolio > certificates.

Week 1: Engineering Foundations + Azure Data Core

Goal: Write production Python/SQL and build your first medallion lakehouse on Azure.
Day
	Focus	Key Tasks
1–2	Python for Data Engineering	Python 3.11+, type hints, Pydantic validation, logging, pytest, pathlib, virtual environments (uv or poetry). Pandas basics. Write a CLI that fetches a public API, validates, and saves to CSV/Parquet.
3–4	Advanced SQL	CTEs, window functions (ROW_NUMBER, LAG, LEAD), QUALIFY, query execution plans, indexing, partitioning. Solve 20 LeetCode-style SQL problems.
5	Azure Storage & Security	ADLS Gen2 (hierarchical namespace), storage account keys vs. Managed Identity vs. SAS, Azure Key Vault, Azure SQL Database.
6	Azure Data Factory (ADF)	Copy activity, mapping data flows, parameters, triggers, pipeline monitoring. Ingest a public dataset (e.g., NYC Taxi) from URL → ADLS Gen2 → Azure SQL.
7	Project 1: Bronze Lakehouse	Ingest raw data via ADF → ADLS Gen2 (raw folder). Use Databricks Community + PySpark to read raw → write Delta Lake (Bronze). Add data quality check (row count, null checks). Push code to GitHub.

Time: ~60 hours.
Week 2: Silver/Gold, ML, and Orchestration

Goal: Transform data, train a model, and schedule everything.
Day
	Focus	Key Tasks
8–9	Databricks + Delta Lake	PySpark DataFrames, joins, broadcasts, caching. Delta Lake: MERGE, time travel, VACUUM, OPTIMIZE, Z-Ordering. Medallion architecture: Bronze → Silver → Gold.
10	dbt (data build tool)	Install dbt Core (or dbt Cloud free tier). Models, sources, seeds, snapshots, tests, documentation. Run dbt against Azure Synapse or local Postgres.
11–12	ML Basics + Azure ML	Scikit-learn: train/test split, metrics (RMSE, AUC-ROC), feature encoding. Azure ML workspace, compute cluster, registered model, batch scoring endpoint. Train a churn/propensity model.
13	Orchestration	Azure DevOps or GitHub Actions: trigger ADF pipeline, run Databricks notebook, run dbt. Basic CI/CD concept (even if manual).
14	Project 2: Batch ML Inference	Raw customer data → ADF → Databricks (Silver features) → train XGBoost model → register in Azure ML → batch predict → write predictions to ADLS Gold → visualize in Power BI. Document in GitHub README.

Time: ~60 hours.
Week 3: Generative AI & RAG Engineering

Goal: Build an AI application that retrieves enterprise data and answers questions.
Day
	Focus	Key Tasks
15–16	Azure OpenAI	Deploy GPT-4o and text-embedding-3-small in Azure OpenAI Studio. Chat completions API, system prompts, token counting, temperature, cost estimation.
17–18	Vector Search	Azure AI Search (vector index) or pgvector on Azure Database for PostgreSQL. Chunk PDFs/text, embed chunks, store vectors, run similarity search.
19–20	RAG with LangChain/LlamaIndex	Build a simple RAG chain: load docs → split → embed → retrieve → prompt → answer. Add citation/source tracking.
21	FastAPI + Streamlit	Expose your RAG chain via FastAPI endpoint. Build a Streamlit UI where a user uploads a PDF and asks questions.
22–23	Project 3: Enterprise RAG Chatbot	Ingest 5–10 PDFs → Azure Blob Storage → Azure AI Search vector index → Azure OpenAI → FastAPI backend → Streamlit frontend. Add evaluation: does the answer come from the source? (basic RAGAS or manual check).

Time: ~60 hours.
Week 4: Capstone, Resume, and Interview Launch

Goal: One end-to-end AI+Data system. Get hired.
Day
	Focus	Key Tasks
24–26	Capstone: “Real-Time Fraud + LLM Explainer”	Stream CSV events (simulate Kafka with Event Hubs or just a folder watcher) → Databricks Structured Streaming → Delta Lake → train Isolation Forest anomaly model → Azure ML online endpoint → when fraud detected, retrieve user history from Azure AI Search → Azure OpenAI generates plain-language fraud explanation → Power BI dashboard shows fraud rate + LLM explanations. Add GitHub Actions to deploy infra (Bicep/Terraform optional but impressive).
27	Resume & LinkedIn	Rewrite resume: “Data Engineer
28	Cert cramming (optional but fast)	Study for DP-203 (Data Engineering on Azure) and AI-102 (Azure AI Engineer) using Microsoft Learn + practice exams. Even if you don’t pass in 30 days, the study material structures your knowledge.
29–30	Interview prep + Apply	SQL live coding (window functions), Python (data structures + Pandas/PySpark), system design (draw a lakehouse diagram), behavioral stories (use your migration job as examples). Apply to 10+ jobs/day.

Time: ~50 hours.
