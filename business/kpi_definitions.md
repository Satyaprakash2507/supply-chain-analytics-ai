# KPI Definitions

This document defines the **key performance indicators (KPIs)** used to evaluate supply chain performance in this project.  
All KPIs are calculated using standardized definitions aligned with common supply chain practices.

---

## Total Orders

**Definition:**  
The total number of unique orders placed within the analysis period.

**Purpose:**  
Provides visibility into overall order volume and demand.

---

## Total Order Lines

**Definition:**  
The total number of individual order lines across all orders.

**Purpose:**  
Measures item-level demand and operational complexity.

---

## Line Fill Rate

**Definition:**  
The percentage of order lines successfully fulfilled, regardless of delivery time.

**Formula:**  
Line Fill Rate = (Fulfilled Order Lines / Total Order Lines) × 100


**Purpose:**  
Evaluates line-level fulfillment efficiency.

---

## Volume Fill Rate

**Definition:**  
The percentage of total ordered quantity that was successfully delivered.

**Formula:**  
Volume Fill Rate = (Delivered Quantity / Ordered Quantity) × 100


**Purpose:**  
Measures quantity-level fulfillment effectiveness.

---

## On-Time Delivery Percentage (OT %)

**Definition:**  
The percentage of orders delivered on or before the committed delivery date.

**Rule:**  
An order is considered on-time only if **all order lines** are delivered on time.

**Purpose:**  
Evaluates delivery timeliness.

---

## In-Full Delivery Percentage (IF %)

**Definition:**  
The percentage of orders delivered with the complete requested quantity.

**Rule:**  
An order is considered in-full only if **all order lines** are delivered in full.

**Purpose:**  
Evaluates delivery completeness.

---

## On-Time In-Full Percentage (OTIF %)

**Definition:**  
The percentage of orders delivered both on time and in full.

**Rule:**  
An order is considered OTIF only if **all order lines** are delivered:
- On time
- In full

**Purpose:**  
Represents overall delivery reliability from the customer perspective.

---

## KPI Usage in This Project

These KPIs are used to:
- Assess supply chain performance
- Identify fulfillment gaps
- Compare customer-level and geographic performance
- Support data-driven decision-making
