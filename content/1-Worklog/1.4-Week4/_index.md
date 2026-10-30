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

* Master infrastructure automation and cloud resource management using the AWS Command Line Interface (AWS CLI v2)
* Explore the Amazon DynamoDB NoSQL non-relational database: data modeling, partitioning, secondary indexes, and query performance optimization
* Deploy a distributed in-memory caching solution with Amazon ElastiCache (Redis) to offload database pressure and achieve sub-millisecond response times
* Practice advanced multi-VPC network architectures using VPC Peering, AWS Transit Gateway, and centralized routing solutions
* Complete the comprehensive Networking Workshop lab series focusing on VPC Endpoints (Gateway and Interface Endpoints) to secure internal traffic

---

### Planned Tasks for This Week:

| Day | Task | Start Date | End Date | Resource Link |
| --- | --- | --- | --- | --- |
| Mon | - Explore AWS CLI v2: installation, named profiles configuration, output formatting (json, yaml, text, table)<br>- Secure identity management: compare long-term Access Keys, AWS CloudShell, and IAM Identity Center (SSO) integration<br>- Automate operations across core services: S3 (bucket/object management, data sync), EC2 (state inspection, instance launch)<br>- Apply advanced output filtering with the --query parameter (JMESPath) and --filter to extract exact data | 26/10/2026 | 26/10/2026 | <https://000007.awsstudygroup.com/> |
| Tue | - Study the Amazon DynamoDB NoSQL database foundation: Key-Value and Document data models<br>- Master Partition Key, Sort Key (Composite Primary Key), and data distribution mechanics across physical partitions<br>- Distinguish between Capacity Modes: On-Demand Mode and Provisioned Mode (RCU, WCU)<br>- Design secondary indexes: Local Secondary Index (LSI) and Global Secondary Index (GSI)<br>- Hands-on table creation, PutItem and GetItem operations, Query vs Scan performance comparison, and Time to Live (TTL) expiration | 27/10/2026 | 27/10/2026 | <https://000009.awsstudygroup.com/> |
| Wed | - Understand caching patterns and cache strategies: Cache-Aside (Lazy Loading), Write-Through, and TTL configuration<br>- Compare the two popular caching engines in Amazon ElastiCache: Redis (rich data structures, Multi-AZ, Read Replicas, data persistence) vs Memcached (multi-threaded, simple)<br>- Deploy an ElastiCache Redis Cluster inside a VPC Private Subnet, configure DB Subnet Groups, and restrict ingress traffic via Security Groups<br>- Connect an EC2 web application to ElastiCache, implement query result caching to reduce database load and achieve sub-millisecond latency | 28/10/2026 | 28/10/2026 | <https://000011.awsstudygroup.com/> |
| Thu | - Expand multi-VPC networking architectures:<br>&nbsp;&nbsp;+ Establish VPC Peering connections across intra-region and inter-region VPCs<br>&nbsp;&nbsp;+ Configure bidirectional Route Tables and apply cross-VPC Security Group referencing<br>&nbsp;&nbsp;+ Evaluate non-transitive routing constraints inherent to VPC Peering<br>- Introduce AWS Transit Gateway (TGW) as a centralized Hub-and-Spoke routing engine<br>- Provision a Transit Gateway, attach VPCs (VPC Attachments), construct TGW Route Tables, and verify end-to-end multi-VPC connectivity | 29/10/2026 | 29/10/2026 | <https://000012.awsstudygroup.com/> |
| Fri | - Intensive hands-on Networking Workshop on private connectivity via AWS PrivateLink and VPC Endpoints:<br>&nbsp;&nbsp;+ Deploy a Gateway Endpoint for Amazon S3 to route internal traffic via Route Tables without requiring an Internet Gateway or NAT Gateway<br>&nbsp;&nbsp;+ Configure an Interface Endpoint (AWS PrivateLink) enabling private on-premises and VPC workloads to access AWS services over Private IPs<br>&nbsp;&nbsp;+ Apply strict VPC Endpoint Policies to restrict access solely to approved S3 buckets and authorized operations<br>- Review overall Week 4 infrastructure: CLI automation, NoSQL database, in-memory caching, and hardened multi-VPC networking<br>- Clean up all created lab resources | 30/10/2026 | 30/10/2026 | <https://000013.awsstudygroup.com/> |

---

### Key Outcomes for Week 4:

* **Infrastructure Automation with AWS CLI v2:**
  * Mastered installation, named profiles configuration, and secure credential handling, eliminating reliance on static long-term keys in local development.
  * Acquired proficiency in advanced data extraction using JMESPath via `--query`, allowing precise parsing of complex JSON responses from AWS APIs.
  * Successfully automated routine administrative workflows across S3, EC2, and IAM, significantly enhancing operational speed compared to manual Console navigation.
* **NoSQL Database Management with Amazon DynamoDB:**
  * Developed deep comprehension of distributed storage architecture, partition hashing mechanisms, and seamless auto-scaling capabilities in DynamoDB.
  * Mastered pricing mechanics between On-Demand and Provisioned capacity modes, accurately estimating Read Capacity Units (RCUs) and Write Capacity Units (WCUs) for predictable workloads.
  * Understood the architectural and cost disparities between targeted Query operations and expensive full-table Scans.
  * Successfully implemented Global Secondary Indexes (GSIs) to facilitate new query patterns without schema overhaul, and configured TTL to automatically purge stale records.
* **Application Performance Acceleration with Amazon ElastiCache:**
  * Comprehended the strategic role of in-memory caching layers in shielding underlying relational databases from request spikes and bottlenecks.
  * Appropriately selected the Redis engine for workloads demanding high availability (Multi-AZ Failover), snapshot persistence, and rich data structures.
  * Securely deployed an ElastiCache cluster within private subnets, implemented the Cache-Aside pattern in an application, and achieved sub-millisecond response times for repeated queries.
* **Advanced Multi-VPC Networking & Internal Hardening:**
  * Mastered diverse multi-VPC topologies, determining ideal architectural fits between point-to-point VPC Peering and centralized AWS Transit Gateway deployments.
  * Successfully executed the Networking Workshop series: deployed both Gateway Endpoints and Interface Endpoints for Amazon S3.
  * Enforced robust VPC Endpoint Policies to prevent data exfiltration risks, guaranteeing that all application traffic to AWS services remains exclusively within the private AWS backbone network.
