# End-to-End Supply Chain Analytics Using Automation and AI-Assisted Analytics

## Overview

This project implements an **end-to-end supply chain analytics pipeline** that automates data ingestion, stores structured data in a cloud-based PostgreSQL database, and generates validated business KPIs using an AI-assisted analytics environment.

The solution demonstrates how automation, structured data modeling, and analytical logic can be combined to support scalable and repeatable supply chain performance analysis.

---

## Problem Statement

Supply chain data is often distributed across multiple sources and formats, making manual analysis time-consuming and error-prone.

This project addresses the challenge by:
- Automating data ingestion from external sources
- Centralizing data in a structured database
- Applying standardized business logic to compute key supply chain KPIs

---

## Solution Approach

The project follows a layered architecture:

1. **Automation Layer**  
   Orchestrates data ingestion and integration workflows.

2. **Data Storage Layer**  
   Stores transactional and dimensional data in a structured relational model.

3. **Analytics Layer**  
   Performs data preparation, transformation, and KPI computation using validated analytical logic.

---

## Architecture Overview

```text
External Data Sources
        ↓
n8n (Cloud-Based Automation)
        ↓
PostgreSQL (Supabase)
        ↓
Quadratic (Analytics Layer)
        ↓
Supply Chain KPIs & Insights
````

---

## Technology Stack

* **Automation:** n8n (Cloud-based)
* **Database:** PostgreSQL (Supabase)
* **Analytics:** Quadratic
* **Authentication:** OAuth 2.0 (Gmail)
* **Data Format:** CSV
* **Domain:** Supply Chain Analytics

---

## Data Model

The analytical model consists of:

### Fact Tables

* Order data
* Order line data

### Dimension Tables

* Customers
* Products
* Targets and reference data

### Reference Tables

* Date dimension
* Exchange rate table

This structure supports efficient aggregation and KPI computation.

---

## Data Pipeline Workflow

1. Data is ingested through automated workflows.
2. Raw data is validated and structured.
3. Data is stored in PostgreSQL using a relational schema.
4. Analytical tables are prepared in the analytics layer.
5. Business KPIs are computed using standardized definitions.

---

## Analytical Logic and KPIs

The following supply chain KPIs are computed:

* Total Orders
* Total Order Lines
* Line Fill Rate
* Volume Fill Rate
* On-Time Delivery Percentage
* In-Full Delivery Percentage
* On-Time In-Full (OTIF) Percentage

All KPIs are derived using clearly defined business rules aligned with standard supply chain practices.

---

## Customer and Geographic Analysis

In addition to overall performance metrics, the project includes:

* Customer-level performance ranking
* Delivery reliability analysis by customer
* Geographic segmentation for regional insights

---

## Security and Access Management

* OAuth 2.0 is used for secure email-based integrations.
* Credentials are stored securely and are not committed to source control.
* Database access is restricted to authorized services.

---

## Repository Structure

```text
supply-chain-analytics-ai/
│
├── README.md
│
├── docs/
│   ├── n8n_setup_web.md
│   ├── supabase_postgres_setup.md
│   └── gmail_oauth_setup.md
│
├── analytics/
│   └── quadratic_prompts.md
│
├── business/
│   ├── supply_chain_concepts.md
│   └── kpi_definitions.md
│
├── Dataset/
│
├── screenshots/
```

---

## Key Learnings

* Designed an end-to-end analytics pipeline from ingestion to insights
* Applied structured data modeling for analytical use cases
* Implemented standardized supply chain KPIs
* Combined automation with analytical validation
* Applied domain knowledge to interpret operational data

---

## Usage

This repository serves as:

* A reference implementation for supply chain analytics
* A demonstration of automation-driven data pipelines
* A portfolio project showcasing analytics and domain understanding

---

## Author

**Satyaprakash Singh Yadav**
Data Analytics | Automation | API & Data Validation Background

---

## Conclusion

This project demonstrates how automation, structured data storage, and validated analytical logic can be combined to produce reliable and scalable supply chain performance insights.

```

---
