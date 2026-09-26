# CLF-C02 Study Guide: AWS Certified Cloud Practitioner

A free, open study guide for the **AWS Certified Cloud Practitioner (CLF-C02)** exam. It covers every domain and topic in the official exam guide as a checklist, lists the facts worth memorizing, and links each topic to a full free lesson.

Maintained by [SaveMyCert](https://www.savemycert.com/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide), where you can read every lesson free, [practice with explained questions](https://www.savemycert.com/practice/aws-cloud-practitioner/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide) and [take timed mock exams](https://www.savemycert.com/mocks/aws-cloud-practitioner/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide).

## Contents

- [Exam at a glance](#exam-at-a-glance)
- [Exam domains](#exam-domains)
- [Syllabus checklist](#syllabus-checklist)
  - [Domain 1: Cloud Concepts](#domain-1-cloud-concepts)
  - [Domain 2: Security and Compliance](#domain-2-security-and-compliance)
  - [Domain 3: Cloud Technology and Services](#domain-3-cloud-technology-and-services)
  - [Domain 4: Billing, Pricing, and Support](#domain-4-billing-pricing-and-support)
- [How to study for CLF-C02](#how-to-study-for-clf-c02)
- [Sample questions](sample-questions.md)
- [Free resources](#free-resources)

## Exam at a glance

| | |
|---|---|
| Exam code | CLF-C02 |
| Level | Foundational |
| Questions | 65 |
| Time limit | 90 min |
| Passing score | 700 / 1000 |
| Format | Multiple choice & response |
| Exam fee | $100 |
| Valid for | 3 years |

Exam details change. Always confirm them in the official [AWS Certified Cloud Practitioner (CLF-C02) exam guide](https://docs.aws.amazon.com/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02.html) from Amazon Web Services.

## Exam domains

| # | Domain | Weight | Topics |
|---|---|---|---|
| 1 | [Cloud Concepts](#domain-1-cloud-concepts) | 24% | 4 |
| 2 | [Security and Compliance](#domain-2-security-and-compliance) | 30% | 4 |
| 3 | [Cloud Technology and Services](#domain-3-cloud-technology-and-services) | 34% | 8 |
| 4 | [Billing, Pricing, and Support](#domain-4-billing-pricing-and-support) | 12% | 3 |

That is 4 domains and 19 topics. Spend your time in proportion to the weights: the heaviest domain decides more of your score than the lightest.

## Syllabus checklist

Tick each topic off once you can explain it without notes. The "Must know" facts are the ones questions turn on. Each lesson link goes to the complete, free lesson.

### Domain 1: Cloud Concepts

**Weight: 24%.** The AWS Cloud value proposition: benefits, Well-Architected design principles, migration strategies, and cloud economics.

- [ ] **1.1 Define the benefits of the AWS Cloud**
  <br>The AWS value proposition: economies of scale and cost savings; benefits of the global infrastructure (speed of deployment, global reach); and the advantages of high availability, elasticity, and agility.
  - 📖 Lesson: [Benefits of the AWS Cloud: Value Proposition, Elasticity & Global Reach](https://www.savemycert.com/revision/aws-cloud-practitioner/benefits-of-the-aws-cloud/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: The AWS value proposition: on-demand resources with pay-as-you-go pricing replace owning and operating your own hardware.
  - Must know: CapEx to OpEx: large upfront hardware investment becomes a variable expense that tracks actual usage.
- [ ] **1.2 Identify design principles of the AWS Cloud**
  <br>The AWS Well-Architected Framework: what each pillar covers — operational excellence, security, reliability, performance efficiency, cost optimization, and sustainability — and how the pillars differ from one another.
  - 📖 Lesson: [AWS Well-Architected Framework: The Six Pillars Explained for CLF-C02](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-well-architected-framework-pillars/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: The AWS Well-Architected Framework has exactly six pillars: operational excellence, security, reliability, performance efficiency, cost optimization, and sustainability
  - Must know: The AWS Well-Architected Tool is a free console service that reviews workloads against the framework and produces an improvement plan
- [ ] **1.3 Understand the benefits of and strategies for migration to the AWS Cloud**
  <br>Cloud adoption strategies and migration-support resources: benefits of the AWS Cloud Adoption Framework (reduced business risk, improved ESG performance, increased revenue, increased operational efficiency) and choosing appropriate migration strategies such as database replication and AWS Snowball.
  - 📖 Lesson: [AWS Cloud Adoption Framework & Migration Strategies: The 7 Rs, DMS, and Snowball](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-cloud-adoption-framework-migration-strategies/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: The AWS CAF has six perspectives: Business, People, Governance (business capabilities) and Platform, Security, Operations (technical capabilities).
  - Must know: The four CAF benefit categories are reduced business risk, improved ESG performance, increased revenue, and increased operational efficiency — outcomes, not perspectives.
- [ ] **1.4 Understand concepts of cloud economics**
  <br>Cloud economics: fixed vs variable costs, costs of on-premises environments, licensing strategies (BYOL vs included licenses), rightsizing, the cost benefits of automation (e.g. CloudFormation), and recognizing managed services (RDS, ECS, EKS, DynamoDB).
  - 📖 Lesson: [AWS Cloud Economics: CapEx vs OpEx, TCO, and Managed Services (CLF-C02)](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-cloud-economics-fundamentals/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: Moving to AWS trades upfront capital expense (CapEx) for pay-as-you-go operational expense (OpEx) — fixed costs become variable costs
  - Must know: A cost is variable if it rises and falls with usage; hardware purchases, data center rent, and facilities are fixed costs

### Domain 2: Security and Compliance

**Weight: 30%.** The shared responsibility model, AWS security and governance concepts, identity and access management, and security resources.

- [ ] **2.1 Understand the AWS shared responsibility model**
  <br>Recognizing the components of the shared responsibility model: what the customer is responsible for, what AWS is responsible for, what is shared, and how responsibilities shift depending on the service used (e.g. EC2 vs RDS vs Lambda).
  - 📖 Lesson: [AWS Shared Responsibility Model: Security OF the Cloud vs IN the Cloud](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-shared-responsibility-model/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: AWS is responsible for security OF the cloud (facilities, hardware, network, hypervisor); the customer is responsible for security IN the cloud (data, access, configuration).
  - Must know: Customer data, IAM permissions, and encryption choices are ALWAYS the customer's responsibility, on every service.
- [ ] **2.2 Understand AWS Cloud security, governance, and compliance concepts**
  <br>Where to find compliance information (AWS Artifact) and how compliance needs vary by geography/industry; security logs and encryption in transit vs at rest; services customers use to secure resources (Amazon Inspector, Security Hub, GuardDuty, Shield); governance services — monitoring with CloudWatch, auditing with CloudTrail, Audit Manager, and Config.
  - 📖 Lesson: [AWS Security, Governance, and Compliance Concepts for CLF-C02](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-security-governance-and-compliance/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: AWS Artifact = self-service download of AWS's compliance reports (SOC, PCI, ISO) and agreements — free, no configuration.
  - Must know: Compliance requirements vary by geography (data residency, GDPR-style laws), industry (HIPAA, PCI DSS), and even by AWS service (services-in-scope lists).
- [ ] **2.3 Identify AWS access management capabilities**
  <br>IAM fundamentals: protecting the root user, the principle of least privilege, IAM Identity Center; access keys and password policies; credential storage (Secrets Manager, Systems Manager); MFA, cross-account IAM roles, federated identity; groups and users, custom vs managed policies, and root-user-only tasks.
  - 📖 Lesson: [AWS IAM Explained: Users, Groups, Roles, Policies & Root User Best Practices](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-iam-access-management/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: IAM is a free, global service: authentication proves who you are; authorization (policies) decides what you can do.
  - Must know: Users hold long-term credentials, groups organize users for shared permissions, roles are assumed temporarily with no long-term credentials, policies are JSON permission documents.
- [ ] **2.4 Identify components and resources for security**
  <br>Network and application protection features (security groups, network ACLs, AWS WAF); third-party security products from AWS Marketplace; where to find security guidance (AWS Knowledge Center, Security Center, Security Blog); recognizing security issues with Trusted Advisor.
  - 📖 Lesson: [AWS Security Components: Security Groups vs Network ACLs, WAF, Trusted Advisor](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-security-components-and-resources/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: Security groups are stateful instance-level firewalls with allow rules only; all rules are evaluated together.
  - Must know: Network ACLs are stateless subnet-level filters with allow AND deny rules, evaluated in number order, first match wins.

### Domain 3: Cloud Technology and Services

**Weight: 34%.** How to deploy and operate in AWS, the global infrastructure, and the core service portfolio: compute, database, network, storage, AI/ML, and analytics.

- [ ] **3.1 Define methods of deploying and operating in the AWS Cloud**
  <br>Access and provisioning methods: programmatic access (APIs, SDKs, CLI) vs the Management Console vs infrastructure as code; one-time vs repeatable processes; cloud, hybrid, and on-premises deployment models; connectivity options (AWS VPN, Direct Connect, public internet).
  - 📖 Lesson: [Deploying and Operating in AWS: Console, CLI, SDKs, IaC, and Connectivity](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-deployment-and-operation-methods/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: Every access method — Console, CLI, SDKs, IaC — ultimately makes calls to the same AWS APIs over HTTPS.
  - Must know: Management Console = human, visual, one-time or infrequent tasks; sign in with password + MFA.
- [ ] **3.2 Define the AWS global infrastructure**
  <br>Relationships among Regions, Availability Zones, and edge locations; high availability through multiple AZs (which share no single point of failure); when to use multiple Regions (disaster recovery, business continuity, low latency, data sovereignty); Local Zones and Wavelength Zones; edge benefits via CloudFront and Global Accelerator.
  - 📖 Lesson: [AWS Global Infrastructure Explained: Regions, Availability Zones, and Edge](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-global-infrastructure/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: A Region is a geographic area containing multiple isolated Availability Zones; an AZ is one or more discrete data centers with independent power, cooling, and networking.
  - Must know: Availability Zones do not share single points of failure but are linked by low-latency connections — deploy across multiple AZs for high availability within a Region.
- [ ] **3.3 Identify AWS compute services**
  <br>EC2 instance families (e.g. compute optimized, storage optimized); container options (ECS, EKS); serverless compute (Lambda, Fargate); elasticity through auto scaling; the purposes of load balancers.
  - 📖 Lesson: [AWS Compute Services Explained: EC2, Lambda, ECS, EKS, and Fargate (CLF-C02)](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-compute-services/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: EC2 = virtual servers with full OS control; you patch, size, and scale them, and they suit long-running workloads.
  - Must know: Instance families by trigger: compute optimized = CPU-heavy (batch, gaming, HPC); memory optimized = in-memory datasets; storage optimized = high local disk I/O (data warehousing); accelerated = GPUs/ML; general purpose = balanced.
- [ ] **3.4 Identify AWS database services**
  <br>EC2-hosted vs AWS managed databases; relational databases (RDS, Aurora); NoSQL (DynamoDB); memory-based databases; database migration tools (AWS DMS, AWS SCT).
  - 📖 Lesson: [AWS Database Services for CLF-C02: RDS, Aurora, DynamoDB, ElastiCache, DMS](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-database-services/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: Database on EC2 = full control (any engine/version, OS access) but you patch, back up, and scale it; managed services shift that work to AWS.
  - Must know: Amazon RDS = managed relational service for MySQL, PostgreSQL, MariaDB, SQL Server, and Oracle; Multi-AZ is for availability, read replicas are for read scaling.
- [ ] **3.5 Identify AWS network services**
  <br>VPC components (subnets, gateways); VPC security (network ACLs, security groups); the purpose of Route 53; edge services (CloudFront, Global Accelerator); connectivity options (AWS VPN, Direct Connect).
  - 📖 Lesson: [AWS Network Services Explained: VPC, Route 53, CloudFront and More](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-network-services/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: Amazon VPC is your logically isolated virtual network in AWS; you define the IP range and split it into subnets, each in exactly one Availability Zone.
  - Must know: Public subnet = route to an internet gateway; private subnet = no direct internet route.
- [ ] **3.6 Identify AWS storage services**
  <br>Object storage use cases; differences between S3 storage classes; block storage (EBS, instance store); file services (EFS, FSx); cached file systems (Storage Gateway); lifecycle policies; AWS Backup use cases.
  - 📖 Lesson: [AWS Storage Services Explained: S3, EBS, EFS, FSx, and Storage Gateway](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-storage-services/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: Match the storage shape first: S3 = objects via API, EBS = block disk for one EC2 instance, EFS/FSx = shared file systems.
  - Must know: S3 is designed for 11 nines (99.999999999%) durability, virtually unlimited capacity, and shines for backups, static websites, data lakes, and media.
- [ ] **3.7 Identify AWS artificial intelligence and machine learning (AI/ML) services and analytics services**
  <br>AI/ML services and the tasks they perform (SageMaker, Lex, Kendra) and the data analytics portfolio (Athena, Kinesis, AWS Glue, QuickSight).
  - 📖 Lesson: [AWS AI/ML and Analytics Services: SageMaker, Athena, Kinesis and More](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-ai-ml-and-analytics-services/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: SageMaker is the platform to build, train, and deploy YOUR OWN ML models; every other AI service is a pre-trained API you just call.
  - Must know: Transcribe = speech to text; Polly = text to speech; Translate = between languages; Comprehend = sentiment and meaning from text.
- [ ] **3.8 Identify services from other in-scope AWS service categories**
  <br>The rest of the in-scope catalog: application integration (EventBridge, SNS, SQS); business applications (Connect, SES); customer engagement (Activate for Startups, IQ, Managed Services, Support); developer tools (CodeBuild, CodeCommit, CodeDeploy, CodePipeline, Cloud9, CloudShell, X-Ray); end-user computing (WorkSpaces, AppStream 2.0); frontend web/mobile (Amplify, AppSync); IoT (IoT Core, IoT Greengrass).
  - 📖 Lesson: [AWS Application Integration, Developer Tools & Other Service Categories](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-application-integration-and-other-services/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: SQS is a pull-based message queue (one consumer per message, buffers and decouples); SNS is push-based pub/sub (one message fanned out to many subscribers).
  - Must know: Fan-out pattern: publish once to an SNS topic, deliver copies to multiple SQS queues for independent processing.

### Domain 4: Billing, Pricing, and Support

**Weight: 12%.** AWS pricing models, cost-management tooling, and the support and technical-resource landscape.

- [ ] **4.1 Compare AWS pricing models**
  <br>Compute purchasing options (On-Demand, Reserved Instances, Spot, Savings Plans, Dedicated Hosts, Dedicated Instances, Capacity Reservations); Reserved Instance flexibility and behavior in AWS Organizations; data transfer charges (incoming/outgoing, same-Region vs cross-Region); storage pricing tiers.
  - 📖 Lesson: [AWS Pricing Models Explained: On-Demand, Reserved, Spot & Savings Plans](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-pricing-models/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: Steady, predictable workloads running a year or more → Reserved Instances or Savings Plans, up to 72% off On-Demand.
  - Must know: Fault-tolerant, interruptible workloads (batch, CI, analytics) → Spot Instances, up to 90% off, reclaimable with a two-minute warning.
- [ ] **4.2 Understand resources for billing, budget, and cost management**
  <br>AWS Budgets, Cost Explorer, and Billing Conductor; the AWS Pricing Calculator; consolidated billing and cost allocation with AWS Organizations; cost allocation tags and the AWS Cost and Usage Report.
  - 📖 Lesson: [AWS Billing and Cost Management Tools: Budgets, Cost Explorer, CUR and More](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-billing-and-cost-management-tools/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: Match by tense: estimate BEFORE = Pricing Calculator; alert DURING = AWS Budgets; analyze AFTER = Cost Explorer; deepest data = CUR.
  - Must know: AWS Pricing Calculator is a free public web tool — no AWS account needed — for estimating a planned architecture's cost.
- [ ] **4.3 Identify AWS technical resources and AWS Support options**
  <br>Where to find whitepapers, blogs, and documentation (Prescriptive Guidance, Knowledge Center, re:Post); AWS Support plans (Developer, Business, Enterprise On-Ramp, Enterprise) and customer service/communities; Trusted Advisor, AWS Health Dashboard, and AWS Health API; abuse reports via Trust and Safety; AWS Partners and Marketplace; Professional Services and Solutions Architects.
  - 📖 Lesson: [AWS Support Plans and Technical Resources: The Complete CLF-C02 Guide](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-support-plans-and-technical-resources/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
  - Must know: Cheapest plan with 24/7 phone/chat access to support engineers: Business; cheapest with any technical support at all: Developer (business-hours email).
  - Must know: Any TAM access (pool) starts at Enterprise On-Ramp; a designated TAM and the Concierge Support Team require Enterprise.

## How to study for CLF-C02

1. **Read the lesson for each topic** in the checklist above, starting with the heaviest domain. Every lesson is free on the [CLF-C02 revision notes](https://www.savemycert.com/revision/aws-cloud-practitioner/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide).
2. **Practice straight after reading.** Answer [CLF-C02 practice questions](https://www.savemycert.com/practice/aws-cloud-practitioner/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide) on the topic you just read. Each option comes with an explanation of why it is right or wrong.
3. **Review what you got wrong**, re-read that lesson section, and tick the topic off only when you get its questions right.
4. **Take a full-length [CLF-C02 mock exam](https://www.savemycert.com/mocks/aws-cloud-practitioner/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)** under the real time limit. Aim to pass mocks comfortably before you book.
5. **On the last day**, skim the [CLF-C02 cheat sheet](https://www.savemycert.com/cheat-sheet/aws-cloud-practitioner/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide) instead of starting anything new.

## Sample questions

[sample-questions.md](sample-questions.md) has 5 worked CLF-C02 questions with the answer, why each option is right or wrong, and the reasoning steps.

## Free resources

- [AWS Certified Cloud Practitioner (CLF-C02) exam guide](https://docs.aws.amazon.com/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02.html): the official source (Amazon Web Services)
- [CLF-C02 certification overview](https://www.savemycert.com/certifications/aws-cloud-practitioner/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)
- [CLF-C02 revision notes](https://www.savemycert.com/revision/aws-cloud-practitioner/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide): every lesson, free to read
- [CLF-C02 practice questions](https://www.savemycert.com/practice/aws-cloud-practitioner/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide): with an explanation on every option
- [CLF-C02 mock exams](https://www.savemycert.com/mocks/aws-cloud-practitioner/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide): full-length and timed
- [CLF-C02 cheat sheet](https://www.savemycert.com/cheat-sheet/aws-cloud-practitioner/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide): the key facts on one page
- [All certification study guides](https://github.com/savemycert-sketch/certification-study-guides)

## Contributing

Spotted an error or an out-of-date fact? [Open an issue](../../issues) with the topic and a link to the official source. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License and disclaimer

This guide is licensed under [CC BY 4.0](LICENSE). You can reuse and adapt it, including commercially, as long as you credit **SaveMyCert** with a link to https://www.savemycert.com/.

This is an independent study resource. It is not affiliated with or endorsed by Amazon Web Services. AWS Certified Cloud Practitioner and CLF-C02 are trademarks of their respective owner. Exam domains and weights are taken from the official exam guide linked above.
