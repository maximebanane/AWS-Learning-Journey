# AWS Data & Analytics

This project documents my hands-on exploration of AWS data and analytics services as part of my AWS Solutions Architect learning path.

The goal is to understand how AWS services can be combined to **store, catalog, query, process, analyze, and visualize large datasets**.

---

## Architecture Overview

A common serverless analytics architecture on AWS can look like:

```text
Data Sources
     │
     ▼
Amazon S3
     │
     ├──────────────► AWS Glue
     │                 │
     │                 ▼
     │            Glue Data Catalog
     │                 │
     ▼                 ▼
Amazon Athena ◄────────┘
     │
     ▼
Amazon QuickSight
```

This architecture allows data stored in Amazon S3 to be cataloged with AWS Glue, queried using SQL with Amazon Athena, and visualized using Amazon QuickSight.

---

# Amazon Athena

Amazon Athena is a **serverless interactive query service** that makes it possible to analyze data directly in Amazon S3 using standard SQL.

## Key Concepts

* Serverless: no infrastructure to manage
* Queries data directly from Amazon S3
* Uses standard SQL
* Integrates with the AWS Glue Data Catalog
* Supports formats such as CSV, JSON, Parquet, and ORC
* Pricing is primarily based on the amount of data scanned

## Athena Performance Optimization

Athena performance and cost can be improved by reducing the amount of data that needs to be scanned.

### Columnar Formats

Formats such as **Apache Parquet** and **ORC** store data by column rather than by row.

This allows Athena to scan only the columns required by a query instead of reading the entire dataset.

AWS Glue can be used to convert datasets into Parquet or ORC.

### Compression

Compressing datasets reduces their size and therefore the amount of data that Athena needs to process.

Common compression formats include:

* gzip
* Snappy
* LZ4
* Zstandard

### Partitioning

Datasets stored in S3 can also be partitioned.

For example:

```text
s3://analytics-data/
    year=2026/
        month=01/
        month=02/
        month=03/
```

A query targeting February 2026 can scan only:

```text
/year=2026/month=02/
```

instead of scanning the entire dataset.

This can significantly improve query performance and reduce cost.

## Hands-On

In this lab, I used Athena to query data stored in an S3 bucket.

Example:

```sql
SELECT *
FROM my_database.my_table
LIMIT 10;
```

The objective was to understand the relationship between:

```text
Amazon S3
    │
    ▼
Glue Data Catalog
    │
    ▼
Amazon Athena
    │
    ▼
SQL Query Results
```


# AWS Glue

AWS Glue is a **serverless data integration and ETL service**.

It can discover, prepare, transform, and catalog data for analytics workloads.

## Important Components

### Glue Crawler

A Glue Crawler can automatically scan a data source and determine its schema.

```text
Amazon S3
    │
    ▼
Glue Crawler
    │
    ▼
Glue Data Catalog
    │
    ▼
Amazon Athena
```

### Glue Data Catalog

The Glue Data Catalog is a centralized metadata repository containing information about datasets, including:

* databases
* tables
* schemas
* partitions
* data locations

Athena can use this metadata to query data stored in S3.



---

# Amazon Redshift

Amazon Redshift is AWS's managed **cloud data warehouse**.

It is designed for large-scale analytical workloads and complex SQL queries.

## Redshift vs Athena

| Amazon Athena               | Amazon Redshift                           |
| --------------------------- | ----------------------------------------- |
| Serverless query service    | Cloud data warehouse                      |
| Queries data directly in S3 | Data stored and managed for analytics     |
| Pay per data scanned        | Provisioned or serverless capacity        |
| Great for ad-hoc queries    | Great for repeated analytics workloads    |
| Minimal administration      | More advanced data warehouse capabilities |

Redshift Spectrum can also query data stored directly in Amazon S3.



---

# Amazon OpenSearch Service

Amazon OpenSearch Service is used for **search, log analytics, observability, and near-real-time data analysis**.

Typical use cases include:

* application log analysis
* full-text search
* monitoring
* security analytics
* dashboards

Example:

