# Amazon EBS Snapshot Hands-On Lab

## Overview

This lab demonstrates how to create and restore an Amazon EBS Snapshot.

## AWS Services

- Amazon EBS
- Amazon EC2

---

# Objectives

- Create a Snapshot
- Restore a Volume
- Attach the restored Volume

---

# Step 1 - Create a Snapshot

Created an EBS Snapshot from an existing volume.

📷 Screenshot

```
screenshots/01-create-snapshot.png
```

---

# Step 2 - Snapshot Completed

Verified that the snapshot state is **Completed**.

📷 Screenshot

```
screenshots/02-snapshot-completed.png
```

---

# Step 3 - Create Volume from Snapshot

Created a new EBS volume using the snapshot.

📷 Screenshot

```
screenshots/03-create-volume-from-snapshot.png
```

---

# Step 4 - Attach the Restored Volume

Attached the restored volume to the EC2 instance.

📷 Screenshot

```
screenshots/04-attach-restored-volume.png
```

---

# What I Learned

- Snapshots are incremental backups
- Snapshots are stored in Amazon S3 (managed by AWS)
- Volumes can be recreated at any time from a snapshot
- Snapshots are commonly used for backup and disaster recovery

---

# Real-World Applications

- Disaster Recovery
- Backup Strategy
- Migration
- Data Protection
