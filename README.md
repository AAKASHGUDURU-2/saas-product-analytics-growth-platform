# saas-product-analytics-growth-platform
Built an end-to-end SaaS Product Analytics &amp; Growth Intelligence Platform using Kafka, Snowflake, dbt, SQL, Python, and Tableau to analyze user behavior, retention, and revenue growth.

User Actions (TaskFlow App)
        │
        ▼
Data Ingestion
(API + Kafka streaming)
        │
        ▼
Data Lake
(AWS S3)
        │
        ▼
Data Processing
(Python / Spark / Databricks)
        │
        ▼
Data Warehouse
(Snowflake / BigQuery)
        │
        ▼
Transformations
(db t)
        │
        ▼
Analytics
(SQL + Python)
        │
        ▼
Machine Learning
(Churn prediction)
        │
        ▼
Dashboards
(Tableau / Power BI)

Phase 1 - Event Tracking Plan (Final)

Our tracking plan:

Event	Purpose
signup	user acquisition
login	engagement
create_project	activation
create_task	product usage
complete_task	productivity
invite_user	collaboration
upload_file	engagement
upgrade_plan	revenue
cancel_subscription	churn

