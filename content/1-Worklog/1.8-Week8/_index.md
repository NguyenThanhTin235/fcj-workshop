---
title: "Worklog Week 8"
date: 2026-10-05
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

**Duration:** 23/11/2026 → 27/11/2026  
**Topic:** Infrastructure as Code (Three-Tier CloudFormation), EC2 Right-Sizing, VPC Flow Logs Monitoring, IAM Cost Governance & EBS Backup Automation/Anomaly Detection  
**Status:** Completed

### Objectives for Week 8:

* Deploy a complete Three-Tier Web Architecture (Web, Application, Database tiers) along with Lambda, VPC, and EC2 resources using AWS CloudFormation
* Optimize compute costs by collecting EC2 metrics via Amazon CloudWatch Agent and analyzing right-sizing recommendations in Cost Optimization Hub and AWS Compute Optimizer
* Monitor network traffic and troubleshoot connectivity by enabling and analyzing Amazon VPC Flow Logs
* Enforce cost and usage governance with IAM policies restricting regions, EC2 instance families/sizes, and EBS volumes
* Automate Amazon EBS snapshot archiving with Amazon Data Lifecycle Manager (DLM) and detect backup anomalies using AWS Backup anomaly detection

---

### Planned Tasks for This Week:

| Day | Task | Start Date | End Date | Resource Link |
| --- | --- | --- | --- | --- |
| Mon | - Prepare environment and deploy Lambda, VPC, and EC2 using AWS CloudFormation<br>- Deploy a Three-Tier Web Architecture stack and test Web, Application, and Database tier access<br>- Clean up CloudFormation stacks and lab resources | 23/11/2026 | 23/11/2026 | <https://000102.awsfcaj.com/> |
| Tue | - Launch EC2 instance, create and attach IAM Role for CloudWatch Agent, and install CloudWatch Agent<br>- Review EC2 right-sizing recommendations in Cost Optimization Hub and AWS Compute Optimizer<br>- Apply EC2 right-sizing best practices and clean up resources | 24/11/2026 | 24/11/2026 | <https://000032.awsfcaj.com/> |
| Wed | - Prepare network environment and create/enable Amazon VPC Flow Logs<br>- Monitor network traffic and analyze flow log records for network infrastructure observability<br>- Clean up VPC Flow Logs and lab resources | 25/11/2026 | 25/11/2026 | <https://000074.awsfcaj.com/> |
| Thu | - Create IAM Group and IAM User for cost governance testing<br>- Create, attach, and validate IAM policies limiting AWS Region, EC2 instance family, EC2 instance size, and EBS volume size/type<br>- Clean up IAM users, groups, and policies | 26/11/2026 | 26/11/2026 | <https://000064.awsfcaj.com/> |
| Fri | - Launch EC2 and configure single and multiple Amazon DLM policy schedules to automatically archive EBS snapshots, then review results<br>- Set up S3 bucket, EBS volume, and CloudFormation stack to test AWS Backup anomaly detection for EBS backups and monitor alerts<br>- Week 8 wrap-up and clean up all remaining lab resources | 27/11/2026 | 27/11/2026 | <https://000088.awsfcaj.com/><br><https://000089.awsfcaj.com/> |

---

### Key Outcomes for Week 8:

* **Infrastructure as Code (Three-Tier CloudFormation):**
  * Provisioned multi-tier architectures (Web, Application, Database) alongside VPC, EC2, and Lambda resources declaratively with AWS CloudFormation and verified end-to-end tier connectivity.
* **EC2 Right-Sizing & Cost Governance:**
  * Collected OS-level memory and disk metrics via CloudWatch Agent to unlock accurate EC2 right-sizing recommendations in Cost Optimization Hub and AWS Compute Optimizer.
  * Implemented preventive cost controls using IAM policies to restrict allowed AWS Regions, EC2 families/sizes, and EBS volumes.
* **Network Monitoring & EBS Backup Resilience:**
  * Enabled VPC Flow Logs to capture and inspect IP traffic across VPC network interfaces for security and troubleshooting.
  * Automated EBS snapshot lifecycle archiving with Amazon DLM schedules and configured AWS Backup anomaly detection to monitor unexpected backup changes on EBS volumes.
