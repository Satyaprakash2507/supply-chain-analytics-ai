# PostgreSQL Setup Using Supabase

This document describes the setup and configuration of a **PostgreSQL database using Supabase**.  
In this project, Supabase is used as a managed PostgreSQL service to store and manage structured supply chain data for analytics and automation workflows.

---

## Overview

Supabase provides a hosted PostgreSQL environment with built-in management features such as table administration, secure access, and connection configuration.  
The database serves as the central data store for downstream analytics and reporting.

---

## Step 1: Create a Supabase Account

1. Open a web browser and navigate to: https://supabase.com
2. Sign in using email or a supported authentication provider.
3. Verify the account if required.
4. Access the Supabase dashboard.

---

## Step 2: Create a New Supabase Project

1. From the dashboard, select **New Project**.
2. Provide the following details:
- Project name
- Strong database password
- Preferred deployment region
3. Submit the project creation request.
4. Wait for the database provisioning to complete.

---

## Step 3: Access the Database Interface

1. Open the created project.
2. Navigate to the **Database** section.
3. Open the **Table Editor** to manage tables and data.

---

## Step 4: Create Tables and Load Data

The following tables are used in this project:

- `fact_order_line`
- `fact_aggregate`
- `dim_customers`
- `dim_products`
- `dim_targets_orders`

### Table Creation and Data Import

For each table:
1. Select **Create new table**.
2. Provide the table name.
3. Use the **Import from CSV** option to load data.
4. Review column mappings and data types.
5. Save the table.

---

## Step 5: Validate and Update Data Types

1. Review all imported columns.
2. Ensure:
- Identifier columns are numeric
- Date fields use appropriate date or timestamp data types
3. Apply schema updates where required.
4. Save the changes.

---

## Step 6: Obtain Database Connection Details

1. Navigate to the **Connect** section of the project.
2. Retrieve the following connection parameters:
- Host
- Port
- Database name
- Username
- Password
3. Use these details to configure external tools such as:
- n8n
- Analytics platforms

---

## Security Considerations

- Database credentials are stored securely within Supabase.
- Credentials are not committed to version control.
- Access to the database is restricted to authorized services and users.

---

## Usage in This Project

In this project, Supabase PostgreSQL is used to:
- Store transactional and dimensional supply chain data
- Serve as the data source for automation workflows
- Support analytical queries and KPI generation

---

## Conclusion

Supabase provides a reliable and managed PostgreSQL environment that supports structured data storage, secure access, and integration with automation and analytics tools.

