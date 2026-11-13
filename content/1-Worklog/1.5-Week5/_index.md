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

* Deploy Amazon CloudFront with S3/Custom origins, Cache Policies, and Origin Access Control (OAC)
* Implement Edge Computing using CloudFront Functions and Lambda@Edge across all 4 event triggers
* Secure edge traffic with AWS WAF Web ACLs, Managed Rules, and rate-based rules
* Build Multi-AZ High Availability web architectures with ALB, Auto Scaling Groups, and RDS Multi-AZ
* Orchestrate global traffic and Disaster Recovery with Route 53 and AWS Global Accelerator

---

### Planned Tasks for This Week:

| Day | Task | Start Date | End Date | Resource Link |
| --- | --- | --- | --- | --- |
| Mon | - Deploy CloudFront Distributions for S3 and Custom (ALB/EC2) origins across Edge Locations & Regional Edge Caches<br>- Configure Origin Access Control (OAC) with `AWS:SourceArn` S3 Bucket Policy, Cache/Origin Request Policies, Gzip/Brotli compression, and Cache Invalidations | 02/11/2026 | 02/11/2026 | <https://000094.awsfcaj.com/> |
| Tue | - Compare CloudFront Functions vs Lambda@Edge across 4 triggers (Viewer/Origin Request & Response)<br>- Implement Lambda@Edge (Node.js/Python) for `CloudFront-Viewer-Country` geo-routing, HTTP security headers (HSTS/CSP/X-Frame-Options), URL rewrites, and JWT validation | 03/11/2026 | 03/11/2026 | <https://000130.awsfcaj.com/> |
| Wed | - Provision AWS WAF Web ACL on CloudFront with AWS Managed Rules (CRS, SQLi, XSS, IP Reputation) and custom rate-based / geo-blocking rules<br>- Validate rules in Count mode before enforcing Block actions and stream logs to S3 | 04/11/2026 | 04/11/2026 | <https://000026.awsfcaj.com/> |
| Thu | - Eliminate SPOFs with a Multi-AZ VPC (Public Subnets for ALB, Private Subnets for App & DB)<br>- Deploy ALB with Health Checks, Multi-AZ Auto Scaling Group (Launch Templates, CPU Target Tracking), and RDS Multi-AZ with synchronous replication | 05/11/2026 | 05/11/2026 | <https://000101.awsfcaj.com/> |
| Fri | - Configure Route 53 Latency, Geolocation, and Failover routing; deploy AWS Global Accelerator (2 static Anycast IPs)<br>- Compare DR strategies (Backup & Restore, Pilot Light, Warm Standby, Active/Active) by RTO/RPO, wrap up Week 5, and clean up resources | 06/11/2026 | 06/11/2026 | <https://000101.awsfcaj.com/> |

---

### Key Outcomes for Week 5:

* **Amazon CloudFront & OAC:** Accelerated static/dynamic delivery with Cache Policies and Gzip/Brotli compression while locking S3 origins behind SigV4 OAC.
* **Edge Computing:** Built CloudFront Functions and Lambda@Edge handlers across all 4 lifecycle triggers for geo-routing, URL rewriting, and security header injection.
* **AWS WAF:** Protected Layer 7 endpoints using Managed Rules, rate-limiting, and geo-blocking validated in Count mode before enforcement.
* **Multi-AZ High Availability & DR:** Eliminated SPOFs with ALB + ASG + RDS Multi-AZ, and compared DNS-based Route 53 failover against sub-second Anycast Global Accelerator and enterprise RTO/RPO DR tiers.
