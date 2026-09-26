# Domain 1: Cloud Concepts (24%)

This domain covers why organizations use AWS, how AWS defines a well-designed workload, how organizations plan and carry out a migration, and the financial case for the cloud. Most questions give a short scenario and ask you to name the benefit, pillar, strategy, or cost concept it describes.

## 1.1 Define the benefits of the AWS Cloud

- **Value proposition:** on-demand resources with pay-as-you-go pricing replace buying and running your own hardware.
- **Six advantages** (map scenarios to these): fixed expense becomes variable expense, economies of scale, stop guessing capacity, speed and agility, stop running data centers, go global in minutes.
- **CapEx to OpEx:** upfront hardware purchases become a metered bill. Cues: "no large initial investment", "pay only for what you use".
- **Economies of scale:** aggregated customer usage lowers AWS unit costs, which reach you as lower prices. Cue: "lower variable costs because usage is aggregated". It explains why the price is low, not how you scale.
- **Global infrastructure:**
  - Region = a geographic area containing multiple AZs.
  - AZ = one or more discrete data centers with independent power, cooling, and networking.
  - Edge locations cache content near users (CloudFront).
  - Benefits: **speed of deployment** (a new geography in minutes, not months) and **global reach** (low latency worldwide). Isolated Regions also help with data residency and disaster recovery.

| Term | Means | Exam cue |
|---|---|---|
| Scalability | The design can grow (vertically or horizontally) | "handle growth", no mention of automation |
| Elasticity | Resources are added **and removed** automatically as demand changes | "fluctuating/spiky demand", "pay only for capacity used" |
| High availability | The system keeps running when components fail (redundancy across AZs plus failover) | "data center failure", "minimal downtime" |
| Agility | The business can experiment and ship faster | "time to market", "cheap to try and discard" |

- **Traps:**
  - Elasticity that only scales up is wrong. It must also scale down.
  - HA handles *failure*. Elasticity handles *demand*.
  - Agility describes the organization, not a running system.

