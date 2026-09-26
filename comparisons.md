# CLF-C02 Commonly Confused Services and Concepts

Side-by-side comparisons of the CLF-C02 services and ideas that exam questions most often set against each other. Each table ends with the one thing to remember.

- [Domain 1: Cloud Concepts](#domain-1-cloud-concepts)
- [Domain 2: Security and Compliance](#domain-2-security-and-compliance)
- [Domain 3: Cloud Technology and Services](#domain-3-cloud-technology-and-services)
- [Domain 4: Billing, Pricing, and Support](#domain-4-billing-pricing-and-support)

## Domain 1: Cloud Concepts

### Elasticity vs Scalability vs High availability

| | Elasticity | Scalability | High availability |
|---|---|---|---|
| What it is | Capacity added and removed automatically to follow demand | The ability of a design to grow to handle more load | The ability to keep running when components fail |
| What it responds to | Changes in demand, in both directions | Growth | Failure |
| How it is achieved | Automatic scaling of fleets | Bigger resources (vertical) or more resources (horizontal) | Redundancy across AZs with automatic failover |
| Exam cue | "Spiky or unpredictable traffic, pay only for what is used" | "Handle growth without redesign" | "Data center outage with minimal downtime" |

**Remember:** elasticity must shrink as well as grow, and HA is about failure, not load.

### CAF perspectives vs CAF benefits

| | Perspectives (6) | Benefits (4) |
|---|---|---|
| What it is | Capability areas the organization must develop | Business outcomes that adoption delivers |
| Items | Business, People, Governance, Platform, Security, Operations | Reduced business risk, improved ESG performance, increased revenue, increased operational efficiency |
| Wording | A single functional noun | Starts with reduced / improved / increased |
| Exam cue | "Retrain staff", "define risk controls", "build the landing zone" | "Fewer outages", "carbon reporting", "enter new markets", "ship features faster" |

**Remember:** if the option has a change verb, it is a benefit. "Operations" is a perspective, and "increased operational efficiency" is a benefit.

### Rehost vs Replatform vs Refactor

| | Rehost | Replatform | Refactor |
|---|---|---|---|
| What it is | Move as-is ("lift and shift") | Move with a few targeted optimizations | Redesign as cloud-native |
| Code or architecture change | None | Minor, and the core architecture is unchanged | Significant |
| Use it when | Speed matters and you want the least change risk | You want managed-service wins without a rewrite | The current design cannot deliver the scale or features you need |
| Example | VMs to EC2 using Application Migration Service | Self-managed MySQL to Amazon RDS | Monolith to Lambda-based microservices |
| Exam cue | "No changes", "as quickly as possible" | "Take advantage of a managed service" | "Microservices", "serverless", "re-architect" |

**Remember:** effort and cloud benefit both increase from rehost to replatform to refactor.

### Reliability vs Performance efficiency (Well-Architected pillars)

| | Reliability | Performance efficiency |
|---|---|---|
| What it is | Working correctly and recovering from failure | Using the right resources efficiently while healthy |
| Core question | "Will it survive when something breaks?" | "Is this the fastest, best-fitting way to run it?" |
| Typical practices | Multi-AZ, failover, backups, self-healing | Caching, CDN, serverless, choosing instance or database types |
| Exam cue | "Even if an AZ becomes unavailable" | "Users complain of slow page loads" |

**Remember:** if the scenario mentions failure or an outage, choose reliability. If it is only about speed or fit, choose performance efficiency.

## Domain 2: Security and Compliance

### Security Groups vs Network ACLs

| | Security group | Network ACL |
|---|---|---|
| What it is | Virtual firewall on an instance's network interface | Traffic filter on a subnet boundary |
| State | Stateful: replies are allowed automatically | Stateless: replies need a matching rule in the other direction |
| Rules | Allow only | Allow and deny, processed in number order |
| Use it when | Controlling which ports and sources can reach one resource | Applying a subnet-wide guardrail or blocking an IP range |
| Exam cue | "stateful", "instance level", "reference another security group" | "stateless", "subnet level", "deny a specific IP" |

**Remember:** if the question needs an explicit deny, it's a NACL. Security groups can only allow.

### GuardDuty vs Inspector vs Security Hub

| | Amazon GuardDuty | Amazon Inspector | AWS Security Hub |
|---|---|---|---|
| What it is | Threat detection | Vulnerability management | Findings aggregator and posture dashboard |
| Looks at | CloudTrail events, VPC Flow Logs, DNS logs | EC2 instances, ECR container images, Lambda functions | Findings from GuardDuty, Inspector, Macie, and partner tools |
| Use it when | You want to spot attacks or compromised credentials in progress | You want to find unpatched CVEs or unintended network exposure | You want one view of all security findings across accounts |
| Exam cue | "malicious activity", "compromised account" | "scan for vulnerabilities", "CVEs" | "single pane of glass", "aggregate findings" |

**Remember:** GuardDuty finds attacks, Inspector finds weaknesses, and Security Hub collects what the other two find.

### CloudTrail vs CloudWatch vs Config

| | AWS CloudTrail | Amazon CloudWatch | AWS Config |
|---|---|---|---|
| What it is | Record of API calls and account activity | Metrics, logs, dashboards, and alarms | History of resource configuration, evaluated against rules |
| Question it answers | Who did what, when, and from where? | How is the resource performing? | What does the resource look like now and before, and is it compliant? |
| Use it when | Investigating who deleted or changed something | Alerting on CPU, latency, or error thresholds | Flagging a bucket that turns public or a volume left unencrypted |
| Exam cue | "audit API activity", "which user" | "monitor", "alarm", "metrics" | "configuration history", "noncompliant resources" |

**Remember:** CloudTrail records the action, Config records the state that results, and CloudWatch records performance.

### AWS Artifact vs AWS Audit Manager

| | AWS Artifact | AWS Audit Manager |
|---|---|---|
| What it is | Portal for AWS's own compliance reports and agreements | Automated evidence collection mapped to control frameworks |
| Whose compliance | AWS's (the underlying infrastructure) | Yours (your accounts and workloads) |
| Use it when | An auditor asks for AWS's SOC or PCI report, or you need to accept a BAA | You are preparing your organization's own audit |
| Exam cue | "download compliance reports", "agreements with AWS" | "automate audit evidence", "assessment reports" |

**Remember:** Artifact gives you AWS's finished audit reports. Audit Manager builds evidence for your own audit.

### AWS Shield vs AWS WAF

| | AWS Shield | AWS WAF |
|---|---|---|
| What it is | DDoS protection service | Layer-7 web application firewall |
| Stops | Floods of traffic meant to overwhelm a service | Malicious request content such as SQL injection and cross-site scripting |
| Tiers / setup | Standard is automatic and free. Advanced is paid and adds a response team. | You create web ACLs, optionally with managed rule groups, on CloudFront, ALB, or API Gateway |
| Exam cue | "DDoS" | "SQL injection", "XSS", "filter HTTP requests" |

**Remember:** Shield protects against volume attacks, and WAF inspects what each request contains.

## Domain 3: Cloud Technology and Services

### Regions vs Availability Zones vs edge locations

| | Region | Availability Zone | Edge location |
| --- | --- | --- | --- |
| What it is | A geographic area holding several isolated AZs | One or more data centers with independent power, cooling, and networking | A site in a city close to users, far more numerous than Regions |
| Hosts your workloads? | Yes; you choose it for every resource | Yes; you spread resources across several | No; it runs CloudFront caches and Global Accelerator entry points |
| Use it when | Disaster recovery, distant users, or data-residency rules | You need high availability within one Region | You want lower latency without deploying to more Regions |
| Exam cue | "data must stay in the country", "regional outage" | "survive a data-center failure" | "cache content near users", "hundreds of locations" |

**Remember:** AZs give availability, Regions give sovereignty, latency, and DR, and the edge gives delivery.

### EC2 vs Lambda vs Fargate

| | Amazon EC2 | AWS Lambda | AWS Fargate |
| --- | --- | --- | --- |
| What it is | Virtual servers with OS-level control | Functions invoked by events | Serverless engine that runs containers for ECS or EKS |
| Who manages servers | You (OS patching, sizing, scaling) | AWS | AWS |
| Runtime pattern | Long-running, always on | Short runs, capped at 15 minutes | Containers of any duration |
| Use it when | Custom OS, host software, lift-and-shift | Event-driven glue, file processing, light APIs | Containerized apps with no hosts to manage |
| Exam cue | "full control of the operating system" | "runs only when a file is uploaded" | "containers without managing servers" |

**Remember:** Lambda runs functions, Fargate runs containers, and EC2 runs whatever you install.

### RDS vs Aurora vs DynamoDB

| | Amazon RDS | Amazon Aurora | Amazon DynamoDB |
| --- | --- | --- | --- |
| What it is | Managed relational engines (MySQL, PostgreSQL, MariaDB, SQL Server, Oracle, Db2) | AWS-built relational engine, MySQL- and PostgreSQL-compatible | Serverless NoSQL key-value and document store |
| Schema and queries | Fixed schema, SQL, joins, transactions | Same as RDS | Flexible schema, key-based access |
| Scaling | Larger instances; read replicas for reads | Storage copied across three AZs; Aurora Serverless adjusts capacity | Scales out automatically; no instances at all |
| Use it when | An existing SQL app, or an engine Aurora lacks | MySQL/PostgreSQL workloads that need more performance | Massive scale with consistent millisecond latency |
| Exam cue | "SQL Server", "Oracle", "managed relational" | "MySQL-compatible, higher performance" | "key-value", "single-digit millisecond at any scale" |

**Remember:** Relational data with joins goes to RDS or Aurora; key-value data at any scale goes to DynamoDB.

### S3 vs EBS vs EFS

| | Amazon S3 | Amazon EBS | Amazon EFS |
| --- | --- | --- | --- |
| Storage type | Object | Block | File (NFS) |
| Accessed by | Any client over HTTPS/API | One EC2 instance in one AZ | Thousands of Linux instances across AZs at once |
| Capacity | No provisioning; pay for what you store | Sized when you create the volume | Grows and shrinks automatically |
| Use it when | Backups, static sites, data lakes, media | Boot volumes, databases on EC2 | Shared content, home directories |
| Exam cue | "store millions of objects", "static website" | "low-latency disk for an instance" | "multiple instances need the same files" |

**Remember:** Use S3 for API-accessed objects, EBS for one instance's disk, and EFS for files shared by many instances.

### S3 Standard-IA vs One Zone-IA vs Glacier Deep Archive

| | Standard-IA | One Zone-IA | Glacier Deep Archive |
| --- | --- | --- | --- |
| Access pattern | Infrequent, but needed immediately | Infrequent and easy to re-create | Almost never; long-term retention |
| Retrieval | Milliseconds | Milliseconds | Hours (typically up to 12) |
| Resilience | Multiple AZs | Single AZ; an AZ loss can destroy the data | Multiple AZs |
| Exam cue | "rarely accessed, needed instantly" | "easily reproduced", "secondary copy" | "compliance retention for years", "cheapest" |

**Remember:** Choose the class by retrieval time and by whether the data can be re-created, and use Intelligent-Tiering when the access pattern is unknown.

### CloudFront vs Global Accelerator

| | Amazon CloudFront | AWS Global Accelerator |
| --- | --- | --- |
| What it is | Content delivery network | Network-path accelerator with static anycast IPs |
| How it helps | Serves cached copies from a nearby edge | Moves user traffic onto the AWS backbone at the nearest edge |
| Traffic | HTTP/HTTPS content, static and dynamic | Any TCP or UDP app, even traffic that cannot be cached |
| Exam cue | "CDN", "cache", "stream video worldwide" | "static IP addresses", "gaming", "VoIP" |

**Remember:** CloudFront caches content, and Global Accelerator speeds up connections.

### Site-to-Site VPN vs Direct Connect

| | AWS Site-to-Site VPN | AWS Direct Connect |
| --- | --- | --- |
| What it is | IPsec-encrypted tunnel over the public internet | Dedicated private physical connection |
| Setup time | Hours to days | Weeks or longer |
| Cost | Lower | Higher |
| Performance | Varies with internet conditions | Consistent, predictable |
| Encryption | Always | Not by itself; add a VPN or TLS on top |
| Exam cue | "set up a secure connection quickly" | "must not traverse the public internet" |

**Remember:** Choose a VPN for speed and cost, and Direct Connect for consistency and a private path.

### SQS vs SNS vs EventBridge

| | Amazon SQS | Amazon SNS | Amazon EventBridge |
| --- | --- | --- | --- |
| Model | Queue (point-to-point) | Publish/subscribe topic | Event bus with rules |
| Delivery | Consumers pull | Pushed to every subscriber | Routed to targets whose rules match the event content |
| Receivers per message | One consumer | All subscribers | Every matching target |
| Use it when | Decoupling and buffering spikes | Broadcasting alerts (email, SMS, push, Lambda, SQS) | Reacting to events from AWS services, SaaS apps, or your code |
| Exam cue | "decouple", "buffer requests" | "notify", "fan out" | "event-driven", "SaaS events" |

**Remember:** SQS holds messages for one worker, SNS broadcasts to all subscribers, and EventBridge routes by content; SNS feeding several SQS queues is the fan-out pattern.

## Domain 4: Billing, Pricing, and Support

### On-Demand vs Reserved Instances vs Savings Plans vs Spot

| | On-Demand | Reserved Instances | Savings Plans | Spot Instances |
| --- | --- | --- | --- | --- |
| What it is | Pay the standard rate for what runs | 1- or 3-year discount tied to instance attributes | 1- or 3-year discount tied to an hourly spend | Spare EC2 capacity that AWS can reclaim |
| Commitment | None | Term plus instance type, Region, platform, and tenancy | Term plus $/hour of compute | None, but you accept interruption |
| Flexibility | Total | Low (Standard) or exchangeable (Convertible) | High; the Compute type also covers Fargate and Lambda | High, but capacity is not guaranteed |
| Use it when | Usage is unpredictable, short-term, or new | A known instance footprint runs all the time | Spend is steady but the architecture may change | The job can stop and restart without harm |
| Exam cue | "cannot commit", "testing a new app" | "steady state", "runs for years" | "flexible", "change Regions", "Lambda/Fargate" | "fault-tolerant", "batch", "lowest cost" |

**Remember:** commitment buys discount, interruption tolerance buys the biggest discount, and paying nothing up front buys freedom.

### Dedicated Host vs Dedicated Instance vs Capacity Reservation

| | Dedicated Host | Dedicated Instance | Capacity Reservation |
| --- | --- | --- | --- |
| What it is | An entire physical server assigned to you | Your instances on hardware no other customer uses | Reserved EC2 capacity in one AZ |
| Host visibility | Sockets, cores, and placement | None | Not applicable |
| Discount | None (the costliest option) | None | None by itself; can combine with Savings Plans or regional RIs |
| Use it when | BYOL licenses are bound to physical cores or sockets | You need isolation but not host control | Capacity must exist for DR or a planned event |
| Exam cue | "per-socket license", "physical server" | "not shared with other customers" | "ensure capacity", "any duration" |

**Remember:** a Host gives you control, an Instance gives you isolation, and a Reservation gives you guaranteed capacity. None of them gives you a discount on its own.

### Pricing Calculator vs Budgets vs Cost Explorer vs Cost and Usage Report

| | Pricing Calculator | AWS Budgets | Cost Explorer | Cost and Usage Report |
| --- | --- | --- | --- | --- |
| What it is | Estimator built on public prices | Threshold monitor with alerts | Interactive charts of your past spend | Raw line-item billing data in S3 |
| Timing | Before you build | While you spend | After you spend (plus forecasts from history) | After you spend, at the finest detail |
| Needs your account data | No, and no account is required | Yes | Yes | Yes |
| Use it when | Pricing a migration or comparing designs | Warning a team before it overspends | Finding which service or team drove costs | Feeding chargeback or custom analytics (Athena, QuickSight) |
| Exam cue | "estimate" | "alert", "notify", "forecasted threshold" | "visualize", "trends" | "most detailed", "granular" |

**Remember:** estimate before, alert during, analyze after, and use the CUR when you need every line item.

### Consolidated billing vs AWS Billing Conductor

| | Consolidated billing | AWS Billing Conductor |
| --- | --- | --- |
| What it is | One real bill for all accounts in AWS Organizations | Custom pro-forma billing views for groups of accounts |
| Changes what AWS charges | Yes, because pooled usage and shared discounts can lower it | No |
| Use it when | You want one invoice, volume tiers, and shared RI/Savings Plans discounts | You resell AWS or run chargeback at custom rates |
| Exam cue | "single bill", "multiple accounts" | "reseller", "custom rates", "margin" |

**Remember:** consolidated billing produces the actual bill, while Billing Conductor only changes the version your customers or teams see.

### Business vs Enterprise On-Ramp vs Enterprise Support

| | Business | Enterprise On-Ramp | Enterprise |
| --- | --- | --- | --- |
| Workload focus | Production | Production and business-critical | Mission-critical |
| Access | 24/7 phone, email, chat | 24/7 phone, email, chat | 24/7 phone, email, chat |
| TAM | None | Shared pool | Designated to your account |
| Fastest response target (per lesson) | Production down under 1 hour | Business-critical down under 30 minutes | Business-critical down under 15 minutes |
| Extras | Full Trusted Advisor, Health API | Annual consultative review | Concierge Support Team, proactive programs such as Well-Architected reviews |
| Exam cue | "cheapest with 24/7 phone" | "any TAM access" | "designated TAM", "concierge" |

**Remember:** pick the cheapest plan that meets every stated requirement, and a "designated" TAM always points to Enterprise.

[← Back to the study guide](README.md)
