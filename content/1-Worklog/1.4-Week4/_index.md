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

* Master infrastructure automation and cloud administration using the AWS Command Line Interface (AWS CLI v2): profile management, S3, SNS, IAM operations, and end-to-end VPC and EC2 provisioning via CLI
* Operate the Amazon DynamoDB NoSQL database: Key-Value/Document data models, On-Demand vs Provisioned capacity modes, Read Consistency mechanics, GSI/LSI secondary indexes, and programmatic CRUD with Python (Boto3)
* Implement distributed in-memory caching solutions with Amazon ElastiCache (Redis): Cluster Mode Disabled vs Enabled architectures, endpoint routing configurations, and cache interaction using redis-cli and Python scripts
* Complete the advanced Networking Workshop (VPC Components Deep Dive): RFC 1918 multi-VPC addressing schemes, inter-VPC connectivity via VPC Peering and AWS Transit Gateway, and private service traffic security with VPC Endpoints (Gateway & Interface Endpoints)

---

### Planned Tasks for This Week:

| Day | Task | Start Date | End Date | Resource Link |
| --- | --- | --- | --- | --- |
| Mon | - Explore AWS CLI v2: installation, named profiles configuration, output formatting (json, yaml, text, table), and enabling interactive command suggestions (`--cli-auto-prompt`)<br>- Data management and messaging with CLI: execute Amazon S3 operations (`mb`, `cp`, `sync`, `rb`) and manage Amazon SNS (create Topics, configure Subscriptions, publish messages)<br>- IAM identity administration via CLI: create IAM Groups, IAM Users, assign users to groups, and manage Access Keys securely<br>- Automate end-to-end network and compute infrastructure provisioning: create VPC, Subnets, Internet Gateways, Route Tables; generate Key Pairs, Security Groups, and launch EC2 instances (`aws ec2 run-instances`)<br>- Apply advanced output filtering with the `--query` parameter (JMESPath) and `--filter` to extract precise information; practice command-line troubleshooting and resource cleanup | 26/10/2026 | 26/10/2026 | <https://000011.awsfcaj.com/> |
| Tue | - Study Amazon DynamoDB NoSQL core foundations: Key-Value and Document models (Tables, Items, Attributes), naming rules, and supported data types<br>- Distinguish between Capacity Modes: On-Demand Mode vs Provisioned Mode (RCU, WCU calculations); master read consistency mechanisms: Eventually Consistent Reads vs Strongly Consistent Reads<br>- Design secondary indexes: Local Secondary Index (LSI) and Global Secondary Index (GSI); compare query performance and cost trade-offs between targeted Query operations vs full-table Scans<br>- Hands-on data operations: create tables, perform PutItem, GetItem, UpdateItem, DeleteItem; author Python automation scripts using `boto3` for CRUD operations and table querying | 27/10/2026 | 27/10/2026 | <https://000060.awsfcaj.com/> |
| Wed | - Understand in-memory caching architecture with Amazon ElastiCache: caching mechanics, cluster concepts, nodes, and shards for the Redis engine<br>- Distinguish and configure Redis cluster architectures:<br>&nbsp;&nbsp;+ **Cluster Mode Disabled**: 1 Primary Node with Read Replicas for read-scaling and high availability<br>&nbsp;&nbsp;+ **Cluster Mode Enabled**: data partitioning across multiple Shards for horizontal write/read scaling<br>- Master connection endpoints: Primary Endpoint, Reader Endpoint, Configuration Endpoint, and Node Endpoints<br>- Deploy an ElastiCache Redis Cluster within a VPC Private Subnet; connect from internal EC2 instances, execute validation commands via `redis-cli` (SET, GET, TTL), and write Python scripts (`redis-py`) to test query result caching | 28/10/2026 | 28/10/2026 | <https://000061.awsfcaj.com/> |
| Thu | - Networking Workshop (Part 1) - VPC Components & Layout Deep Dive:<br>&nbsp;&nbsp;+ Design enterprise multi-VPC layouts (Non-Prod, Prod, Shared Services, Datacenter) based on RFC 1918 private IP standards (10.0.0.0/8 partitioned into /16 and /24 blocks)<br>&nbsp;&nbsp;+ Deep-dive configuration of core components: Public/Private Subnets, multi-tier Route Tables, Internet Gateways (IGW), and NAT Gateways for secure outbound internet traffic<br>&nbsp;&nbsp;+ Implement layered network defense: configure instance-level Security Groups (Stateful) and subnet-level Network ACLs (Stateless)<br>&nbsp;&nbsp;+ Establish inter-VPC connectivity via VPC Peering: request peering connections, update bidirectional Route Tables, and apply Security Group referencing | 29/10/2026 | 29/10/2026 | <https://000092.awsfcaj.com/> |
| Fri | - Networking Workshop (Part 2) - Transit Gateway, VPC Endpoints & Wrap-up:<br>&nbsp;&nbsp;+ Deploy AWS Transit Gateway (TGW) as a central Hub-and-Spoke routing engine replacing complex peering meshes; configure TGW Attachments and TGW Route Tables<br>&nbsp;&nbsp;+ Secure AWS service traffic via VPC Endpoints (AWS PrivateLink): provision a Gateway Endpoint for Amazon S3 attached to the Private Subnet Route Table; deploy an Interface Endpoint enabling private IP connectivity from VPC and simulated on-premises environments<br>&nbsp;&nbsp;+ Enforce strict VPC Endpoint Policies to control resource access and prevent data exfiltration risks<br>- Review overall Week 4 architecture: AWS CLI automation, DynamoDB NoSQL, ElastiCache Redis in-memory caching, and advanced multi-VPC networking with Transit Gateway & VPC Endpoints<br>- Clean up all created lab resources | 30/10/2026 | 30/10/2026 | <https://000092.awsfcaj.com/> |

