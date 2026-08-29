# AWS Organizations, IAM & Governance

This section covers AWS multi-account management, advanced IAM concepts, centralized identity management, and governance.

## Topics Covered

- AWS Organizations
- Service Control Policies (SCPs)
- Advanced IAM Policies
- Resource-based Policies vs IAM Roles
- IAM Policy Evaluation Logic
- AWS IAM Identity Center
- AWS Directory Service
- AWS Control Tower

---

## 01 - AWS Organizations

AWS Organizations allows centralized management of multiple AWS accounts from a single organization.

Key concepts:
- Management and member accounts
- Organizational Units (OUs)
- Consolidated billing
- Service Control Policies (SCPs)
- Centralized account management

SCPs define the **maximum permissions** available to accounts or Organizational Units. They do not directly grant permissions.



---

## IAM Policies & Permission Evaluation

AWS IAM controls access to AWS resources through policies.

Different types of policies can participate in the authorization process:

- Identity-based policies
- Resource-based policies
- Service Control Policies (SCPs)
- Permission boundaries
- Session policies

### Resource-based Policies vs IAM Roles

**IAM Roles**
- Can be assumed by users, applications, or AWS services
- Provide temporary credentials
- Define permissions for the entity assuming the role

**Resource-based Policies**
- Are attached directly to AWS resources
- Specify which principals can access the resource
- Commonly used with services such as S3, SQS, SNS, and Lambda

---

## 02 - IAM Policy Evaluation Logic

AWS evaluates all applicable policies when deciding whether an API request should be authorized.

The main rules are:

1. Access is implicitly denied by default.
2. An explicit `Allow` can grant access.
3. An explicit `Deny` overrides any `Allow`.

Simplified:

`Explicit Deny > Explicit Allow > Implicit Deny`

Understanding this evaluation logic is essential when troubleshooting AWS permissions.



---

## 03 - AWS IAM Identity Center

AWS IAM Identity Center provides centralized access management for multiple AWS accounts and applications.

Key concepts:
- Single Sign-On (SSO)
- Centralized users and groups
- Permission Sets
- Multi-account access
- Integration with AWS Organizations

Instead of creating separate IAM users in every AWS account, users can authenticate centrally and receive permissions based on assigned Permission Sets.



---

## AWS Directory Service

AWS Directory Service provides managed directory solutions compatible with Microsoft Active Directory.

Main options include:

- AWS Managed Microsoft AD
- AD Connector
- Simple AD

It can be used to connect AWS resources and applications to existing enterprise identity infrastructure.

---

## 04 - AWS Control Tower

AWS Control Tower simplifies the setup and governance of secure multi-account AWS environments.

It builds on services such as AWS Organizations and IAM Identity Center.

Key concepts:
- Landing Zone
- Organizational Units
- Account Factory
- Controls
- Automated account provisioning
- Centralized governance

Control Tower is particularly useful for organizations that need to manage many AWS accounts while enforcing security and governance standards.



---

## Key Takeaways

- **AWS Organizations** → centrally manages multiple AWS accounts.
- **SCPs** → define permission boundaries at the organization or OU level.
- **IAM Policies** → control access to AWS resources.
- **Resource-based Policies** → grant access directly from the resource.
- **Explicit Deny** → always overrides an Allow.
- **IAM Identity Center** → provides centralized SSO and multi-account access.
- **Directory Service** → integrates Active Directory environments with AWS.
- **Control Tower** → automates multi-account setup and governance.