```text
Application Logs
      │
      ▼
Amazon OpenSearch
      │
      ▼
OpenSearch Dashboards


---

# Amazon EMR

Amazon EMR is a managed big-data platform for running frameworks such as:

* Apache Spark
* Apache Hadoop
* Apache Hive
* Apache HBase

It is designed for large-scale distributed data processing.

Example:

```text
Large Dataset
     │
     ▼
Amazon S3
     │
     ▼
Amazon EMR / Spark
     │
     ▼
Processed Data
```


---

# Amazon QuickSight

Amazon QuickSight is AWS's **business intelligence and visualization service**.

It can create:

* dashboards
* charts
* reports
* interactive analytics

A typical architecture is:

```text
Amazon S3
     │
     ▼
Amazon Athena
     │
     ▼
Amazon QuickSight
     │
     ▼
Dashboard
```

QuickSight can also connect to services such as Redshift and RDS.



---

# AWS Lake Formation

AWS Lake Formation simplifies the creation and management of **data lakes on AWS**.

It provides centralized mechanisms for:

* data access
* permissions
* governance
* data discovery

It commonly works with:

```text
Amazon S3
AWS Glue
Amazon Athena
Amazon Redshift
```



---

# Amazon Managed Service for Apache Flink

Amazon Managed Service for Apache Flink can process and analyze **streaming data in real time**.

It can consume streams coming from services such as Amazon Kinesis Data Streams.

Example:

```text
Applications / Devices
          │
          ▼
Kinesis Data Streams
          │
          ▼
Managed Service for Apache Flink
          │
          ▼
Real-Time Analytics
```



---

# Amazon MSK

Amazon Managed Streaming for Apache Kafka (Amazon MSK) provides managed **Apache Kafka clusters** on AWS.

AWS manages much of the underlying infrastructure, including:

* cluster provisioning
* broker availability
* infrastructure maintenance
* integration with AWS networking and security

Typical architecture:

```text
Producers
    │
    ▼
Amazon MSK
    │
    ▼
Consumers
```



---

# Big Data Ingestion Pipeline

AWS services can be combined to build scalable ingestion and analytics pipelines.

Example:

```text
Applications
     │
     ▼
Kinesis Data Streams
     │
     ├──────────────► AWS Lambda
     │
     └──────────────► Data Firehose
                            │
                            ▼
                        Amazon S3
                            │
                            ▼
                        AWS Glue
                            │
                            ▼
                     Amazon Athena
                            │
                            ▼
                    Amazon QuickSight
```

This architecture separates **data ingestion, storage, cataloging, analytics, and visualization**.



---

# Key Takeaways

This module helped me understand the role of the main AWS analytics services:

| Service                          | Main Purpose                 |
| -------------------------------- | ---------------------------- |
| Amazon Athena                    | Serverless SQL queries on S3 |
| AWS Glue                         | ETL and Data Catalog         |
| Amazon Redshift                  | Data warehousing             |
| Amazon OpenSearch Service        | Search and log analytics     |
| Amazon EMR                       | Big-data processing          |
| Amazon QuickSight                | Business intelligence        |
| AWS Lake Formation               | Data lake governance         |
| Managed Service for Apache Flink | Real-time stream processing  |
| Amazon MSK                       | Managed Apache Kafka         |
| Amazon S3                        | Data lake / object storage   |

The most important architectural distinction is choosing the appropriate service depending on whether the workload requires **ad-hoc SQL queries, data warehousing, distributed processing, search, streaming, or visualization**.

For Athena specifically:

```text
Parquet / ORC
      +
Compression
      +
S3 Partitioning
      │
      ▼
Less Data Scanned
      │
      ├──► Lower Cost
      │
      └──► Better Performance
```

---

# Skills Demonstrated

* AWS analytics architecture
* Amazon S3 data storage
* Serverless SQL with Amazon Athena
* AWS Glue Data Catalog
* Data lake concepts
* Columnar data formats
* S3 dataset partitioning
* Athena query optimization
* Streaming architectures
* Selection of AWS analytics services
* AWS Solutions Architect design principles

---


```

---

# Next Steps

* Build an S3 + Glue + Athena analytics workflow
* Optimize Athena queries using Parquet and partitioning
* Explore real-time ingestion with Kinesis
* Build a visualization layer with QuickSight
* Apply IAM least-privilege permissions to analytics workloads
