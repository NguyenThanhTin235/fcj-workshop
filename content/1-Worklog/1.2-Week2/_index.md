---
title: "Week 2 Worklog"
date: 2026-10-05
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

**Period:** 12/10/2026 → 16/10/2026  
**Topic:** EC2, IAM Roles, S3 & RDS  
**Status:** Completed

### Week 2 Objectives:

* Launch and manage Amazon EC2 instances (AMIs, EBS Volumes, Key Pairs, Security Groups)
* Connect to EC2 and deploy a sample web application on Amazon Linux 2023
* Attach IAM Roles to EC2 for keyless access to AWS services
* Store objects and host static websites on Amazon S3
* Deploy Amazon RDS in a Private Subnet and connect from the EC2 web tier

---

### Tasks to be carried out this week:

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Study EC2 concepts (instance families/types, AMIs, EBS Volumes)<br>- Launch Amazon Linux 2023 EC2 in Public Subnet with `.pem` Key Pair and Security Group (ports 22, 80) | 12/10/2026 | 12/10/2026 | <https://000004.awsstudygroup.com/> |
| Tue | - Connect via SSH & EC2 Instance Connect; manage EBS Volumes/Snapshots and create a Custom AMI<br>- Install LAMP/Node.js, deploy AWS User Management app, and verify via Public IPv4 / Elastic IP | 13/10/2026 | 13/10/2026 | <https://000004.awsstudygroup.com/> |
| Wed | - Review risks of hardcoded Access Keys and how IAM Instance Profiles / IMDSv2 work<br>- Create S3 Bucket and IAM Role (`AmazonS3ReadOnlyAccess`), attach to EC2, and test S3 access via AWS CLI | 14/10/2026 | 14/10/2026 | <https://000048.awsstudygroup.com/> |
| Thu | - Study S3 concepts (Buckets, Objects, S3 URI, 11 9s durability, Versioning, Lifecycle Rules)<br>- Upload HTML/CSS/JS, enable Static Website Hosting, configure Public Read Bucket Policy & Block Public Access, and verify S3 Website Endpoint | 15/10/2026 | 15/10/2026 | <https://000057.awsstudygroup.com/> |
| Fri | - Study Amazon RDS (MySQL/PostgreSQL/MariaDB, Multi-AZ, Read Replicas)<br>- Create DB Subnet Group in Private Subnets, launch RDS MySQL (port 3306 from EC2 SG), test CRUD from EC2, take snapshot, and clean up | 16/10/2026 | 16/10/2026 | <https://000005.awsstudygroup.com/> |

---

### Expected Week 2 Outcomes:

* **Amazon EC2 & App Deployment:** Selected instance types, launched Amazon Linux 2023 in a Public Subnet, managed SSH/Instance Connect, EBS resizing/snapshots, Custom AMIs, and deployed the AWS User Management app behind an Elastic IP.
* **IAM Roles for EC2:** Eliminated permanent Access Keys by attaching an `AmazonS3ReadOnlyAccess` IAM Role (Instance Profile / IMDSv2) and verifying keyless AWS CLI access.
* **Amazon S3:** Configured Versioning and Lifecycle Rules, and hosted a public static website via S3 Website Endpoint with Bucket Policy.
* **Amazon RDS:** Deployed RDS MySQL in isolated Private Subnets with a DB Subnet Group and port-3306 SG restriction, verified app CRUD and manual DB Snapshot, and cleaned up resources.
