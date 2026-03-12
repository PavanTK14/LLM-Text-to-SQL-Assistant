# LLM-Powered Natural Language to SQL System

An intelligent **Natural Language → SQL query generator** built using **AWS Bedrock**, **Claude Sonnet**, **FAISS**, and **Streamlit**.
This system allows users to ask questions in natural language and automatically converts them into **valid SQL queries** that run against a database.

---

## 🚀 Project Overview

Traditional database querying requires knowledge of SQL. This project leverages **Large Language Models (LLMs)** to translate human language questions into executable SQL queries.

Users can simply ask:

> "Show top customers by transaction amount"

and the system automatically generates and executes the SQL query.

---

##  Architecture

Natural Language Query
↓
Streamlit UI
↓
LLM (AWS Bedrock – Claude Sonnet)
↓
SQL Query Generation
↓
DuckDB Execution Engine
↓
Query Results

Additional components:

* **FAISS Vector Search** → Similar question retrieval
* **TF-IDF Embeddings** → Column semantic search
* **Query Cache** → Faster repeated queries
* **Schema Awareness** → Accurate SQL generation

---

## ⚙️ Tech Stack

* Python
* Streamlit (UI)
* AWS Bedrock (LLM inference)
* Claude Sonnet (SQL generation)
* FAISS (vector similarity search)
* DuckDB (query execution)
* Pandas (data processing)
* TF-IDF (feature extraction)

---

## 📂 Project Structure

```
text-to-sql-ai
│
├── app.py
├── Banking_Dataset.xlsx
├── requirements.txt
├── README.md
│
├── data/
│
├── screenshots/
│
└── utils/
```

---

## Key Features

✔ Natural language to SQL generation
✔ Schema-aware query generation
✔ Semantic column matching using TF-IDF
✔ FAISS vector search for similar queries
✔ Query caching for faster responses
✔ SQL validation before execution
✔ Interactive Streamlit interface

---

##  Example

**User Input**

```
Show all customers with balance greater than 10000
```

**Generated SQL**

```
SELECT *
FROM Customers
WHERE balance > 10000;
```

**Output**

| Customer | Balance |
| -------- | ------- |
| Pavan    | 15000   |
| Kumar   | 12000   |

---

## 🛡 SQL Safety Checks

The system prevents unsafe SQL operations:

* DROP
* DELETE
* ALTER
* SQL comment injection (`--`)

Queries are validated before execution using **DuckDB EXPLAIN**.

---

## ⚡ How It Works

1. Load Excel dataset into **DuckDB**
2. Extract database schema
3. Convert schema columns into **TF-IDF embeddings**
4. Store embeddings in **FAISS index**




NL2SQL RAG SQL Generator

Convert natural language queries into valid SQL with RAG, hybrid prompting, and guardrails.

This project demonstrates:

Multi-source database integration (S3 Excel/CSV + PostgreSQL/MySQL/SQL Server)

DuckDB in-memory execution for fast query results

Schema chunking & RAG with FAISS for relevant schema retrieval

Hybrid prompting with reflection to improve LLM reasoning and prevent hallucinations

Guardrails to block destructive or invalid SQL statements

Streamlit UI for interactive question-to-SQL exploration

Ideal for data analysts, AI/ML engineers, and anyone exploring LLM-assisted SQL generation.
   
