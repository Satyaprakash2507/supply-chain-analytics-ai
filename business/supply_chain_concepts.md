# Supply Chain Concepts

This document outlines the core **supply chain concepts** used in this project.  
These concepts form the foundation for defining performance metrics and interpreting analytical results.

---

## Orders

An **Order** represents a unique request placed by a customer on a specific date.

Key characteristics:
- Identified by a unique order ID
- May contain one or more items
- Evaluated at the order level for delivery performance metrics

---

## Order Lines

An **Order Line** represents an individual item within an order.

Key characteristics:
- Each order can contain multiple order lines
- Order lines capture item-level quantities and fulfillment status
- Used to calculate line-level fulfillment metrics

**Example:**
If a customer places an order for two different products, the order contains two order lines.

---

## Order Quantity

Order quantity represents the number of units requested for a specific order line.  
This attribute is used to evaluate volume-based fulfillment performance.

---

## Delivery Dates

Delivery-related dates are used to assess delivery performance:
- Order placement date
- Committed delivery date
- Actual delivery date

These dates are critical for determining whether an order meets on-time delivery criteria.

---

## Fulfillment Status

Fulfillment status indicates whether an order line was:
- Delivered
- Delivered in full
- Delivered on time

Fulfillment outcomes at the order line level are aggregated to evaluate order-level performance.

---

## Supply Chain Performance Measurement

Supply chain performance is measured across two primary dimensions:
1. **Timeliness** – whether deliveries meet agreed timelines
2. **Completeness** – whether requested quantities are fulfilled

These dimensions are combined to evaluate overall delivery reliability.
