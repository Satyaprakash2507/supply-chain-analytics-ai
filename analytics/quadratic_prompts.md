# Analytical Logic Implemented Using Quadratic

This document documents the analytical logic executed in **Quadratic** to prepare datasets and compute supply chain KPIs.  
The logic described here is based on structured analytical prompts used to generate reproducible and validated outputs.

---

## Overview

Quadratic is used as the analytical execution layer to:
- Create supporting analytical tables
- Clean and standardize raw data
- Merge transactional and dimensional datasets
- Compute business KPIs aligned with supply chain definitions

All analytical steps are explicitly defined and validated.

---

## Date Dimension Creation

### Objective
Enable time-based analysis and consistent aggregation across reporting periods.

### Logic Implemented
- Generate a continuous date table covering the analysis window  
- Date range: **March 1, 2025 to May 31, 2025**

This table is used to support time-series analysis and KPI aggregation.

---

## Exchange Rate Reference Table

### Objective
Normalize monetary values into a single reporting currency (INR).

### Logic Implemented
- Create an exchange rate table covering **March 1, 2025 to May 17, 2025**
- Fetch daily USD to INR exchange rates using a historical exchange rate API
- Store exchange rates at a daily granularity
- Join exchange rates with transactional data using the order placement date

This ensures consistent financial reporting across currencies.

---

## Fact Summary Table Preparation

A consolidated fact table (`fact_summary`) is created to support downstream KPI computation.

### Data Sources
- `fact_order_line`
- `dim_products`
- `dim_customers`
- `exchange_rate`

### Data Cleaning Logic
- Convert `product_id` and `customer_id` to numeric format
- Remove leading and trailing whitespace from identifier fields
- Remove records with missing identifiers
- Convert identifiers to integers
- Convert date fields to datetime format

### Data Merging Logic
- Merge order data with product data using `product_id`
- Merge the result with customer data using `customer_id`
- Merge the result with exchange rate data using order placement date

### Amount Calculation Logic
- For USD transactions:
  - `total_amount = price_USD × USD_INR_rate × order_quantity`
- For INR transactions:
  - `total_amount = price_INR × order_quantity`

### Final Dataset Cleanup
- Remove intermediate calculation columns
- Retain only essential analytical fields:
  - Order identifiers
  - Product and customer identifiers
  - Order and delivery dates
  - Quantities and delivery status
  - Total order amount (INR)

The resulting table serves as the primary analytical dataset.

---

## Business KPI Computation

The following supply chain KPIs are computed using the prepared fact summary table:

1. Total Order Lines  
2. Line Fill Rate  
3. Volume Fill Rate  
4. Total Orders  
5. On-Time Delivery Percentage  
6. In-Full Delivery Percentage  
7. On-Time In-Full (OTIF) Percentage  

Each KPI follows clearly defined business rules consistent with standard supply chain metrics.

---

## Customer-Level Performance Analysis

### Objective
Evaluate customer performance based on order value and delivery reliability.

### Logic Implemented
- Aggregate total order value by customer
- Compute OT %, IF %, and OTIF % at the customer level
- Rank customers by total order value
- Include customer metadata:
  - Customer ID
  - Customer Name
  - City

---

## Geographic Customer Analysis (India)

### Objective
Analyze customer performance within a specific geography.

### Logic Implemented
- Filter customers based on country = India
- Rank top 5 customers by order value
- Compute delivery KPIs (OT %, IF %, OTIF %)
- Include customer identifiers and city-level details

---

## Validation and Quality Checks

- Aggregated values are cross-validated against base tables
- KPI calculations are reviewed for consistency
- Business rules are aligned with documented supply chain definitions

---

## Usage in This Project

Quadratic is used to:
- Transform raw operational data into analysis-ready datasets
- Compute validated supply chain KPIs
- Support structured performance analysis at order and customer levels

---

## Conclusion

The analytical logic implemented in Quadratic enables consistent data preparation, validated KPI computation, and structured supply chain performance analysis using well-defined business rules.

