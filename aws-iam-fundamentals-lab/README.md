# AWS IAM Fundamentals Lab

## Objective

Understand AWS IAM basics by creating users, groups, and applying permissions.

---

## Steps Completed

### 1. Root Account Login
Logged into AWS root account to set up initial IAM configuration.

### 2. IAM User Creation
Created a new IAM administrator user for daily usage.

### 3. IAM Group Creation
Created a group called `Administrators`.

### 4. Permissions
Attached the AWS managed policy `AdministratorAccess` to the group.

### 5. MFA Setup
Enabled Multi-Factor Authentication (MFA) for improved security.

### 6. IAM Role for EC2

Created an IAM role attached to an EC2 instance to securely grant access to AWS services (such as S3 or CloudWatch) without using static credentials.

This improves security by using temporary credentials via AWS IAM roles.

---

## Key Learnings

- Root account should never be used for daily tasks
- IAM users and groups simplify permission management
- Policies define access rights in AWS
- MFA is essential for security
- IAM roles provide secure, temporary access to AWS services without using long-term credentials.

---

## Screenshots

See `/screenshots` folder for evidence of each step.
