# AWS Route 53 - DNS & Routing Policies

## Overview

This lab explores Amazon Route 53, AWS's highly available and scalable DNS service.

The objective is to understand how DNS works, create hosted zones and DNS records, configure health checks, and implement different routing policies for highly available applications.

---

## AWS Services Used

- Amazon Route 53
- Amazon EC2
- Application Load Balancer (optional)

---

## Topics Covered

- DNS Fundamentals
- Domain Registration
- Hosted Zones
- DNS Records
- TTL (Time To Live)
- CNAME vs Alias Records
- Route 53 Health Checks
- Route 53 Routing Policies
- Third-Party Domains

---

# Architecture

```
                 Internet
                     │
                     ▼
             Amazon Route 53
                     │
             DNS Resolution
                     │
                     ▼
           Alias / CNAME Record
                     │
                     ▼
              EC2 / Load Balancer
```

---

# Routing Policies

## Simple Routing

Routes traffic to a single resource.

---

## Weighted Routing

Distributes traffic across multiple resources using custom weights.

Example:

- Server A → 80%
- Server B → 20%

---

## Latency Routing

Routes users to the AWS Region with the lowest latency.

---

## Failover Routing

Routes traffic to a secondary endpoint if the primary endpoint becomes unhealthy.

Requires Route 53 Health Checks.

---

## Geolocation Routing

Routes traffic according to the user's geographic location.

---

## Geoproximity Routing

Routes traffic based on the geographic location of AWS resources.

Traffic distribution can be adjusted using Bias.

---

## IP-based Routing

Routes traffic based on the client's IP address (CIDR blocks).

---

## Multi-Value Routing

Returns multiple healthy IP addresses.

Provides basic load distribution without a Load Balancer.

---

# Alias vs CNAME

## Alias

Supported AWS Resources:

- Elastic Load Balancer
- CloudFront
- S3 Static Website
- API Gateway
- Global Accelerator

Advantages:

- No additional Route 53 query charges
- Automatically tracks AWS resource IP changes

---

## CNAME

Maps one hostname to another hostname.

Cannot be used for the root domain.

---

# Health Checks

Health Checks monitor application availability.

Can be used with:

- Failover Routing
- Multi-Value Routing

---

screenshots/

01-hosted-zone-created.png
02-a-record-created.png
03-alias-record-created.png
04-weighted-routing.png
05-latency-routing.png
06-health-check-created.png
07-failover-routing.png
08-geolocation-routing.png
09-multi-value-routing.png

---

# What I Learned

During this lab I learned how to:

- Understand DNS resolution
- Register a domain
- Create Hosted Zones
- Create DNS Records
- Configure TTL values
- Use Alias Records
- Configure Route 53 Health Checks
- Implement all Route 53 Routing Policies
- Configure Third-Party Domains

---

# AWS Concepts

- DNS
- Hosted Zones
- Record Sets
- TTL
- Alias Records
- CNAME
- Health Checks
- High Availability
- Routing Policies

---

# Best Practices

- Use Alias Records whenever possible for AWS resources.
- Use Health Checks for production workloads.
- Choose the appropriate Routing Policy based on the application requirements.
- Keep TTL values low during migrations and failovers.

---

# Cleanup

To avoid AWS charges:

- Delete Health Checks
- Delete DNS Records
- Delete Hosted Zones
- Delete test EC2 instances
- Release Elastic IPs (if used)

---

# References

AWS Route 53 Documentation

https://docs.aws.amazon.com/route53/