📖 Full lesson: [Benefits of the AWS Cloud: Value Proposition, Elasticity & Global Reach](https://www.savemycert.com/revision/aws-cloud-practitioner/benefits-of-the-aws-cloud/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

## 1.2 Identify design principles of the AWS Cloud

- **Well-Architected Framework** = best-practice guidance in **six pillars** (design principles plus best practices). It is documentation, not a service. Sustainability became the sixth pillar in late 2021, so "five pillars" is out of date.
- **Well-Architected Tool** = a free console service that reviews a workload, flags high-risk issues, and produces an improvement plan. **Lenses** extend reviews to workload types such as serverless.

| Pillar | Goal | Trigger words | Typical services |
|---|---|---|---|
| Operational excellence | Run, observe, and improve operations | operations as code, runbooks, small reversible changes, game days, post-incident review | CloudFormation, CloudWatch, Systems Manager, Config |
| Security | Protect data, systems, and identities | least privilege, MFA, encryption, traceability, defense in depth | IAM, KMS, CloudTrail, GuardDuty, WAF, Shield |
| Reliability | Work correctly and recover from failure | failover, Multi-AZ, backup/restore, DR, self-healing | ELB, Route 53 health checks, Auto Scaling, RDS Multi-AZ, AWS Backup |
| Performance efficiency | Use the right resources efficiently | latency, resource selection, caching, serverless, experiment | Lambda, CloudFront, ElastiCache, purpose-built databases |
| Cost optimization | Deliver value at the lowest price | reduce spend, right-size, idle resources, cost allocation tags | Cost Explorer, Budgets, Savings Plans, Spot, S3 lifecycle |
| Sustainability | Reduce environmental impact | energy, carbon, maximize utilization, efficient hardware | Graviton, serverless, managed services |

- **Method:** find the stated *goal* first and use the services only to confirm it. The same service (Auto Scaling, S3 lifecycle) can support several pillars.
- **Confusions:**
  - Reliability vs performance efficiency: is something failing? If yes, reliability. If it works but is slow or badly matched, performance efficiency.
  - Cost optimization vs operational excellence: measured in money, or in process quality?
  - Security vs reliability: protection from attackers and data exposure, or from component failure? Encrypting a DB is security. Replicating it across AZs is reliability.
  - Cost optimization vs sustainability: right-sizing belongs to either one. "Lower the bill" means cost. "Lower energy/carbon" means sustainability.
- **Shared responsibility for sustainability:** AWS handles sustainability *of* the cloud, and customers handle it *in* the cloud.

📖 Full lesson: [AWS Well-Architected Framework: The Six Pillars Explained for CLF-C02](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-well-architected-framework-pillars/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

## 1.3 Understand the benefits of and strategies for migration to the AWS Cloud

- **First find the level:** organizational readiness or outcomes means CAF, a per-application decision means a 7 R, and moving bytes means DMS or Snowball.
- **CAF perspectives (6)**, which are work areas:
  - Business side: **Business, People, Governance**
  - Technical side: **Platform, Security, Operations** (mnemonic B-P-G / P-S-O)
  - People covers skills, training, and culture. Governance covers risk, program management, and cloud financial management. Platform covers building the environment.
- **CAF benefits (4)**, which are outcomes:
  - Reduced business risk
  - Improved ESG performance
  - Increased revenue
  - Increased operational efficiency
- **Trap:** a benefit starts with *reduced / improved / increased*, and a perspective is a single noun. "Operations" is not "increased operational efficiency", and "Governance" is not ESG.
- **CAF transformation phases:** Envision, Align, Launch, Scale. You only need to recognize the names.

| Strategy | One-line meaning |
|---|---|
| Rehost | Lift and shift with no code changes (e.g. VMs to EC2 using Application Migration Service) |
| Replatform | A small optimization with no redesign (e.g. self-managed MySQL to RDS) |
| Refactor / re-architect | Rebuild as cloud-native (microservices, serverless) |
| Repurchase | Replace with a different product, usually SaaS |
| Relocate | Move VMware workloads without changing how you operate them (VMware Cloud on AWS) |
| Retain | Keep it where it is for now |
| Retire | Decommission it |

- Retain and retire are the only two strategies where nothing moves to AWS, and exams often pair them as distractors.
- **AWS DMS:** migrates a database while the source stays live, using continuous replication until cutover. It handles homogeneous (same engine) and heterogeneous (different engine, needs schema conversion, see AWS SCT) migrations. Cue: "production database, minimal downtime".
- **AWS Snowball:** a physical device that AWS ships to you. You load data locally, ship it back, and AWS imports it into S3. Choose it when the network would take too long, connectivity is poor, the move is a one-time bulk transfer, or the transfer would saturate the corporate link. Do not use it for ongoing sync (use DMS or DataSync for that).
- **Supporting resources:** track progress with **Migration Hub**, rehost servers with **Application Migration Service (MGN)**, find documented patterns in **Prescriptive Guidance**, get outside expertise from **AWS Partners**, and build a business case with **Migration Evaluator**.

📖 Full lesson: [AWS Cloud Adoption Framework & Migration Strategies: The 7 Rs, DMS, and Snowball](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-cloud-adoption-framework-migration-strategies/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

## 1.4 Understand concepts of cloud economics

- **Fixed vs variable:** if usage doubles, does the line item double? Yes means variable (on-demand compute, S3 GB-month, data transfer). No means fixed (hardware, data center rent, multi-year contracts). Classify by behavior, not location, because cloud commitments are fixed-like.
- **On-premises TCO** goes well beyond servers. It also covers facilities, power **and** cooling, network, licenses and support, hardware refresh, idle capacity, and **staff labor**, which is the item most often forgotten.
- **Migration eliminates** hardware, facilities, power, cooling, and physical maintenance. **What remains** is usage-based charges.
- **Licensing:**
  - **BYOL:** reuse licenses you already own. You pay AWS only for the infrastructure and remain responsible for compliance. Some licenses may require dedicated hardware. AWS License Manager tracks entitlements. Cue: "existing investment in licenses".
  - **License-included:** the license cost is bundled into the hourly price, so there is nothing to buy or audit. Cue: "avoid managing licenses".
- **Rightsizing:** match instance type and size to what the workload actually uses. Options are to downsize, switch to a better-fitting family, or terminate idle resources. It is an ongoing process, not a one-off. An oversized instance is overprovisioning billed by the hour.
- **Automation (CloudFormation):** templates cut manual labor and drift, speed up rebuilds, and make idle environments safe to delete because they can be recreated. Cue: "consistent, repeatable deployments at lower cost".
- **Managed services** (AWS handles patching, backups, failover): **RDS** is relational and you still pick an instance size, **ECS** is AWS container orchestration, **EKS** is managed Kubernetes, and **DynamoDB** is serverless NoSQL with no instances.
- **TCO trap:** a managed service can cost more per hour than running the same software on EC2 and still be cheaper overall once you count staff time and downtime. Cues like "reduce operational overhead" or "minimize administrative effort" point to the managed option. Choose self-managed on EC2 when you need OS access or unsupported extensions.

📖 Full lesson: [AWS Cloud Economics: CapEx vs OpEx, TCO, and Managed Services (CLF-C02)](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-cloud-economics-fundamentals/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

[← Back to the study guide](../README.md)
