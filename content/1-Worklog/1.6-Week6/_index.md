---
title: "Worklog Week 6"
date: 2026-10-05
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

**Duration:** 09/11/2026 → 13/11/2026  
**Topic:** Database Migration, Serverless Automation with AWS Lambda & Monitoring with CloudWatch and Grafana  
**Status:** Completed

### Objectives for Week 6:

* Execute heterogeneous database schema conversion and migration using AWS SCT and AWS DMS (Replication Instance & Serverless)
* Automate EC2 start/stop schedules with AWS Lambda and Slack webhooks to optimize non-24/7 compute costs
* Deploy Grafana on Linux EC2 and integrate Amazon CloudWatch for metric visualization and alerting

---

### Planned Tasks for This Week:

| Day | Task | Start Date | End Date | Resource Link |
| --- | --- | --- | --- | --- |
| Mon | - Set up EC2 & AWS SCT; select DMS source (Oracle/SQL Server) and target (RDS/Aurora/S3)<br>- Convert schema/procedural code via SCT and configure DMS Replication Instance, endpoints, and Full Load + CDC task | 09/11/2026 | 09/11/2026 | <https://000043.awsfcaj.com/> |
| Tue | - Test DMS Serverless replication and auto-scaling behavior<br>- Monitor DMS via CloudWatch metrics, table stats, event notifications, and task logs<br>- Troubleshoot memory pressure/table errors and clean up resources | 10/11/2026 | 10/11/2026 | <https://000043.awsfcaj.com/> |
| Wed | - Prepare VPC, Security Group, tagged EC2 instance, and Slack Incoming Webhook<br>- Create IAM Role and AWS Lambda functions to auto-stop/start EC2<br>- Test scheduled automation and clean up lab resources | 11/11/2026 | 11/11/2026 | <https://000022.awsfcaj.com/> |
| Thu | - Provision VPC, subnet, Security Group, and Linux EC2 instance<br>- Configure IAM User/Access Key and IAM Role for CloudWatch read access<br>- Install and start open-source Grafana on Linux EC2 | 12/11/2026 | 12/11/2026 | <https://000029.awsfcaj.com/> |
| Fri | - Connect Grafana to Amazon CloudWatch data source and build metric dashboards & alerts<br>- Week 6 wrap-up and clean up all remaining lab resources | 13/11/2026 | 13/11/2026 | <https://000029.awsfcaj.com/> |

---

### Key Outcomes for Week 6:

* **Database Migration (AWS SCT & DMS):**
  * Converted heterogeneous schemas and migrated data using DMS Replication Instances and DMS Serverless with CDC.
  * Monitored replication health via CloudWatch metrics/logs and resolved memory and table-level migration errors.
* **Serverless Cost Automation (AWS Lambda):**
  * Automated EC2 start/stop lifecycles via Lambda and IAM Roles using resource tags, reducing idle compute costs.
  * Integrated Slack Incoming Webhooks for real-time execution notifications.
* **Observability (CloudWatch & Grafana):**
  * Deployed Grafana on EC2 with least-privilege IAM permissions to query and visualize CloudWatch metrics.
  * Configured custom dashboards and alerts for proactive infrastructure monitoring.
