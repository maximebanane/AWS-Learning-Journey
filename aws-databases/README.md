
# AWS Databases – Choosing the Right Database

This chapter provides an overview of the main database services available on AWS and explains how to choose the appropriate database depending on the workload.

Unlike other AWS topics in this repository, this section is mainly theoretical and does not include hands-on labs.

---

## 🗄️ Amazon RDS

**Amazon Relational Database Service (RDS)** is a managed relational database service.

Supported engines include:

* PostgreSQL
* MySQL
* MariaDB
* Oracle
* Microsoft SQL Server
* IBM Db2

### Key Features

* Managed backups
* Automated patching
* Multi-AZ deployments for high availability
* Read Replicas for read scalability
* Encryption
* Vertical and horizontal scaling options

### Typical Use Cases

* Traditional applications
* E-commerce platforms
* ERP and CRM systems
* Applications requiring SQL and relational data

> **Choose RDS when you need a traditional relational SQL database.**

---

## 🚀 Amazon Aurora

**Amazon Aurora** is an AWS-designed relational database compatible with **MySQL and PostgreSQL**.

### Key Features

* Fully managed
* High availability
* Automatic storage scaling
* Up to 15 Read Replicas
* Multi-AZ architecture
* Aurora Serverless available
* Global Database for multi-region workloads

### Typical Use Cases

* High-performance applications
* SaaS platforms
* Large relational workloads
* Applications requiring high availability

> **Choose Aurora when you need a highly available and scalable relational database optimized for AWS.**

---

## ⚡ Amazon ElastiCache

**Amazon ElastiCache** provides an in-memory caching layer.

It supports:

* Redis / Valkey
* Memcached

### Purpose

Instead of repeatedly querying a database:

```text
Application
     ↓
ElastiCache
     ↓
Database
```

Frequently requested data can be served directly from memory.

### Typical Use Cases

* Database caching
* Session storage
* Gaming leaderboards
* Frequently accessed data
* Reducing database load

> **Choose ElastiCache when extremely fast, in-memory access is required.**

---

## ⚡ Amazon DynamoDB

**Amazon DynamoDB** is a fully managed serverless NoSQL database.

### Key Features

* Key-value and document database
* Very low latency
* Automatic scaling
* Serverless
* Multi-region with Global Tables
* DynamoDB Streams
* TTL
* Point-in-Time Recovery
* DAX caching

### Typical Use Cases

* Serverless applications
* Gaming
* Shopping carts
* User sessions
* IoT
* Applications requiring massive scale

> **Choose DynamoDB when you need a highly scalable, low-latency NoSQL database.**

---

## 🪣 Amazon S3

Although **Amazon S3 is object storage rather than a traditional database**, it can store massive datasets and is commonly used as a data lake.

### Typical Use Cases

* Data lakes
* Logs
* Analytics datasets
* Backups
* JSON / CSV / Parquet files
* Machine learning datasets

S3 data can be queried using services such as **Amazon Athena**.

> **Choose S3 when you need inexpensive, massively scalable object storage or a data lake.**

---

## 📄 Amazon DocumentDB

**Amazon DocumentDB** is AWS's managed document database designed for MongoDB-compatible workloads.

Data is stored as JSON-like documents.

### Typical Use Cases

* Content management
* User profiles
* Catalogs
* Document-oriented applications

> **Choose DocumentDB when your application needs a managed document database with MongoDB compatibility.**

---

## 🕸️ Amazon Neptune

**Amazon Neptune** is AWS's managed graph database.

Instead of traditional tables, graph databases focus on relationships:

```text
User A ──friend──> User B
   │
   └──likes──> Product X
```

### Typical Use Cases

* Social networks
* Recommendation engines
* Fraud detection
* Knowledge graphs
* Relationship analysis

> **Choose Neptune when relationships between data are central to the application.**

---

## 📚 Amazon Keyspaces

**Amazon Keyspaces (for Apache Cassandra)** is a managed, serverless Cassandra-compatible database.

### Key Features

* Cassandra Query Language (CQL)
* Serverless
* Highly scalable
* Managed by AWS

### Typical Use Cases

* Cassandra workloads
* Large distributed applications
* High-volume applications

> **Choose Keyspaces when you need Cassandra compatibility without managing Cassandra clusters yourself.**

---

## 📜 Amazon QLDB

**Amazon Quantum Ledger Database (QLDB)** was designed as an immutable ledger database providing a cryptographically verifiable history of changes.

Typical historical use cases included:

* Financial transactions
* Audit trails
* Supply chains
* Systems requiring immutable transaction history

> **Important:** Amazon QLDB has been discontinued by AWS and reached end of support on **July 31, 2025**. It should therefore be treated as legacy knowledge rather than a service to choose for a new architecture.

---

## ⏱️ Amazon Timestream

**Amazon Timestream** is designed for **time-series data**.

Examples:

```text
12:00 → CPU 42%
12:01 → CPU 47%
12:02 → CPU 51%
```

### Typical Use Cases

* IoT sensors
* Application metrics
* Infrastructure monitoring
* Industrial telemetry
* Time-based analytics

> **Choose Timestream when your data consists primarily of measurements or events associated with timestamps.**

---

# 🧠 Choosing the Right AWS Database

| Requirement                    | AWS Service                    |
| ------------------------------ | ------------------------------ |
| Traditional relational SQL     | **RDS**                        |
| High-performance relational DB | **Aurora**                     |
| In-memory caching              | **ElastiCache**                |
| Serverless NoSQL / Key-Value   | **DynamoDB**                   |
| Data lake / Object storage     | **S3**                         |
| Document / MongoDB workloads   | **DocumentDB**                 |
| Graph relationships            | **Neptune**                    |
| Cassandra workloads            | **Keyspaces**                  |
| Immutable ledger               | **QLDB (legacy/discontinued)** |
| Time-series data               | **Timestream**                 |

---

## 🎯 Architecture Examples

### Traditional Web Application

```text
Users
  ↓
Application
  ↓
RDS / Aurora
```

### High-Traffic Application with Cache

```text
Users
  ↓
Application
  ↓
ElastiCache
  ↓
RDS / Aurora
```

### Serverless Application

```text
API Gateway
     ↓
   Lambda
     ↓
 DynamoDB
```

### Data Lake

```text
Applications / Logs
        ↓
       S3
        ↓
     Athena
```

---

## 📌 SAA Exam Quick Reference

For the AWS Solutions Architect Associate exam, the most important skill is recognizing the **type of workload**.

```text
SQL?              → RDS / Aurora
NoSQL?            → DynamoDB
Cache?            → ElastiCache
Documents?        → DocumentDB
Relationships?    → Neptune
Cassandra?        → Keyspaces
Time-series?      → Timestream
Data lake?        → S3
```

The goal is not simply to know what each service does, but to identify **which database best matches a given architecture and workload**.

---

## 📚 Skills Covered

* AWS database selection
* Relational vs NoSQL databases
* Database scalability
* High availability
* In-memory caching
* Document databases
* Graph databases
* Time-series databases
* Serverless database architectures
