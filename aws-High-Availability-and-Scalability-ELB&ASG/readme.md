# AWS Solutions Architect Associate – High Availability & Scalability

## Overview

This project demonstrates how to build a highly available and scalable web application on AWS using Elastic Load Balancing and Auto Scaling.

The architecture distributes incoming traffic across multiple EC2 instances and automatically adjusts capacity based on application demand.

---

## AWS Services Used

- Amazon EC2
- Application Load Balancer (ALB)
- Target Groups
- Launch Templates
- Auto Scaling Groups (ASG)
- Amazon CloudWatch
- Security Groups

---

# Architecture

```
                Internet
                    │
                    ▼
        Application Load Balancer
                    │
            Target Group (HTTP)
             ┌───────────────┐
             │               │
             ▼               ▼
        EC2 Instance     EC2 Instance
             ▲               ▲
             └──────┬────────┘
                    │
          Auto Scaling Group
                    │
            Launch Template
```

📷 Architecture Diagram

- architecture-overview.png

---

# Part 1 – Application Load Balancer

## Create Target Group

A Target Group was created to register EC2 instances and perform health checks before routing traffic.

📷 Screenshot

- **01-target-group-created.png**

---

## Create Application Load Balancer

Configured an internet-facing Application Load Balancer.

Configuration:

- Internet-facing
- IPv4
- HTTP Listener (Port 80)
- Associated with Target Group

📷 Screenshot

- **02-alb-created.png**

---

## Register EC2 Instances

Both EC2 instances were successfully registered.

Health status changed to **Healthy** after passing health checks.

📷 Screenshot

- **03-healthy-targets.png**

---

## Test Load Balancing

Traffic was successfully distributed across multiple EC2 instances.

Refreshing the webpage returned responses from different backend servers, confirming that the Application Load Balancer was distributing requests correctly.

📷 Screenshot

- **04-alb-working.png**

---

## Test Path-Based Routing

Configured and verified a path-based routing rule.

Requests sent to **/error** were successfully forwarded according to the configured listener rule.

📷 Screenshot

- **05-path-based-routing.png**

---

# Part 2 – Auto Scaling Group

## Create Launch Template

Created a Launch Template containing:

- Amazon Linux AMI
- Instance Type
- Security Group
- Key Pair
- User Data

The Launch Template is used by the Auto Scaling Group to automatically launch identical EC2 instances.

📷 Screenshot

`06-launch-template.png`

---

## Create Auto Scaling Group

Created an Auto Scaling Group.

**Configuration**

- Minimum Capacity: 2
- Desired Capacity: 2
- Maximum Capacity: 4

The Auto Scaling Group was attached to the existing Application Load Balancer.

📷 Screenshot

`07-auto-scaling-group.png`

---

# Part 3 – Dynamic Scaling Policies

Configured Dynamic Scaling Policies using Amazon CloudWatch metrics.

### Scale Out

- CPU Utilization > 70%

### Scale In

- CPU Utilization < 30%

📷 Screenshot

`08-scaling-policy.png`

---

## Test Scale Out

Generated CPU load to trigger a Scale Out event.

The Auto Scaling Group automatically launched an additional EC2 instance.

📷 Screenshot

`09-scale-out.png`

---

## Test Scale In

After CPU utilization returned to normal, the Auto Scaling Group automatically terminated the additional EC2 instance.

📷 Screenshot

`10-scale-in.png`
