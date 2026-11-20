---
title: "Worklog Week 7"
date: 2026-10-05
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

**Duration:** 16/11/2026 → 20/11/2026  
**Topic:** Remote Server Access with Systems Manager Session Manager & Infrastructure as Code (CloudFormation, AWS CDK)  
**Status:** Completed

### Objectives for Week 7:

* Securely access public and private EC2 instances without SSH keys or bastion hosts using AWS Systems Manager Session Manager, VPC Endpoints, S3 session logging, and Port Forwarding
* Provision, manage, and detect drift on AWS infrastructure declaratively using AWS CloudFormation (templates, Custom Resources with Lambda, Mappings, StackSets)
* Build, update, and deploy cloud infrastructure programmatically in TypeScript/Python using AWS CDK (Essentials & Advanced: ECS/ALB/API Gateway, Lambda/S3, and Nested Stacks)

---

### Planned Tasks for This Week:

| Day | Task | Start Date | End Date | Resource Link |
| --- | --- | --- | --- | --- |
| Mon | - Set up VPC, public/private subnets, Security Groups, Linux/Windows EC2 instances, and IAM Role for SSM<br>- Connect to public and private EC2 instances via Session Manager using VPC Endpoints (`ssm`, `ssmmessages`, `ec2messages`)<br>- Configure S3 session logging via S3 Gateway Endpoint, test Port Forwarding, and clean up resources | 16/11/2026 | 16/11/2026 | <https://000058.awsfcaj.com/> |
| Tue | - Create IAM User and launch AWS CloudShell to write and deploy basic CloudFormation templates<br>- Implement Advanced CloudFormation: Custom Resources backed by AWS Lambda, Mappings, and StackSets<br>- Practice Drift Detection to identify out-of-band infrastructure changes and clean up stacks | 17/11/2026 | 17/11/2026 | <https://000037.awsfcaj.com/> |
| Wed | - Set up local CDK workspace and AWS CloudShell environment for AWS CDK Essentials<br>- Initialize CDK project, understand constructs/stacks, and create initial CDK template | 18/11/2026 | 18/11/2026 | <https://000038.awsfcaj.com/> |
| Thu | - Synthesize CloudFormation templates (`cdk synth`), deploy (`cdk deploy`), and update CDK stacks (`cdk diff` / `cdk deploy`)<br>- Clean up CDK Essentials resources and review IaC best practices | 19/11/2026 | 19/11/2026 | <https://000038.awsfcaj.com/> |
| Fri | - Prepare IAM Role, EC2 instance, and VSCode Remote development environment for AWS CDK Advanced<br>- Build multi-service architectures with CDK: ECS + ALB + API Gateway, Lambda + S3, and Nested Stacks<br>- Week 7 wrap-up and clean up all remaining stacks and lab resources | 20/11/2026 | 20/11/2026 | <https://000076.awsfcaj.com/> |

---

### Key Outcomes for Week 7:

* **Secure Remote Access (AWS Systems Manager Session Manager):**
  * Accessed EC2 instances in private subnets without opening inbound SSH/RDP ports or managing bastion hosts and key pairs.
  * Configured VPC Interface Endpoints (`ssm`, `ssmmessages`, `ec2messages`) and S3 Gateway Endpoint for private session connectivity and centralized S3 audit logging, plus Port Forwarding.
* **Infrastructure as Code with AWS CloudFormation:**
  * Authored and deployed declarative CloudFormation templates via CloudShell, extending capabilities with Lambda-backed Custom Resources.
  * Managed multi-region/multi-account deployments with Mappings and StackSets, and verified configuration consistency using Drift Detection.
* **Programmatic IaC with AWS CDK (Essentials & Advanced):**
  * Bootstrapped and managed CDK projects using `cdk synth`, `cdk diff`, and `cdk deploy` workflows.
  * Composed higher-level constructs for containerized workloads (ECS, ALB, API Gateway), serverless integrations (Lambda, S3), and modular Nested Stacks.
