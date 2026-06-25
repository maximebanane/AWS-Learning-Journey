# Amazon Machine Image (AMI) Hands-On Lab

## Overview

This lab demonstrates how to create a custom Amazon Machine Image (AMI) and launch a new EC2 instance from it.

## AWS Services

- Amazon EC2
- Amazon Machine Images

---

# Objectives

- Create an AMI
- Launch an EC2 instance from the AMI
- Verify the deployment

---

# Step 1 - Create an AMI

Created a custom AMI from an existing EC2 instance.

📷 Screenshot

```
screenshots/01-create-ami.png
```

---

# Step 2 - AMI Available

Verified the AMI status is **Available**.

📷 Screenshot

```
screenshots/02-ami-available.png
```

---

# Step 3 - Launch EC2 from AMI

Launched a new EC2 instance using the custom AMI.

📷 Screenshot

```
screenshots/03-launch-instance.png
```

---

# Step 4 - Verify the Instance

Confirmed that the new EC2 instance started successfully.

📷 Screenshot

```
screenshots/04-running-instance.png
```

---

# What I Learned

- AMIs are reusable EC2 templates
- AMIs include the operating system and configuration
- Custom AMIs simplify infrastructure deployment
- AMIs improve consistency across environments

---

# Real-World Applications

- Auto Scaling
- Disaster Recovery
- Golden Images
- Infrastructure Automation
