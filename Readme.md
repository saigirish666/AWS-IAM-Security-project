# Security with AWS: Identity and Access Management (IAM) Guided Project 🔐

This project is part of my cloud journey, focused on foundational IAM security operations in AWS, including user management, policies, roles, and cross-account access. It is a hands-on lab designed to implement best practices using the AWS Console and CLI.

## 🚀 Table of Contents

- [Project Overview](#project-overview)  
- [Lab Sections](#lab-sections)  
- [Key Learnings & Best Practices](#key-learnings--best-practices)  
- [🌟 Observations & Console Evolution](#-observations--console-evolution)  
- [Project Scenario](#project-scenario)  
- [Cleanup](#cleanup)  
- [About This Project](#about-this-project)  

---

## Project Overview

### Objectives

- Set up secure user access in AWS IAM, including creating and managing user accounts, groups, and policies  
- Set up secure permissions and create roles for cross-account access following AWS best practices  
- Manage IAM permissions by configuring policies, understanding policy structures, and enforcing granular access controls  

By completing this project, you will master secure user access, permission management, role creation for cross-account access, and IAM best practices, including granting secure access to third-party auditors.

---

## Lab Sections

### 1. Project Setup & Overview

- 🚀 Learned project outcomes: secure user access, permissions management, cross-account roles, IAM best practices  
- 🚀 Understood core IAM concepts and importance of centralized permission management  
- 🚀 Role assigned: Cloud Security Professional  
- 🚀 Implemented MFA for root user as a security best practice  

### 2. Create an IAM User from the Console

- 🚀 Created a user named `SecurityTeamAdmin` with AdministratorAccess and AWSAccountManagementFullAccess policies  
- 🚀 Best practice: avoid root user for daily tasks; create users with specific permissions instead  

### 3. Create IAM Users from the CLI

- 🚀 Created access keys for IAM users (limit of 2 per AWS account)  
- 🚀 Created users Matt, Sarah, and Deborah with CLI and configured access keys  
- 🚀 Avoided creating access keys on root user  

### 4. Practice Activity: Create User 'Rachel' via CLI

- 🚀 Hands-on CLI user creation  

### 5. Create IAM Groups and Add Users to Groups

- 🚀 Learned group purpose and management via CLI  
- 🚀 Added users to groups and attached policies for centralized control  

### 6. Practice Assessment: Securing AWS Accounts

- 🚀 Completed multiple-choice questions to validate understanding  

### 7. Implement IAM Policies

- 🚀 Created custom IAM policies (managed and inline) via visual and JSON editors  
- 🚀 Created a read-only IAM policy for IAM components  
- 🚀 Attached policy to CloudSecurityTeam group  

### 8. Create and Upload to an S3 Bucket

- 🚀 Created S3 bucket and uploaded Excel files for storage practice  

### 9. Create an IAM Role for an AWS Service

- 🚀 Created an IAM role for EC2 with S3 full access  
- 🚀 Launched an EC2 instance and attached role for service communication  
- 🚀 Verified metadata and did file listings in EC2 shell  

### 10. Practice Activity: Create a Customer-Managed Policy

- 🚀 Created a "S3ListAndReadPolicy" custom policy  

### 11. Use IAM Roles to Grant AWS Cross-Account Access

- 🚀 Created cross-account role `auditfindata` for a second AWS account  
- 🚀 Assigned S3 ReadOnly access to limit permissions for auditing purposes  
- 🚀 Learned that switching roles defaults to a 1-hour session duration  

### 12. Use IAM Roles for Cross-Account Access with External ID

- 🚀 Used CLI to access S3 list and read using role with external ID for added security  

### 13. Revoke an IAM Role

- 🚀 Revoked active sessions by adding `AWSRevokeOlderSessions` policy to IAM role  
- 🚀 Verified revoked access fails when using external ID credentials  

### 14. Practice Activity: Get Cross-Account Access After Revoking Role

- 🚀 Reconfigured CLI after revoking role sessions and tested access denial  

### 15. Setting Permission Boundaries

- 🚀 Explored effective vs ineffective permissions in permission boundaries  
- 🚀 Created `IAMPermissionBoundary` policy to restrict permissions of IAM users  
- 🚀 Restricted users from elevating their own permissions or creating overly permissive users  

### 16. Test and Debug IAM Policies Using IAM Policy Simulator

- 🚀 Simulated denied and allowed actions (e.g., denied `s3:CreateBucket` for user Matt)  
- 🚀 Analyzed reasons for policy evaluation outcomes  

### 17. Cumulative Activity: Deal with a Cloud Security Breach

- 🚀 Created EC2 full access role with S3 privileges  
- 🚀 Used EC2 shell to list S3 buckets  
- 🚀 Enforced permission boundaries to restrict bucket listing  
- 🚀 Terminated EC2 instance to prevent ongoing security risk  
- 🚀 Used EC2 Connect after revoking sessions to test credential restrictions  

---

## Key Learnings & Best Practices

- MFA is critical for root user protection  
- Never use root user for routine tasks; create IAM users with scoped permissions  
- Use groups for efficient permission management  
- IAM roles enable secure cross-account and service permissions  
- Permission boundaries prevent privilege escalation  
- Use IAM policy simulator to validate policies  
- Revoke sessions immediately to mitigate risks from leaked credentials  

---

## 🌟 Observations & Console Evolution

- **IAM Console Enhancements:**  
  - 🚀 The AWS IAM console now provides more intuitive navigation for creating users, groups, roles, and policies in 2025.  
  - 🚀 Policy visual editor and JSON editor are tightly integrated, making policy creation and debugging easier.  
  - 🚀 Permission boundaries UI is clearer, helping users understand effective vs. boundary limits quickly.  

- **CLI Improvements:**  
  - 🚀 AWS CLI now supports streamlined commands for managing users, groups, roles, and policies with better error messages.  
  - 🚀 Cross-account role switching with external IDs is simplified, improving security practices for third-party access.  

- **Security Best Practices Visibility:**  
  - 🚀 The console actively encourages MFA setup for root and IAM users, nudging users towards more secure environments.  
  - 🚀 Policy simulator integration helps visualize policy effects before applying them, reducing misconfigurations.  

- **User Experience (UX):**  
  - 🚀 Consolidated IAM workflows have reduced the number of steps required to create and manage IAM resources.  
  - 🚀 Real-time feedback on policy syntax and permissions helps accelerate learning and correct mistakes during hands-on labs.  

---

## Project Scenario

- Role: Cloud Security Professional  
- Primary responsibility: secure user access, permission management, and compliance with best practices  
- Hands-on experience with real-world scenarios including cross-account access and breach mitigation  

---

## Cleanup

- Removed all created IAM users, groups, roles, and policies after project completion  
- Deleted S3 buckets and EC2 instances to avoid unnecessary charges  
- Revoked any active role sessions and access keys created  

---

## About This Project

This guided project teaches AWS Identity and Access Management (IAM) fundamentals using the AWS Console and CLI, updated for 2025. Designed for cloud security professionals aiming to secure AWS environments by implementing best practices around MFA, policies, permission boundaries, and cross-account roles.

---

### How to Use This Documentation

- Follow the lab sections step-by-step to reproduce the project in your AWS account  
- Use the console and CLI commands as shown in each section  
- Reference the key learnings to implement secure and scalable IAM configurations  

---

*Thank you for reviewing this guided project!*

