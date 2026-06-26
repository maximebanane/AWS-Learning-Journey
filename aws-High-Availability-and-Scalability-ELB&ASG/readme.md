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

# Part 2 – Launch Template

Created a Launch Template containing:

- Amazon Linux AMI
- Instance Type
- Security Group
- Key Pair
- User Data

The Launch Template is used by the Auto Scaling Group to launch identical EC2 instances automatically.

📷 Screenshot

- **06-launch-template.png**

---

# Part 3 – Auto Scaling Group

Created an Auto Scaling Group.

Configuration:

- Minimum Capacity: 2
- Desired Capacity: 2
- Maximum Capacity: 4

The Auto Scaling Group was attached to the existing Application Load Balancer.

📷 Screenshot

- **07-auto-scaling-group.png**

---

# Part 4 – Scaling Policies

Configured Dynamic Scaling Policies using CloudWatch metrics.

Example:

- Scale Out
  - CPU > 70%

- Scale In
  - CPU < 30%

📷 Screenshot

- **08-scaling-policy.png**

---

# Test Auto Scaling

Generated CPU load to trigger a Scale Out event.

The Auto Scaling Group automatically launched an additional EC2 instance.

📷 Screenshot

- **09-scale-out.png**

After CPU utilization returned to normal, the Auto Scaling Group automatically terminated the additional EC2 instance.

📷 Screenshot

- **10-scale-in.png**

---

# Concepts Learned

## High Availability

Deploy applications across multiple Availability Zones to eliminate single points of failure.

## Scalability

Automatically increase or decrease infrastructure capacity according to demand.

## Application Load Balancer

- Layer 7 (HTTP / HTTPS)
- Host-based routing
- Path-based routing
- Content-based routing
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

## Cross-Zone Load Balancing

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
- Implementing Path-Based Routing
- Building Launch Templates
- Creating Auto Scaling Groups
- Configuring Dynamic Scaling Policies
- Designing Highly Available Architectures
