---
title: "Worklog Week 5"
date: 2026-10-05
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

**Duration:** 02/11/2026 → 06/11/2026  
**Topic:** CloudFront, Edge Computing & High Availability  
**Status:** Completed

### Objectives for Week 5:

* Deploy global content delivery infrastructure using Amazon CloudFront: multi-origin distribution, cache optimization (Cache Policies, TTLs), and origin hardening using Origin Access Control (OAC)
* Master Edge Computing architectures on AWS: compare and implement CloudFront Functions and Lambda@Edge across 4 event triggers (Viewer Request/Response, Origin Request/Response) for header manipulation, dynamic routing, and edge security
* Fortify application edge defenses using AWS WAF & AWS Shield: deploy Web ACLs, configure AWS Managed Rules, and implement rate-based rules against brute-force and DDoS attacks
* Architect and build highly available, fault-tolerant web applications: eliminate Single Points of Failure (SPOFs) via Multi-AZ topologies integrating Application Load Balancers (ALBs), Auto Scaling Groups (ASGs), and Amazon RDS Multi-AZ
* Master global traffic orchestration and Disaster Recovery (DR) strategies: configure advanced Route 53 routing policies and implement instant failover and network path optimization with AWS Global Accelerator

---

### Planned Tasks for This Week:

| Day | Task | Start Date | End Date | Resource Link |
| --- | --- | --- | --- | --- |
| Mon | - Overview of Amazon CloudFront global content delivery network: Points of Presence (Edge Locations), Regional Edge Caches, and latency reduction mechanics<br>- Deploy CloudFront Distributions serving static and dynamic content: integrate Amazon S3 origins and Custom origins (ALB/EC2)<br>- Secure origin access via Origin Access Control (OAC): migrate from legacy OAI, configure S3 Bucket Policies restricting access to `cloudfront.amazonaws.com` scoped by `AWS:SourceArn`<br>- Optimize caching performance: configure Cache Policies (Min/Default/Max TTL, Cache Keys), Origin Request Policies, automated compression (Gzip/Brotli), and create Cache Invalidations | 02/11/2026 | 02/11/2026 | <https://000094.awsfcaj.com/> |
| Tue | - Explore Edge Computing on AWS: deep-dive comparison between CloudFront Functions (sub-millisecond execution, lightweight) and Lambda@Edge (heavy compute, external network/IO access)<br>- Master the 4 CloudFront event triggers: Viewer Request, Origin Request, Origin Response, and Viewer Response<br>- Implement hands-on Lambda@Edge functions (Node.js/Python):<br>&nbsp;&nbsp;+ Route users dynamically based on geolocation headers (`CloudFront-Viewer-Country`)<br>&nbsp;&nbsp;+ Inject HTTP security headers (HSTS, CSP, X-Frame-Options, X-Content-Type-Options)<br>&nbsp;&nbsp;+ Customize URL rewriting and execute lightweight edge token/JWT validation | 03/11/2026 | 03/11/2026 | <https://000130.awsfcaj.com/> |
| Wed | - Enhance edge defense with AWS WAF (Web Application Firewall):<br>&nbsp;&nbsp;+ Explore Layer 7 application firewall principles protecting CloudFront distributions and Application Load Balancers<br>&nbsp;&nbsp;+ Provision a Web ACL and associate it directly with the CloudFront Distribution<br>&nbsp;&nbsp;+ Attach AWS Managed Rules (Core Rule Set - CRS, SQLi, XSS) and Amazon IP Reputation lists<br>&nbsp;&nbsp;+ Construct Custom Rules: rate-based rules preventing brute-force flooding and geographic access filtering (Geo-blocking)<br>&nbsp;&nbsp;+ Validate rules in Count mode prior to enforcing Block actions, and stream request logs to Amazon S3 | 04/11/2026 | 04/11/2026 | <https://000026.awsfcaj.com/> |
| Thu | - Building Highly Available Web Applications:<br>&nbsp;&nbsp;+ Architect fault-tolerant systems eliminating all Single Points of Failure (SPOFs)<br>&nbsp;&nbsp;+ Deploy a Multi-AZ VPC network layout: separate Public Subnets (ALB) and Private Subnets (App instances, Databases)<br>&nbsp;&nbsp;+ Configure Application Load Balancers (ALB) with comprehensive Health Checks to automatically reroute traffic away from degraded targets<br>&nbsp;&nbsp;+ Provision multi-AZ Auto Scaling Groups (ASG): build Launch Templates, dynamic scaling policies (CPU Target Tracking), and automated self-healing replacement<br>&nbsp;&nbsp;+ Deploy Amazon RDS Multi-AZ database instances with synchronous replication and automated failover | 05/11/2026 | 05/11/2026 | <https://000101.awsfcaj.com/> |
| Fri | - Global Traffic Management & Disaster Recovery (DR):<br>&nbsp;&nbsp;+ Explore intelligent DNS routing with Amazon Route 53: Latency-based Routing, Geolocation Routing, and Failover Routing driven by Route 53 Health Checks<br>&nbsp;&nbsp;+ Deploy AWS Global Accelerator: utilize 2 static Anycast IP addresses routing traffic over the AWS global backbone, achieving sub-second multi-region failover and lower jitter<br>&nbsp;&nbsp;+ Compare enterprise Disaster Recovery strategies: Backup & Restore, Pilot Light, Warm Standby, and Multi-Region Active/Active mapped against RTO and RPO objectives<br>- Week 5 wrap-up: end-to-end evaluation of CDN acceleration, edge compute, application security, and resilient high-availability architecture<br>- Clean up all created lab resources | 06/11/2026 | 06/11/2026 | <https://000101.awsfcaj.com/> |

