# ML Price Intelligence Pipeline

End-to-end data engineering pipeline for e-commerce price intelligence, built on top of the Mercado Livre public API.

## Overview

This project implements a production-grade data pipeline that collects, processes, and models product pricing data from Mercado Livre — Brazil's largest e-commerce platform. The goal is to answer real business questions about pricing behavior, seller competition, and market dynamics.

## Business Questions

- How do prices vary across sellers for the same product?
- Is there a correlation between seller reputation and pricing strategy?
- Do products with free shipping have inflated prices compared to those without?

## Architecture
Mercado Livre API

↓

[Python + requests]

↓

S3 Bronze          ← raw JSON, partitioned by date

↓

[PySpark]

↓

S3 Silver          ← clean Parquet, typed and deduplicated

↓

[dbt]

↓

S3 Gold            ← analytical models with SCD Type 2

↓

[Analysis + Insights]

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Ingestion | Python, Requests, boto3 |
| Storage | AWS S3, Parquet |
| Processing | PySpark |
| Modeling | dbt |
| Orchestration | Apache Airflow |
| Quality | Great Expectations |
| CI/CD | GitHub Actions |

## Project Structure
ml-price-intelligence/

├── ingestion/        # API collection scripts

├── processing/       # PySpark transformation jobs

├── dbt/              # Analytical models

├── orchestration/    # Airflow DAGs

├── quality/          # Great Expectations validations

├── tests/            # Unit tests

└── docs/             # Additional documentation

## Setup

```bash
git clone https://github.com/vtohrq/ml-price-intelligence.git
cd ml-price-intelligence
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env  # fill in your credentials
```

## Status

🚧 Work in progress

| Phase | Status |
|-------|--------|
| 0 - Setup | ✅ Done |
| 1 - Bronze Ingestion | 🔄 In progress |
| 2 - Silver Processing | ⏳ Pending |
| 3 - Gold Modeling | ⏳ Pending |
| 4 - Orchestration | ⏳ Pending |
| 5 - Data Quality | ⏳ Pending |
| 6 - CI/CD | ⏳ Pending |

## Author

Victor Oliveira — [LinkedIn](https://www.linkedin.com/in/seu-perfil) · [GitHub](https://github.com/vtohrq)
