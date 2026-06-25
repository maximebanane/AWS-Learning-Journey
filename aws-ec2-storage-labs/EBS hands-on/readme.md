# Amazon EBS Hands-On Lab

## Overview

This lab demonstrates how to create and attach an Amazon Elastic Block Store (EBS) volume to an existing EC2 instance.

## AWS Services

- Amazon EC2
- Amazon EBS

---

# Objectives

- Create an EBS Volume
- Attach the volume to an EC2 instance
- Verify the attachment
- Remove the volume

---

# Step 1 - Create an EBS Volume

Created a new **General Purpose SSD (gp3)** EBS volume in the same Availability Zone as the EC2 instance.

📷 Screenshot

```
screenshots/01-create-ebs-volume.png
```

---

# Step 2 - Attach the Volume

Attached the new EBS volume to the running EC2 instance.

📷 Screenshot

```
screenshots/02-attach-volume.png
```

---

# Step 3 - Verify the Attachment

Verified that the EBS volume is successfully attached to the EC2 instance.

📷 Screenshot

```
screenshots/03-volume-attached.png
```

---

# Step 4 - Delete the Volume

Detached and deleted the EBS volume.

📷 Screenshot

```
screenshots/04-delete-volume.png
```

---

# What I Learned

- Difference between the root volume and additional EBS volumes
- EBS volumes are AZ-specific
- Additional storage can be attached without recreating the instance
- EBS volumes provide persistent block storage

---

# Real-World Applications

- Database storage
- Application servers
- Persistent storage
- Enterprise workloads
