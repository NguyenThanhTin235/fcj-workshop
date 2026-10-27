---
title: "Week 1 Worklog"
date: 2026-10-05
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

**Period:** 05/10/2026 → 09/10/2026  
**Topic:** Onboarding, AWS Account, Budgets, Support, IAM & VPC  
**Status:** Completed

### Week 1 Objectives:

* Meet and connect with FCAJ members, understand internship rules and regulations
* Create a secure AWS Free Tier account, master credit strategy and cost management with AWS Budgets
* Explore technical support offerings with AWS Support Plans and AWS Trusted Advisor
* Manage identity and access control with AWS IAM (User, Group, Policy, Role, MFA)
* Understand cloud networking fundamentals and deploy a custom Amazon VPC

### Tasks to be carried out this week:
| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Meet and connect with FCAJ members<br>- Read and review internship rules and company regulations | 05/10/2026 | 05/10/2026 | |
| Tue | - Create AWS Free Tier account:<br>&nbsp;&nbsp;+ Strategy to obtain full $200 credit and complete 5 earning tasks<br>&nbsp;&nbsp;+ List of credit killers to avoid unexpected costs<br>- Cost management with AWS Budgets:<br>&nbsp;&nbsp;+ Create Cost Budget & Usage Budget<br>&nbsp;&nbsp;+ Set up Billing Alerts sent to email | 06/10/2026 | 06/10/2026 | <https://000001.awsstudygroup.com/> |
| Wed | - Explore AWS Support Plans:<br>&nbsp;&nbsp;+ Compare support tiers: Basic, Developer, Business, Enterprise<br>&nbsp;&nbsp;+ Open Support Cases & inspect account health with AWS Trusted Advisor<br>- Access management with AWS IAM:<br>&nbsp;&nbsp;+ Core concepts: IAM User, IAM Group, IAM Policy<br>&nbsp;&nbsp;+ Hands-on: Create Admin Group & Admin User<br>&nbsp;&nbsp;+ Enable Multi-Factor Authentication (MFA) | 07/10/2026 | 07/10/2026 | <https://000002.awsstudygroup.com/> |
| Thu | - Advanced permissions with IAM Role & Switch Role:<br>&nbsp;&nbsp;+ Create IAM Role and OperatorUser<br>&nbsp;&nbsp;+ Practice Switch Role from OperatorUser to Admin Role<br>&nbsp;&nbsp;+ Enforce Principle of Least Privilege<br>- Networking fundamentals with Amazon VPC:<br>&nbsp;&nbsp;+ Concepts: VPC, CIDR block, Public Subnet vs Private Subnet<br>&nbsp;&nbsp;+ Route Table, Internet Gateway (IGW) & NAT Gateway<br>&nbsp;&nbsp;+ VPC Firewalls: Security Group (Stateful) vs Network ACLs (Stateless) | 08/10/2026 | 08/10/2026 | <https://000003.awsstudygroup.com/> |
| Fri | - Hands-on deployment of Amazon VPC network:<br>&nbsp;&nbsp;+ Create Custom VPC with IPv4 CIDR Block<br>&nbsp;&nbsp;+ Create Public Subnet & Private Subnet<br>&nbsp;&nbsp;+ Create Internet Gateway (IGW) and attach to VPC<br>&nbsp;&nbsp;+ Configure Route Table routing traffic to Internet via IGW<br>&nbsp;&nbsp;+ Create Security Group allowing HTTP/SSH traffic<br>- Review Week 1 architecture: Account → Budgets → Support → IAM → VPC<br>- Clean up lab resources | 09/10/2026 | 09/10/2026 | <https://000003.awsstudygroup.com/> |

### Expected Week 1 Outcomes:

* **Workplace Integration & Regulations:** Successfully completed the onboarding process at First Cloud Journey (FCAJ); thoroughly understood company policies, information security standards, working schedules, and the overall internship training roadmap and deliverables.
* **AWS Account Setup & Cost Governance:**
  * Successfully registered and activated a personal AWS account under the AWS Free Tier program.
  * Mastered the strategy to acquire the full $200 AWS credit allowance and identified critical "credit killers" to proactively prevent unexpected cloud expenses.
  * Established automated AWS Budgets (Cost & Usage Budgets) with 80% and 100% threshold notifications delivered via email alerts.
* **Technical Support & Account Health Auditing:**
  * Understood the operational scope of AWS Support Plans (Basic, Developer, Business, Enterprise) and mastered submitting and managing Support Cases via AWS Support Center.
  * Utilized AWS Trusted Advisor to assess account posture across core pillars: Cost Optimization, Performance, Security, Fault Tolerance, and Service Limits.
* **Identity and Access Management (AWS IAM):**
  * Mastered core IAM building blocks: Users, Groups, Policies, Roles, and permission boundary mechanisms.
  * Implemented the Principle of Least Privilege by creating an Admin Group and non-root Admin User for daily operations, minimizing direct root account usage.
  * Enforced Multi-Factor Authentication (MFA) using virtual authenticator apps across both root and IAM user identities.
  * Configured IAM Roles and executed Switch Role operations from OperatorUser to Admin Role, gaining hands-on insight into temporary security credentials.
* **Cloud Networking Architecture (Amazon VPC):**
  * Acquired solid understanding of AWS networking concepts: IPv4 CIDR blocks, Public Subnets (Internet-facing), and Private Subnets (isolated workloads).
  * Successfully architected and deployed a Custom VPC across multiple Availability Zones (AZs) for high availability.
  * Attached an Internet Gateway (IGW) and configured Route Tables to properly direct outbound and inbound internet traffic.
  * Differentiated and applied the two layers of VPC firewalls: Security Groups (Stateful host-level inspection) and Network ACLs (Stateless subnet-level filtering).
  * Validated end-to-end network reachability, establishing a solid foundation for deploying compute and database resources in upcoming weeks.
