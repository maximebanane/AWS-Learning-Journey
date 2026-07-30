# Amazon S3 (Simple Storage Service)

Amazon S3 is a highly scalable, durable, secure and fully managed object storage service.

---

# Introduction

## 1. S3 Overview

### Topics

- Buckets
- Objects
- Keys
- Prefixes
- Regions
- Durability
- Availability

---

## 2. S3 Hands-On

### Screenshots

- `screenshots/intro/01-create-bucket.png`
- `screenshots/intro/02-upload-object.png`

### What was done

- Created a bucket
- Uploaded objects
- Deleted objects
- Navigated through the console

---

## 3. Bucket Policies

### Screenshot

`screenshots/intro/03-bucket-policy.png`

### Topics

- Resource-based policies
- JSON policy
- Principal
- Action
- Resource
- Effect

---

## 4. Static Website Hosting

### Screenshot

`screenshots/intro/04-static-website.png`

### Topics

- Static website hosting
- Index document
- Error document
- Public access

---

## 5. Versioning

### Screenshot

`screenshots/intro/05-versioning.png`

### Topics

- Enable Versioning
- Object versions
- Delete markers
- Rollback

---

## 6. Replication

### Screenshot

`screenshots/intro/06-replication.png`

### Topics

- SRR
- CRR
- IAM Role
- Versioning requirement

---

## 7. Storage Classes

### Screenshot

`screenshots/intro/07-storage-classes.png`

### Topics

- Standard
- Intelligent-Tiering
- Standard-IA
- One Zone-IA
- Glacier Instant Retrieval
- Glacier Flexible Retrieval
- Glacier Deep Archive
- Express One Zone

---

# Advanced

## 8. Lifecycle Rules

### Screenshots

- `screenshots/advanced/01-lifecycle-rule.png`
- `screenshots/advanced/02-lifecycle-created.png`

### Topics

- Transition
- Expiration
- Lifecycle Analytics

---

## 9. Requester Pays

### Screenshot

`screenshots/advanced/03-requester-pays.png`

### Topics

- Bucket owner
- Request charges
- Download costs

---

## 10. Event Notifications

### Screenshots

- `screenshots/advanced/04-event-notification.png`
- `screenshots/advanced/05-event-trigger.png`

### Topics

- Lambda
- SNS
- SQS

---

## 11. Performance

### Screenshot

`screenshots/advanced/06-performance.png`

### Topics

- Multipart Upload
- Prefixes
- Transfer Acceleration
- Byte-Range Fetches

---

## 12. S3 Select & Glacier Select

### Screenshot

`screenshots/advanced/07-s3-select.png`

### Topics

- SQL Queries
- Retrieve partial data
- Reduce transfer costs

---

## 13. Batch Operations

### Screenshot

`screenshots/advanced/08-batch-operations.png`

### Topics

- Copy
- Delete
- Restore
- Invoke Lambda
- Tagging
