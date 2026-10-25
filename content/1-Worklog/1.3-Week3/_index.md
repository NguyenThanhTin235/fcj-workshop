---
title: "Week 3 Worklog"
date: 2026-10-05
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

**Period:** 19/10/2026 → 23/10/2026  
**Topic:** Amazon RDS, Amazon Lightsail & Containers, EC2 Auto Scaling, Amazon CloudWatch & Route 53  
**Status:** Completed

### Week 3 Objectives:

* Master relational database management with Amazon RDS: Multi-AZ architecture, Read Replicas, and automated backups
* Explore simplified computing with Amazon Lightsail: deploy WordPress VPS and orchestrate container services
* Build scalable and fault-tolerant architectures using Application Load Balancers (ALB) and Auto Scaling Groups (ASG)
* Implement full-stack monitoring with Amazon CloudWatch: Metrics, Logs Insights, Alarms, and Dashboards
* Configure a Hybrid DNS resolution architecture using Amazon Route 53 Resolver

---

### Tasks to be carried out this week:

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Explore Amazon RDS: Multi-AZ (synchronous), Read Replicas (asynchronous), and gp3 SSD storage<br>- Provision RDS MySQL in Private Subnets across multiple AZs using a DB Subnet Group<br>- Restrict database Security Group inbound port 3306 strictly to the EC2 Web Server<br>- Connect application, test CRUD operations, and configure Automated Backups & manual DB Snapshots | 19/10/2026 | 19/10/2026 | <https://000005.awsstudygroup.com/> |
| Tue | - Deploy a WordPress VPS instance on Amazon Lightsail, attach Static IP, and install Let's Encrypt SSL<br>- Migrate the WordPress database to Amazon Lightsail Managed Database<br>- Install `lightsailctl` plugin, Docker CLI, and deploy public container images<br>- Build a custom Docker image locally, push to Lightsail Container Service, and set up Health checks | 20/10/2026 | 20/10/2026 | <https://000045.awsstudygroup.com/><br><https://000046.awsstudygroup.com/> |
| Wed | - Build a standardized Launch Template with custom AMI and User Data scripts for automated bootstrap<br>- Deploy Application Load Balancer (ALB) and Target Group with root path (`/`) Health Checks<br>- Create a multi-AZ Auto Scaling Group (ASG) with Min, Desired, and Max capacity parameters<br>- Validate scaling policies: Manual Scaling, Scheduled Scaling, and Dynamic Target Tracking (CPU > 50%) | 21/10/2026 | 21/10/2026 | <https://000006.awsstudygroup.com/> |
| Thu | - Monitor EC2/RDS metrics using CloudWatch Metrics, Metric Math, and Search Expressions<br>- Install CloudWatch Unified Agent on EC2 to collect Memory/Disk metrics and operating system logs<br>- Query centralized application logs using CloudWatch Logs Insights syntax<br>- Configure CloudWatch Alarms with Amazon SNS email alerts and design a centralized CloudWatch Dashboard | 22/10/2026 | 22/10/2026 | <https://000008.awsstudygroup.com/> |
| Fri | - Understand Hybrid DNS architecture with Route 53 Resolver: Inbound/Outbound Endpoints and Forwarding Rules<br>- Launch a simulated on-premises Active Directory Domain Controller using CloudFormation<br>- Configure Route 53 Outbound Endpoint & Resolver Rule to forward on-prem domain queries<br>- Configure Route 53 Inbound Endpoint for resolving AWS Private Hosted Zones from on-premises<br>- Verify bidirectional hybrid DNS lookups and clean up all provisioned lab resources | 23/10/2026 | 23/10/2026 | <https://000010.awsstudygroup.com/> |

---

### Expected Week 3 Outcomes:

* **Database Management with Amazon RDS:**
  * Contrasted self-managed EC2 databases with fully-managed Amazon RDS services.
  * Mastered automated Multi-AZ failover mechanisms and Read Replica read scaling.
  * Successfully deployed an RDS MySQL instance in a Private Subnet, secured access over port 3306, and validated Point-in-time recovery.
* **Simplified Cloud Computing with Amazon Lightsail:**
  * Grasped Lightsail's fixed-cost model; deployed WordPress with Static IP and custom domain SSL.
  * Migrated database workloads to Lightsail Managed Database for enhanced resilience.
  * Utilized `lightsailctl` to package, push, and deploy containers on Lightsail Container Service with health monitoring.
* **Automated Scalability & Load Balancing with EC2 Auto Scaling:**
  * Implemented cloud elasticity and traffic distribution using Application Load Balancers (ALB).
  * Standardized instance provisioning via Launch Templates and Target Group Health Checks.
  * Operated multi-AZ Auto Scaling Groups, successfully validating dynamic scaling triggered by CPU workloads.
* **Centralized Observability with Amazon CloudWatch:**
  * Collected deep OS-level metrics (RAM, Disk) using the unified CloudWatch Agent on EC2.
  * Filtered and analyzed distributed logs rapidly using CloudWatch Logs Insights queries.
  * Automated email alerting using CloudWatch Alarms & Amazon SNS, aggregating operational metrics on custom Dashboards.
* **Hybrid DNS Infrastructure with Amazon Route 53 Resolver:**
  * Mastered cross-environment DNS resolution between on-premises networks and AWS VPCs.
  * Configured Route 53 Inbound & Outbound Endpoints along with Resolver Forwarding Rules.
  * Successfully validated seamless bidirectional DNS resolution and executed safe resource teardown.
