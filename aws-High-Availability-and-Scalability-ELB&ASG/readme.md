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
- AWS Certificate Manager (ACM)
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

📷 Screenshot:
- architecture-overview.png

---

# Part 1 – Application Load Balancer

## Create Target Group

A Target Group was created to register EC2 instances and perform health checks before routing traffic.

### Screenshot

- target-group-created.png

---

## Create Application Load Balancer

Configured an internet-facing Application Load Balancer.

Configuration:

- Internet-facing
- IPv4
- HTTP Listener (Port 80)
- Associated with Target Group

### Screenshot

- alb-created.png

---

## Register EC2 Instances

Both EC2 instances were successfully registered.

Health status changed to **Healthy** after passing health checks.

### Screenshot

- healthy-targets.png

---

## Test Load Balancing

Traffic was successfully distributed across multiple EC2 instances.

Refreshing the webpage returned responses from different servers.

### Screenshot

- alb-working.png

---

# Part 2 – HTTPS using ACM

## Request SSL Certificate

An SSL/TLS certificate was requested using AWS Certificate Manager.

### Screenshot

- acm-certificate.png

---

## Configure HTTPS Listener

Added an HTTPS Listener (443) to the Application Load Balancer.

The ACM certificate was attached to enable encrypted traffic.

### Screenshot

- https-listener.png

---

## Test HTTPS

Verified secure access using HTTPS.

### Screenshot

- https-working.png

---

# Part 3 – Launch Template

Created a Launch Template containing:

- Amazon Linux AMI
- Instance Type
- Security Group
- Key Pair
- User Data

The Launch Template is used by the Auto Scaling Group to launch identical EC2 instances automatically.

### Screenshot

- launch-template.png

---

# Part 4 – Auto Scaling Group

Created an Auto Scaling Group.

Configuration:

- Minimum Capacity: 2
- Desired Capacity: 2
- Maximum Capacity: 4

The ASG was attached to the existing Application Load Balancer.

### Screenshot

- auto-scaling-group.png

---

# Part 5 – Scaling Policies

Configured Dynamic Scaling Policies based on CloudWatch metrics.

Example:

- Scale Out:
    - CPU > 70%

- Scale In:
    - CPU < 30%

### Screenshot

- scaling-policy.png

---

# Test Auto Scaling

Generated CPU load to trigger a Scale Out event.

The Auto Scaling Group launched an additional EC2 instance automatically.

### Screenshot

- scale-out.png

After CPU usage decreased, the Auto Scaling Group terminated the extra instance.

### Screenshot

- scale-in.png

---

# Concepts Learned

## High Availability

Deploy applications across multiple Availability Zones to eliminate single points of failure.

## Scalability

Automatically increase or decrease infrastructure according to demand.

## Application Load Balancer

- Layer 7 (HTTP / HTTPS)
- Host-based routing
- Path-based routing
- SSL termination
- Web applications

## Network Load Balancer

- Layer 4 (TCP / UDP)
- Static IP addresses
- Ultra-low latency
- Millions of requests per second

## Gateway Load Balancer

- Layer 3
- Security appliances
- Firewalls
- Intrusion Detection Systems

## Sticky Sessions

Allows users to continue interacting with the same EC2 instance during a session.

## Cross Zone Load Balancing

Evenly distributes requests across all registered instances, regardless of Availability Zone.

## Connection Draining (Deregistration Delay)

Allows existing connections to finish before an EC2 instance is removed from service.

---

# Real World Applications

- Highly Available Web Applications
- Enterprise APIs
- SaaS Platforms
- E-commerce Websites
- Production Environments
- Microservices Architectures

---

# Skills Demonstrated

- Deploying Application Load Balancers
- Creating Target Groups
- Configuring Health Checks
- Implementing HTTPS using ACM
- Building Launch Templates
- Creating Auto Scaling Groups
- Configuring Dynamic Scaling Policies
- Designing Highly Available Architectures
