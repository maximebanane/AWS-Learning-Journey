# AWS EC2 Networking Fundamentals

This section covers key EC2 networking concepts used in real-world cloud infrastructure: public/private IPs, Elastic IPs, Placement Groups, Elastic Network Interfaces, and EC2 Hibernate.

## Topics Covered

### 001 - Private vs Public IP vs Elastic IP

In this lab, I learned the difference between private IP addresses, public IP addresses, and Elastic IP addresses in AWS EC2.

#### Key Concepts

- **Private IP**: Used for communication inside the VPC.
- **Public IP**: Used to access an EC2 instance from the internet.
- **Elastic IP**: A static public IPv4 address that remains attached even if the instance is stopped and started again.

#### Real-World Applications

- Hosting a public web server with a fixed IP address.
- Allowing external services to whitelist a stable IP.
- Keeping the same public IP after restarting or replacing an EC2 instance.
- Separating internal traffic from internet-facing traffic.

---

### 002 - Private vs Public IP vs Elastic IP Hands-On

In this hands-on lab, I launched an EC2 instance and tested how private IPs, public IPs, and Elastic IPs behave.

#### What I Practiced

- Launching an EC2 instance.
- Checking private and public IP addresses.
- Stopping and starting an instance to observe public IP changes.
- Allocating and associating an Elastic IP.
- Verifying that the Elastic IP remains stable.

#### Real-World Applications

This is useful when deploying production servers that need a reliable public endpoint, such as:

- Web servers
- Bastion hosts
- VPN servers
- Monitoring agents
- Small production applications

---

### 003 - EC2 Placement Groups

This lesson explains how EC2 Placement Groups control how instances are placed on AWS infrastructure.

#### Types of Placement Groups

- **Cluster Placement Group**: Places instances close together for low-latency networking.
- **Spread Placement Group**: Spreads instances across different hardware to reduce failure risk.
- **Partition Placement Group**: Splits instances across partitions, useful for large distributed systems.

#### Real-World Applications

- High-performance computing workloads.
- Low-latency applications.
- Big data clusters.
- Distributed databases.
- Applications that need high availability across physical hardware.

---

### 004 - EC2 Placement Groups Hands-On

In this hands-on lab, I created and tested EC2 Placement Groups.

#### What I Practiced

- Creating different types of Placement Groups.
- Understanding how instance placement affects performance and resilience.
- Associating EC2 instances with Placement Groups.

#### Real-World Applications

Placement Groups are important when designing architectures where performance, latency, and fault tolerance matter.

Examples:

- Financial trading systems
- Gaming servers
- Hadoop/Spark clusters
- Cassandra clusters
- Critical multi-instance applications

---

### 005 - Elastic Network Interfaces Overview

An Elastic Network Interface, or ENI, is a virtual network card attached to an EC2 instance.

#### Key Concepts

An ENI can include:

- Private IPv4 addresses
- Public IPv4 addresses
- Security groups
- MAC address
- Elastic IP association

#### Real-World Applications

- Moving a network interface from one EC2 instance to another.
- Building failover architectures.
- Separating management traffic from application traffic.
- Creating appliances such as firewalls, NAT instances, or monitoring systems.

---

### 006 - Elastic Network Interfaces Hands-On

In this lab, I practiced creating and attaching ENIs to EC2 instances.

#### What I Practiced

- Creating an ENI.
- Attaching an ENI to an EC2 instance.
- Understanding how security groups and private IPs are linked to ENIs.
- Testing how ENIs can be moved between instances.

#### Real-World Applications

ENIs are useful in production when an application must keep the same private IP even if the underlying EC2 instance changes.

Example use cases:

- High availability failover
- Network appliances
- Firewall instances
- Active/passive server architecture

---

### 008 - EC2 Hibernate

EC2 Hibernate allows an instance to pause and resume later while preserving the RAM state.

#### Key Concepts

When an instance hibernates:

- The RAM content is saved to the EBS root volume.
- The instance stops.
- When restarted, the application state is restored.
- The root volume must be encrypted EBS.
- The instance RAM must be supported by AWS hibernation limits.

#### Real-World Applications

- Saving boot time for applications with long startup processes.
- Pausing development environments.
- Preserving in-memory application state.
- Reducing compute costs while keeping the environment ready to resume.

---

### 009 - EC2 Hibernate Hands-On

In this hands-on lab, I tested EC2 Hibernate behavior.

#### What I Practiced

- Enabling hibernation during EC2 launch.
- Checking root EBS volume requirements.
- Starting and hibernating an instance.
- Verifying that the instance state is restored after resume.

#### Real-World Applications

This is useful for workloads where startup time matters, such as:

- Developer workstations
- Data analysis environments
- Applications with long initialization time
- Temporary environments that need to preserve state

---

## Summary

This section helped me understand how EC2 networking and instance behavior work in real-world AWS environments.

I practiced concepts that are essential for cloud architecture, including:

- Public and private networking
- Static IP management
- High-performance instance placement
- Network interface management
- Instance hibernation
- Cost optimization
- High availability design

These skills are useful for roles such as:

- Cloud Engineer
- AWS Solutions Architect
- Cloud Security Engineer
- DevOps Engineer