---

### Key Outcomes for Week 5:

* **Accelerated Content Delivery & Origin Hardening with Amazon CloudFront:**
  * Developed deep comprehension of CDN edge caching, offloading traffic from origin servers, and reducing data egress expenses.
  * Successfully provisioned CloudFront distributions handling both S3 and Custom origins, mastering Cache Policies, Origin Request Policies, and modern compression algorithms.
  * Successfully deployed Origin Access Control (OAC) with SigV4 signing, strictly locking down S3 buckets to CloudFront access and eliminating direct public exposure.
* **Programmable Edge Processing with Lambda@Edge & CloudFront Functions:**
  * Mastered architectural boundaries between lightweight CloudFront Functions and compute-heavy Lambda@Edge runtimes.
  * Effectively utilized all 4 CloudFront lifecycle triggers (Viewer Request/Response, Origin Request/Response) to manipulate requests and responses near the user.
  * Successfully authored and deployed edge functions executing dynamic geo-redirection and injecting critical HTTP security headers directly at Points of Presence.
* **Application Layer Security with AWS WAF:**
  * Established robust Layer 7 security perimeters at the edge, protecting core VPC workloads from malicious attacks and request flooding.
  * Leveraged AWS Managed Rules to safeguard applications against OWASP Top 10 vulnerabilities without maintaining complex regex signatures.
  * Implemented rate-limiting rules preventing brute-force traffic spikes, verifying rule efficacy safely via Count mode before enforcing active Block rules.
* **Resilient High Availability Web Architecture:**
  * Architected and implemented a complete 3-tier Multi-AZ web application infrastructure, successfully eliminating any single points of failure.
  * Mastered dynamic traffic distribution via Application Load Balancers and automated elasticity/self-healing using Auto Scaling Groups.
  * Deployed highly available database tiers using Amazon RDS Multi-AZ, ensuring continuous operation and automated failover during zone-level disruptions.
* **Global Network Optimization & Disaster Recovery Readiness:**
  * Understood the operational and latency differences between DNS-level Route 53 failover (subject to TTL caching) and network-level AWS Global Accelerator failover (sub-second Anycast rerouting).
  * Evaluated enterprise disaster recovery topologies (Backup/Restore, Pilot Light, Warm Standby, Active/Active), mastering RTO/RPO trade-offs and cost implications.

