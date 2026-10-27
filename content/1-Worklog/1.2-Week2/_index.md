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

* Master compute concepts and practice launching Amazon EC2 instances
* Configure secure connectivity to EC2 and deploy a sample web application
* Assign IAM Roles to EC2 to access AWS services securely without hardcoding Access Keys
* Store objects and host static websites using Amazon S3
* Deploy Amazon RDS relational database in a Private Subnet and connect from EC2

### Tasks to be carried out this week:
| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Explore compute essentials with Amazon EC2:<br>&nbsp;&nbsp;+ Concepts: Instance types, AMI (Amazon Machine Image), EBS Volumes<br>&nbsp;&nbsp;+ Instance families (General Purpose, Compute, Memory Optimized)<br>- Hands-on EC2 deployment:<br>&nbsp;&nbsp;+ Launch EC2 Linux Instance (Amazon Linux 2023) in Public Subnet<br>&nbsp;&nbsp;+ Create and securely manage Key Pair (.pem)<br>&nbsp;&nbsp;+ Configure Security Group opening port 22 (SSH) and 80 (HTTP) | 12/10/2026 | 12/10/2026 | <https://000004.awsstudygroup.com/> |
| Tue | - Connect and manage EC2 Instance:<br>&nbsp;&nbsp;+ Connect via SSH Client and EC2 Instance Connect<br>&nbsp;&nbsp;+ Manage EBS Volumes and create Snapshot backups<br>&nbsp;&nbsp;+ Create Custom AMI from running EC2 instance<br>- Deploy Web Application on EC2:<br>&nbsp;&nbsp;+ Install Web Server (LAMP stack / Node.js) on Amazon Linux 2023<br>&nbsp;&nbsp;+ Deploy sample AWS User Management application<br>&nbsp;&nbsp;+ Verify application access via Public IPv4 / Elastic IP | 13/10/2026 | 13/10/2026 | <https://000004.awsstudygroup.com/> |
| Wed | - Authorize applications with IAM Roles for EC2:<br>&nbsp;&nbsp;+ Security risks of storing permanent Access Keys on compute instances<br>&nbsp;&nbsp;+ IAM Instance Profiles and temporary credential mechanisms<br>- Hands-on IAM Role for EC2:<br>&nbsp;&nbsp;+ Create S3 Bucket for storage<br>&nbsp;&nbsp;+ Create IAM Role with AmazonS3ReadOnlyAccess permissions<br>&nbsp;&nbsp;+ Attach IAM Role to EC2 Instance<br>&nbsp;&nbsp;+ Verify S3 access via AWS CLI from EC2 without configuring access keys | 14/10/2026 | 14/10/2026 | <https://000048.awsstudygroup.com/> |
| Thu | - Object storage with Amazon S3:<br>&nbsp;&nbsp;+ Concepts: S3 Bucket, Object, S3 URI, 11 9s durability (99.999999999%)<br>&nbsp;&nbsp;+ Object Versioning and Lifecycle Rules<br>- Hands-on Static Website Hosting on S3:<br>&nbsp;&nbsp;+ Create S3 Bucket and upload static website files (HTML, CSS, JS)<br>&nbsp;&nbsp;+ Enable Static Website Hosting<br>&nbsp;&nbsp;+ Configure Bucket Policy for Public Read and disable Block Public Access<br>&nbsp;&nbsp;+ Verify website access via S3 Website Endpoint | 15/10/2026 | 15/10/2026 | <https://000057.awsstudygroup.com/> |
| Fri | - Relational Database with Amazon RDS:<br>&nbsp;&nbsp;+ Concepts: Amazon RDS and DB Engines (MySQL, PostgreSQL, MariaDB)<br>&nbsp;&nbsp;+ Multi-AZ architecture for high availability and Read Replicas<br>- Hands-on RDS deployment and connectivity:<br>&nbsp;&nbsp;+ Create DB Subnet Group across Private Subnets in VPC<br>&nbsp;&nbsp;+ Launch RDS MySQL Instance in Private Subnet<br>&nbsp;&nbsp;+ Configure Security Group allowing inbound traffic from EC2 on port 3306<br>&nbsp;&nbsp;+ Connect web application from EC2 to RDS database and verify data operations<br>- Clean up lab resources | 16/10/2026 | 16/10/2026 | <https://000005.awsstudygroup.com/> |

### Expected Week 2 Outcomes:

* **Compute Foundations with Amazon EC2:**
  * Mastered EC2 hardware sizing metrics and instance families (General Purpose, Compute, Memory, Storage Optimized) to choose the optimal type for specific application workloads.
  * Understood instance provisioning mechanisms using Amazon Machine Images (AMIs) and persistent block storage via Amazon Elastic Block Store (EBS Volumes).
  * Successfully launched an Amazon Linux 2023 EC2 instance within the Public Subnet of the custom VPC built in Week 1.
  * Generated and securely managed SSH Key Pairs (.pem); configured inbound/outbound Security Group rules strictly limiting access to ports 22 (SSH) and 80 (HTTP).
* **Remote Management & Application Deployment on EC2:**
  * Proficiently established remote management connections to EC2 instances using both standalone SSH clients and browser-based EC2 Instance Connect.
  * Mastered EBS lifecycle management: volume attachment/detachment, live volume resizing, and taking point-in-time EBS Snapshots for data durability.
  * Built custom AMIs from pre-configured running instances to establish standardized deployment images for future scaling.
  * Successfully installed web server runtimes (LAMP stack / Node.js) on Amazon Linux 2023, deployed the AWS User Management sample application, and verified public accessibility via Elastic IP.
* **Application Authorization via IAM Roles for EC2:**
  * Recognized severe security risks associated with embedding permanent Access Keys and Secret Access Keys in application code or server configuration files.
  * Understood the underlying mechanisms of IAM Instance Profiles and the Instance Metadata Service (IMDSv2) for delivering short-lived temporary credentials.
  * Created an IAM Role with least-privilege permissions (`AmazonS3ReadOnlyAccess`), attached it directly to the EC2 instance, and validated secure S3 data querying via the AWS CLI without permanent credentials.
* **Object Storage & Static Website Hosting with Amazon S3:**
  * Mastered core S3 storage fundamentals: Buckets, Objects, S3 URIs, strong read-after-write consistency, and 11 9s of data durability (99.999999999%).
  * Implemented advanced data governance features: enabled Object Versioning to prevent accidental deletion and configured Lifecycle Rules across S3 Storage Classes for cost efficiency.
  * Successfully hosted a static web application on S3: uploaded website assets (HTML/CSS/JS), enabled Static Website Hosting, defined a Public Read Bucket Policy, adjusted Block Public Access settings, and tested global accessibility via the S3 Website Endpoint.
* **Relational Database Management with Amazon RDS:**
  * Differentiated between self-managed databases hosted on EC2 versus AWS fully managed database services with Amazon RDS.
  * Mastered Multi-AZ deployment concepts for automated synchronous failover and Read Replicas for scalable asynchronous read performance.
  * Provisioned a dedicated DB Subnet Group across isolated Private Subnets, enforcing network isolation according to AWS Well-Architected security principles.
  * Successfully launched an Amazon RDS MySQL/PostgreSQL instance; configured database Security Groups allowing inbound traffic on port 3306 strictly from the web EC2 Security Group.
  * Connected the web tier application to the RDS database, verified CRUD database transactions, took a manual DB Snapshot, and executed a clean teardown of all provisioned cloud resources.
