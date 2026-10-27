---
title: "Event 1"
date: 2026-10-05
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

<h2 align="center">EVENT SUMMARY: FIRST CLOUD AI JOURNEY MEET UP</h2>

### Event Objectives

* Learn directly from experienced Tech Leads and enterprise engineers regarding Cloud and AI Agents in enterprise environments.
* Explore practical use cases: low-latency Vietnamese Voice AI, secure multi-account resource sharing in AWS Organizations, automated infrastructure pentesting via Security Agents, and cost optimization using MicroVMs on EC2 Spot.
* Expand professional networking with the AWS engineer community and fellow interns in the First Cloud AI Journey program.

### Speakers List

* **Kiet Tran** - Revve AI
* **Long Huynh** - Styl Solution
* **Thinh Nguyen** - Styl Solution
* **Xuan An** - Leader, AWS Student Builder Group HCMUTE
* **Khoa Kieu** - Tech Lead, ACB
* **Nghi Danh** - AWS Community Builder

### Key Highlights

#### Session 1: Hear, Think, Speak - Building a Vietnamese voice-AI contact center on AWS
* **Speaker:** Kiet Tran (Revve AI)
* Explored Voice AI architecture aimed at reducing latency down to ~1.8s for smooth, natural voice conversations.
* Live demonstration of an AI system initiating outbound phone calls to interview Cloud Engineer candidates in Vietnamese with natural intonation and instant interactions.

#### Session 2: AWS Resource Access Manager
* **Speaker:** Long Huynh (Styl Solution)
* Secure resource sharing strategies across accounts within AWS Organizations.
* Architectural approach for cost reduction, centralized network management, and tighter synergy between IAM policies and Service Control Policies (SCPs) to establish strict permission boundaries.

#### Session 3: AWS Pentest with AWS Continuum / Security Agent
* **Speaker:** Thinh Nguyen (Styl Solution)
* Early-stage infrastructure security evaluation: reviewing Terraform code and integrating directly into GitLab/GitHub PRs to catch flaws.
* Simulating real attacker behavior with Security Agents to perform automated pentesting on SIT/UAT environments before actual deployment.

#### Session 4: Amazon Bedrock AgentCore
* **Speaker:** Xuan An (Leader, AWS Student Builder Group HCMUTE)
* Comprehensive overview of two foundational pillars for taking AI Agents to production:
  * **Agent Runtime:** Running MicroVMs on EC2 Spot instances for significant cost savings.
  * **Memory System:** Layered memory architecture with synchronous Short-term memory and asynchronous Long-term memory to deeply retain user context.

#### Session 5: Kiro Crew
* **Speakers:** Khoa Kieu (Tech Lead, ACB) & Nghi Danh (AWS Community Builder)
* Running autonomous AI Agents 24/7 to support code reviews and continuous system health checks.
* Artifact Generation: AI Agent scrapes real-time recruitment data and renders visual statistical charts directly inside the conversation thread.
* Context Window Governance: Auto Compact mechanism triggered when context utilization reaches 70% - 90%, paired with Break down context functionality to analyze token consumption per component.
* Memory Management & Guardrails: Routine eviction of stale memories to prevent cost runaway, alongside strict security guardrails preventing AI from modifying infrastructure or exposing server secrets.

### Experience at the Event

Attending the First Cloud AI Journey meet up at Bitexco was a deeply rewarding experience:

* **Open learning environment:** Directly engaged with real-world challenges and technical solutions deployed at financial institutions and technology enterprises such as ACB, Styl Solution, and Revve AI.
* **Engaging technical discussions:** The closing Q&A session addressed technical nuances regarding context management, memory lifecycles, and enterprise guardrails in large-scale systems.
* **Professional networking:** Connected with seasoned industry leaders, alumni interns, and peers with similar career aspirations.

### Results Achieved

* Gained a holistic view of deploying production AI Agents and cloud infrastructure in enterprise settings.
* Deepened understanding of context window management, layered memory design (Short-term/Long-term), and security guardrail enforcement.
* Acquired knowledge on secure multi-account governance via AWS RAM and SCPs, alongside shift-left automated security pipelines in CI/CD.
* Mastered practical techniques to optimize operational costs for 24/7 AI workloads using MicroVMs on EC2 Spot instances.

### Lessons Learned

* **Production-First Mindset:** The gap between a Proof of Concept (PoC) and a production-grade system is substantial, requiring rigorous attention to real-time latency, operating costs, and stringent security boundaries.
* **Cost Optimization Strategy:** High-end instances are not always necessary; orchestrating EC2 Spot instances, MicroVMs, and routine memory hygiene significantly minimizes costs while maintaining reliability.
* **Security by Design:** Always enforce least-privilege principles and integrate automated security checks early into the CI/CD development pipeline (Shift-left security) to remediate vulnerabilities at the Pull Request stage.
* **Active Networking & Continuous Learning:** Participating in community events and engaging with experienced practitioners broadens technical perspectives, accelerates technology adoption, and provides clearer career guidance.

### Event Photos

![Check-in at First Cloud AI Journey Meet Up](/images/event1/event1-checkin.jpg)
<p align="center"><em>Check-in attending the First Cloud AI Journey meet up at Bitexco</em></p>

![Three ways to build a Voice Agent](/images/event1/event1-voice-ai-methods.jpg)
<p align="center"><em>Session 1: Three ways to build a Voice Agent (Cascade, Speech-to-Speech, Full-duplex S2S)</em></p>

![Revve on AWS Architecture](/images/event1/event1-revve-architecture.jpg)
<p align="center"><em>Detailed Voice-AI Contact Center system architecture on AWS (EKS, Amazon Bedrock, ElastiCache, RDS)</em></p>

![Event space and presentation overview](/images/event1/event1-presentation-overview.jpg)
<p align="center"><em>Overview of the technical session presentation at AWS office (Bitexco Financial Tower)</em></p>
