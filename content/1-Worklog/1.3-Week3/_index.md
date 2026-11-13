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

* Operate Amazon RDS Multi-AZ, Read Replicas, and automated backups
* Deploy WordPress VPS and container services on Amazon Lightsail
* Build elastic, fault-tolerant architectures with Application Load Balancers (ALB) and Auto Scaling Groups (ASG)
* Implement observability with Amazon CloudWatch (Metrics, Unified Agent, Logs Insights, Alarms, Dashboards)
* Configure bidirectional Hybrid DNS with Amazon Route 53 Resolver

---

### Tasks to be carried out this week:

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Review RDS Multi-AZ (synchronous), Read Replicas (asynchronous), and gp3 SSD<br>- Deploy RDS MySQL in multi-AZ Private Subnets (DB Subnet Group, port 3306 from EC2 SG), test CRUD, and configure Automated Backups & manual Snapshots | 19/10/2026 | 19/10/2026 | <https://000005.awsstudygroup.com/> |
| Tue | - Deploy Lightsail WordPress VPS with Static IP & Let's Encrypt SSL; migrate DB to Lightsail Managed Database<br>- Install `lightsailctl` & Docker CLI, push custom Docker image to Lightsail Container Service, and configure Health Checks | 20/10/2026 | 20/10/2026 | <https://000045.awsstudygroup.com/><br><https://000046.awsstudygroup.com/> |
| Wed | - Create Launch Template (custom AMI + User Data), ALB, and Target Group (`/` Health Checks)<br>- Deploy multi-AZ ASG (Min/Desired/Max) and test Manual, Scheduled, and Target Tracking (CPU > 50%) scaling | 21/10/2026 | 21/10/2026 | <https://000006.awsstudygroup.com/> |
| Thu | - Monitor EC2/RDS with CloudWatch Metrics, Metric Math, and Search Expressions<br>- Install CloudWatch Unified Agent (Memory/Disk/OS logs), query via Logs Insights, and set up SNS Alarms & Dashboards | 22/10/2026 | 22/10/2026 | <https://000008.awsstudygroup.com/> |
| Fri | - Deploy simulated on-prem AD Domain Controller via CloudFormation<br>- Configure Route 53 Resolver Outbound/Inbound Endpoints & Forwarding Rules for Private Hosted Zones, verify bidirectional DNS, and clean up | 23/10/2026 | 23/10/2026 | <https://000010.awsstudygroup.com/> |

---

### Expected Week 3 Outcomes:

* **Amazon RDS:** Configured Multi-AZ failover, Read Replicas, Private Subnet isolation, and Point-in-Time Recovery.
* **Amazon Lightsail:** Deployed WordPress with Static IP/SSL, migrated to Lightsail Managed Database, and shipped containers via `lightsailctl` with health checks.
* **ALB & Auto Scaling:** Standardized provisioning with Launch Templates and validated multi-AZ ASG dynamic CPU scaling behind an ALB.
* **Amazon CloudWatch:** Collected OS-level RAM/Disk metrics and logs via Unified Agent, queried with Logs Insights, and built SNS Alarms and Dashboards.
* **Route 53 Resolver:** Enabled bidirectional Hybrid DNS resolution between on-premises AD and AWS Private Hosted Zones, then cleaned up all lab resources.
