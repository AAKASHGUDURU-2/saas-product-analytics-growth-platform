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

1. Generated random data and created a table db. Now converting it to csv file. - Data Generation
2. Creating a database taskflow.db through conn = sqlite3.connect("taskflow.db") and uploading all the data into this db by naming the table events - df.to_sql("events",conn,if_exists="replace",index="False") - Data Ingestion with Python
3. But in real life data usually comes from websites etc. So we use API frameworks. APIs work bw app and server. These r API servers which takes data from apps and send it to database. Here we r using Fast API which creates a local server. After running the Fast API python framework it creates a db and a table and connects it with db and verify where the actions to enter to where in the table. After running the code, run this in the terminal uvicorn api.event_api:app --reload. We get a host link, here http://127.0.0.1:8000/docs, run this in browser. To verify that it is working, clickmon post, try it now and add an action. Here we did
{
  "user_id": "101",
  "event_type": "create_task",
  "timestamp": "2026-03-13T10:20:00",
  "properties": {
    "task_id": "T100"
  }
}. We got output - { "status": "event stored"}. So, its working. This is just to understand the working of API. This is usually a backend part. taskflow.db created, events table created, API storing events
