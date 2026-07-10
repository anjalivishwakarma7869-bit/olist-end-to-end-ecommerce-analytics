
# Olist End-to-End E-Commerce & Marketing Analytics

An end-to-end analytics project built on the **Olist Brazilian E-Commerce** and **Marketing Funnel** datasets, covering the complete workflow from **raw data ingestion → analytical modeling → SQL insights → Power BI dashboards**.

This project demonstrates how real-world analytics teams design data models, validate data, derive business insights, and communicate results through interactive dashboards.

---

# Business Context & Objectives

Olist is a Brazilian e-commerce platform connecting sellers and customers across multiple product categories.

The objective of this project is to analyze:

- Overall e-commerce performance
- Customer behavior
- Seller performance
- Product & category trends
- Order fulfillment and delivery performance
- Marketing funnel effectiveness (MQL → Closed Seller)
- Revenue quality of acquired sellers

The project is structured to reflect how analytics is performed in production environments.

---

# Dataset Overview

This project uses publicly available datasets from Kaggle, spanning two analytical domains:

- Transactional E-Commerce Data
- CRM-Style Marketing Funnel Data

Detailed dataset descriptions and source links are documented in:

📂 `02_data_sources/`

## Domains Covered

### E-Commerce Transactions

- Customers
- Orders
- Sellers
- Products
- Product Categories
- Payments
- Reviews

### Marketing Funnel

- Marketing Qualified Leads (MQLs)
- Closed Deals (Seller Acquisition Outcomes)

The dataset intentionally combines transactional e-commerce data with CRM-style marketing funnel data, enabling both operational analytics and growth-focused funnel analysis.

---

# Project Architecture

The repository follows a real-world analytics workflow.

```text
01_project_overview/
│── Business context, objectives, and project scope

02_data_sources/
│── Dataset documentation and data lineage

03_ddl_table_creation/
│── Database schema and table creation scripts

04_dml_data_load/
│── Data ingestion and transformation scripts

05_data_validation/
│── Data quality checks and integrity validation

06_star_schema/
│── Analytical data models
│   ├── ecommerce/
│   └── marketing/

07_analytical_insights/
│── SQL business analysis and insights

08_power_bi_dashboard/
│── Power BI dashboards (.pbix)
│── Dashboard screenshots
```

Each folder represents one stage of the analytics lifecycle—from raw data to business insights.

---

# Data Modeling Strategy

## 1. E-Commerce Analytics — Star Schema

Transactional e-commerce data is modeled using a **Star Schema** to support fast analytical queries and BI reporting.

### Fact Table

- `Fact_Order_Items`

### Dimension Tables

- Customers
- Products
- Sellers
- Orders
- Payments
- Reviews
- Geolocation
- Category Translation

### Supports Analysis Of

- Revenue & GMV
- Delivery performance
- Product performance
- Seller performance
- Customer purchasing behavior

Documentation:

```
06_star_schema/ecommerce/ecommerce_star_schema.md
```

---

## 2. Marketing Funnel Analytics — Event-Based Funnel Model

Marketing data is intentionally **not modeled using a Star Schema**.

Instead, it follows an **Event-Based Funnel Model**, which better represents CRM and growth analytics workflows.

### Core Tables

- `marketing_qualified_leads`
- `marketing_closed_deals`

These tables are connected using:

```
mql_id
```

### Supports Analysis Of

- Funnel drop-off
- Conversion rates
- Lead origin effectiveness
- Seller acquisition quality
- Revenue quality

Documentation:

```
06_star_schema/marketing/marketing_data_model.md
```

> Knowing **when not to use a Star Schema** is just as important as knowing how to design one.

---

# SQL Analytical Insights

Business insights are generated using SQL queries written on top of the analytical models.

Key business questions answered include:

- How many MQLs convert into sellers?
- Which lead origins convert most effectively?
- Which acquisition channels bring higher-value sellers?
- How does seller quality vary by business type?
- What are the revenue and fulfillment characteristics of acquired sellers?

SQL scripts:

```
07_analytical_insights/
```

---

# Power BI Dashboards

Interactive dashboards were built in **Power BI Desktop** using validated analytical tables and DAX measures.

Power BI files (`.pbix`) are documented inside:

```
08_power_bi_dashboard/
```

---

## 1. E-Commerce Performance Dashboard

A **5-page interactive dashboard** covering:

- Executive Summary
- Customer Analytics
- Order Analytics
- Seller Analytics
- Product & Category Analytics

Built on the analytical Star Schema model.

### Dashboard Preview

```markdown
![E-Commerce Dashboard - Summary](08_power_bi_dashboard/screenshots/ecommerce/Summary.png)
```

---

## 2. Marketing Funnel Dashboard

Features include:

- MQL → Closed Deal Funnel
- Conversion Rate Analysis
- Lead Origin Performance
- Seller Acquisition Quality
- Revenue Quality Analysis

### Dashboard Preview

```markdown
![Marketing Funnel Dashboard](08_power_bi_dashboard/screenshots/marketing/Marketing_Funnel.png)
```

---

# Tools & Skills Demonstrated

- PostgreSQL
- SQL
- Data Modeling
- Star Schema Design
- Funnel Modeling
- Data Validation
- Data Quality Checks
- Power BI Desktop
- DAX
- Business Intelligence
- Dashboard Design
- Analytical Problem Solving

---

# Key Takeaways

This project demonstrates:

- End-to-end ownership of an analytics workflow
- Real-world data modeling practices
- Business-oriented SQL analysis
- Data validation and quality assurance
- Interactive Power BI dashboard development
- Ability to transform raw data into actionable business insights

---

# Repository Structure

```text
Olist-End-to-End-Ecommerce-Marketing-Analytics
│
├── 01_project_overview
├── 02_data_sources
├── 03_ddl_table_creation
├── 04_dml_data_load
├── 05_data_validation
├── 06_star_schema
│   ├── ecommerce
│   └── marketing
├── 07_analytical_insights
├── 08_power_bi_dashboard
└── README.md
```

---

# Final Note

This project intentionally combines **technical rigor**, **business interpretation**, and **analytics engineering best practices**.

Rather than simply presenting dashboards, it demonstrates the complete analytics lifecycle—from data ingestion and validation to modeling, SQL-based business analysis, and executive-level reporting—mirroring how modern analytics teams operate in production environments