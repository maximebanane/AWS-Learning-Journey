# AWS EC2 Fundamentals Lab ☁️

## Overview

This project demonstrates the deployment and configuration of an Amazon EC2 instance as part of my AWS learning journey.  
It focuses on compute provisioning, security configuration, and basic cloud deployment.

---

## Objectives

- Launch and configure an EC2 instance
- Understand key pair authentication (SSH access)
- Configure security groups
- Deploy a basic web server using User Data
- Attach IAM roles to EC2 instances
- Monitor cloud costs using AWS Budgets

---

## Steps Completed

### 1. AWS Budget Configuration
Created an AWS Budget to monitor cloud spending and set up alerts to avoid unexpected charges.

📸 `01-aws-budget-created.png`

---

### 2. EC2 Instance Running
Launched an EC2 instance and verified that it is successfully running in AWS.

📸 `02-ec2-instance-running.png`

---

### 3. Security Group Configuration
Configured inbound rules to allow SSH (22) and HTTP (80) traffic to the instance.

📸 `03-security-group-inbound-rules.png`

---

### 4. Key Pair Creation
Created a key pair used for secure SSH authentication to the EC2 instance.

📸 `04-ec2-key-pair-created.png`

---

### 5. EC2 Connection
Connected to the instance using SSH / EC2 Instance Connect.

### Key Pair

The EC2 instance was launched using an SSH key pair (`ec2-key`) generated at the time of instance creation.  
This key is required to securely access the instance via SSH.


📸 `05-ec2-connection-success.png`

---

### 6. Web Server Deployment (User Data)
Used EC2 User Data to automatically install and run a web server at instance launch.

📸 `06-ec2-web-server-running.png`

---

### 7. IAM Role Attachment
Attached an IAM role to the EC2 instance to securely access AWS services without long-term credentials.

📸 `07-ec2-iam-role-attached.png`

---

## Key Learnings

- AWS Budgets help monitor and control cloud spending
- EC2 provides scalable virtual compute in AWS
- Security Groups act as virtual firewalls for instances
- Key pairs enable secure SSH authentication
- User Data allows automation of instance setup
- IAM roles are preferred over access keys for AWS services
- Principle of least privilege is a core AWS security best practice

---

## Security Best Practices Applied

- Monitored costs using AWS Budgets
- Restricted network access using Security Groups
- Used SSH key-based authentication instead of passwords
- Used IAM roles instead of hardcoded credentials
- Avoided using root account for operations

---

## Status

✔ AWS Budget configured  
✔ EC2 instance launched and running  
🚧 EC2 Fundamentals Lab in progress (AWS SAA journey)

---


## Next Steps

- Deep dive into Security Groups rules
- Deploy full web application on EC2
- Explore Load Balancer integration
- Continue with S3 Static Website Lab
- Continue VPC Networking Lab
