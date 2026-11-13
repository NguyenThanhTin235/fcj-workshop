---
title: "Worklog Week 4"
date: 2026-10-05
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

**Duration:** 26/10/2026 → 30/10/2026  
**Topic:** AWS CLI, Amazon DynamoDB, Amazon ElastiCache & Networking Workshop  
**Status:** Completed

### Objectives for Week 4:

* Automate AWS administration and VPC/EC2 provisioning using AWS CLI v2
* Operate Amazon DynamoDB (data models, capacity modes, consistency, LSI/GSI, Python Boto3 CRUD)
* Deploy Amazon ElastiCache (Redis) in Cluster Mode Disabled/Enabled and test caching with `redis-cli` and Python
* Architect multi-VPC networking with VPC Peering, AWS Transit Gateway, and VPC Endpoints (Gateway & Interface)

---

### Planned Tasks for This Week:

| Day | Task | Start Date | End Date | Resource Link |
| --- | --- | --- | --- | --- |
| Mon | - Configure AWS CLI v2 (named profiles, json/yaml/text/table output, `--cli-auto-prompt`)<br>- Run S3 (`mb`, `cp`, `sync`, `rb`), SNS (Topics/Subscriptions/Publish), and IAM (Users/Groups/Access Keys) commands<br>- Provision VPC, Subnets, IGW, Route Tables, Key Pairs, Security Groups, and EC2 (`aws ec2 run-instances`) using `--query` (JMESPath) and `--filter`; clean up | 26/10/2026 | 26/10/2026 | <https://000011.awsfcaj.com/> |
| Tue | - Study DynamoDB Key-Value/Document models, On-Demand vs Provisioned (RCU/WCU), Eventual vs Strong Consistency, and LSI/GSI (Query vs Scan)<br>- Perform PutItem, GetItem, UpdateItem, DeleteItem and write Python `boto3` CRUD/query scripts | 27/10/2026 | 27/10/2026 | <https://000060.awsfcaj.com/> |
| Wed | - Compare ElastiCache Redis Cluster Mode Disabled (Primary + Read Replicas) vs Enabled (Shards) and Primary/Reader/Configuration/Node endpoints<br>- Deploy Redis in a Private Subnet, test `SET`/`GET`/`TTL` via `redis-cli`, and run Python (`redis-py`) caching scripts | 28/10/2026 | 28/10/2026 | <https://000061.awsfcaj.com/> |
| Thu | - Networking Workshop (Part 1): design RFC 1918 multi-VPC layouts (Non-Prod, Prod, Shared Services, Datacenter)<br>- Configure Public/Private Subnets, Route Tables, IGW, NAT Gateway, Security Groups, NACLs, and VPC Peering (bidirectional routes & SG referencing) | 29/10/2026 | 29/10/2026 | <https://000092.awsfcaj.com/> |
| Fri | - Networking Workshop (Part 2): deploy AWS Transit Gateway (Hub-and-Spoke attachments & route tables) and VPC Endpoints (S3 Gateway Endpoint + PrivateLink Interface Endpoint with Endpoint Policies)<br>- Review Week 4 architecture and clean up all lab resources | 30/10/2026 | 30/10/2026 | <https://000092.awsfcaj.com/> |

---

### Key Outcomes for Week 4:

* **AWS CLI v2:** Automated S3, SNS, IAM, VPC, and EC2 provisioning from the terminal using named profiles, `--cli-auto-prompt`, JMESPath `--query`, and `--filter`.
* **Amazon DynamoDB:** Designed Partition/Sort keys and LSI/GSI indexes, balanced On-Demand vs Provisioned RCU/WCU and read consistency, and automated CRUD/Query operations with Python `boto3`.
* **Amazon ElastiCache (Redis):** Deployed private Redis clusters, distinguished Cluster Mode Disabled vs Enabled and endpoint types, and validated sub-millisecond caching with `redis-cli` and `redis-py`.
* **Multi-VPC Networking:** Implemented RFC 1918 enterprise VPCs connected via VPC Peering and Hub-and-Spoke Transit Gateway, and secured private AWS service traffic with Gateway/Interface VPC Endpoints and Endpoint Policies.