---

### Key Outcomes for Week 4:

* **Infrastructure Automation with AWS CLI v2:**
  * Mastered installation, named profiles configuration, and leveraged `--cli-auto-prompt` for rapid syntax discovery and parameter validation.
  * Successfully administered cloud storage and messaging services (Amazon S3, Amazon SNS) and managed IAM identities (Users, Groups, Access Keys) purely through the command-line interface.
  * Commanded end-to-end provisioning of VPC network foundations (VPCs, Subnets, IGWs, Route Tables) and EC2 instances via scriptable CLI commands, eliminating reliance on the AWS Console.
  * Mastered advanced output filtering with JMESPath via `--query` and refined resource status filtering with `--filter`.
* **NoSQL Database Management with Amazon DynamoDB:**
  * Gained a solid understanding of distributed storage architecture, Key-Value and Document data models, and partition distribution via Partition Keys and Sort Keys.
  * Mastered pricing mechanics between On-Demand and Provisioned capacity modes (RCU/WCU cost optimization) alongside data read consistency behaviors (Eventually Consistent vs Strongly Consistent Reads).
  * Understood the operational and cost differences between targeted Query searches and costly full-table Scans; successfully implemented Global Secondary Indexes (GSIs) and Local Secondary Indexes (LSIs) for flexible query patterns.
  * Programmed Python automation scripts utilizing the `boto3` SDK to perform automated CRUD actions and efficient table querying.
* **Application Performance Acceleration with Amazon ElastiCache (Redis):**
  * Comprehended the strategic value of in-memory caching in shielding underlying databases from heavy workloads and eliminating repeated query latencies.
  * Clearly distinguished between **Cluster Mode Disabled** (ideal for read-scaling via Read Replicas) and **Cluster Mode Enabled** (data partitioning across Shards for horizontal write scaling).
  * Mastered the appropriate use cases for Primary Endpoints, Reader Endpoints, Configuration Endpoints, and Node Endpoints.
  * Securely deployed Redis clusters inside private subnets, verified connectivity from EC2 instances using `redis-cli`, and authored Python caching implementations (`redis-py`) achieving sub-millisecond response latencies.
* **Hardened Private Connectivity & Architecture with Networking Workshop:**
  * Successfully structured enterprise multi-VPC layouts conforming to RFC 1918 standards (Non-Prod, Prod, Shared Services, Datacenter), establishing multi-tier routing with Route Tables and dual-layer defense via Security Groups and NACLs.
  * Mastered both inter-VPC connectivity paradigms: point-to-point **VPC Peering** for simple connections, and centralized Hub-and-Spoke **AWS Transit Gateway (TGW)** for scalable enterprise routing.
  * Implemented AWS PrivateLink solutions using both **Gateway Endpoints** (internal S3 routing via Route Tables) and **Interface Endpoints** (dedicated Private IP communication for VPC and on-premises traffic).
  * Enforced robust **VPC Endpoint Policies** to prevent data exfiltration risks and comply with stringent enterprise security standards.
