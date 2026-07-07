# AWS Lab – Amazon RDS, Amazon Aurora & Amazon ElastiCache

## Overview

This lab introduces three managed database services available on AWS:

* **Amazon RDS** – Managed relational database service.
* **Amazon Aurora** – High-performance cloud-native relational database.
* **Amazon ElastiCache** – Fully managed in-memory caching service.

The goal is to understand when to use each service and how ElastiCache improves application performance.

---

# Amazon RDS

## What is Amazon RDS?

Amazon Relational Database Service (RDS) is a fully managed service that simplifies the deployment, operation, and scaling of relational databases in AWS.

AWS manages:

* Hardware provisioning
* Operating system maintenance
* Automated backups
* Software patching
* Monitoring
* High availability (Multi-AZ)

Supported database engines include:

* MySQL
* PostgreSQL
* MariaDB
* Oracle
* Microsoft SQL Server
* Amazon Aurora

### Common Features

* Automated Backups
* Read Replicas
* Multi-AZ Deployments
* Encryption at Rest
* Encryption in Transit
* Performance Insights

---

# Amazon Aurora

## What is Aurora?

Amazon Aurora is AWS's cloud-native relational database engine compatible with MySQL and PostgreSQL.

Unlike standard RDS engines, Aurora uses a distributed storage architecture replicated across multiple Availability Zones.

### Advantages

* Up to 5x faster than MySQL
* Up to 3x faster than PostgreSQL
* Automatic storage scaling
* Six copies of data across three Availability Zones
* Faster failover
* Shared cluster storage

### Aurora Architecture

```text
                Writer
                  |
        -----------------------
        |         |          |
    Reader 1  Reader 2  Reader 3
                  |
        Shared Distributed Storage
        (6 copies across 3 AZs)
```

---

# Amazon ElastiCache

## What is Amazon ElastiCache?

Amazon ElastiCache is a fully managed in-memory caching service.

Instead of querying a database every time, frequently accessed data is stored in RAM, significantly reducing response times.

### Supported Engines

### Redis

* Persistence
* Replication
* High Availability
* Advanced data structures

### Memcached

* Simple distributed cache
* No persistence
* No replication
* Lightweight

---

# Cache Workflow

```text
Client
   |
Application
   |
ElastiCache
   |
 Cache Miss
   |
Amazon RDS / Aurora
```

* Cache Hit → Response returned immediately.
* Cache Miss → Data retrieved from the database and stored in cache.

---

# Why Use ElastiCache?

* Lower latency
* Reduce database load
* Improve scalability
* Handle large numbers of read requests
* Better user experience

---

# Lab Objectives

During this lab you will:

* Create an Amazon ElastiCache cluster
* Deploy a Redis cache
* Review cluster configuration
* Identify the cache endpoint
* Explore the AWS console
* Delete all resources

---

# Screenshots

```
01-elasticache-dashboard.png
02-create-redis-oss-cache.png
03-cache-name.png
04-cache-created.png
05-cache-endpoint.png
06-delete-cache.png
```

---

# AWS Certified Solutions Architect (SAA) Notes

## Choose Amazon RDS when:

* You need a traditional relational database.
* You use Oracle or SQL Server.
* Cost is more important than maximum performance.

## Choose Amazon Aurora when:

* You need maximum performance.
* High availability is critical.
* You use MySQL or PostgreSQL.
* Automatic storage scaling is required.

## Choose Amazon ElastiCache when:

* Your application performs many read operations.
* Database latency becomes a bottleneck.
* You want to reduce the load on RDS or Aurora.
* Frequently accessed data can be cached.

---

# Key Takeaways

| Service            | Purpose                                           |
| ------------------ | ------------------------------------------------- |
| Amazon RDS         | Fully managed relational databases                |
| Amazon Aurora      | High-performance cloud-native relational database |
| Amazon ElastiCache | In-memory cache for faster reads                  |

Together, these services form a common AWS architecture where RDS or Aurora stores persistent data, while ElastiCache accelerates read-heavy workloads by serving frequently requested data directly from memory.
