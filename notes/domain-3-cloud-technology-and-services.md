# Domain 3: Cloud Technology and Services (34%)

The largest CLF-C02 domain: how you access and operate AWS, how its global infrastructure is laid out, and the core service catalog. Nearly every question is a matching exercise: find the trigger phrase, name the service.

## 3.1 Define methods of deploying and operating in the AWS Cloud

- **Everything is an API call.** Console, CLI, SDKs, and IaC all end up as the same signed HTTPS requests, so anything done by hand can be automated.

| Method | What it is | Pick it when | Exam cue |
| --- | --- | --- | --- |
| Management Console | Browser-based GUI (plus a mobile app) | Learning, exploring, one-off or rare tasks, visual monitoring | "graphical", "one-time", "new administrator" |
| AWS CLI | Terminal commands you can chain into scripts | An administrator automating repeatable or scheduled ops work | "script", "scheduled task", "from a terminal" |
| SDKs | Language libraries (Python, Java, JavaScript, and more) | Application code needs to call AWS | "from application code", "developer" |
| AWS CloudFormation | JSON/YAML templates deployed as a *stack* | Provisioning whole environments identically, many times | "identical environments", "template", "version control" |

- **CLI script vs CloudFormation:** a script is imperative (run these steps); a template is declarative (reach this end state).
- **AWS CDK:** define infrastructure in a general-purpose language; it generates CloudFormation underneath. On this exam, CloudFormation is the IaC answer.
- **One-time vs repeatable:** a one-off task is fine in the console; anything repeated belongs in code. A written runbook is still manual.

**Deployment models**

- **Cloud:** everything on AWS (new builds, fully migrated workloads).
- **Hybrid:** AWS linked to an on-premises data center. Triggers: legacy systems that must stay, data residency or compliance, phased migration.
- **On-premises (private cloud):** all in your own facility; full control, but upfront capital and maintenance.

**Connectivity**

| Option | Path | Setup | Performance | Exam cue |
| --- | --- | --- | --- | --- |
| Public internet | Shared, TLS-encrypted | Immediate | Variable | "lowest cost, no special need" |
| Site-to-Site VPN | IPsec tunnel over the internet | Hours to days | Variable | "quickly", "encrypted connection" |
| Direct Connect | Dedicated private physical circuit | Weeks or longer | Consistent, predictable | "consistent performance", "must not cross the public internet" |

- Direct Connect does not encrypt by itself. For both a private path and encryption, run a VPN over Direct Connect (or use TLS in the application).

📖 Full lesson: [Deploying and Operating in AWS: Console, CLI, SDKs, IaC, and Connectivity](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-deployment-and-operation-methods/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

## 3.2 Define the AWS global infrastructure

- **Region:** a distinct geographic area where AWS groups its data centers. You choose the Region for every resource. Data stays in that Region unless you move or replicate it yourself, which is the basis of every data-sovereignty answer.
- **Availability Zone (AZ):** one or more discrete data centers inside a Region, each with its own power, cooling, and networking. AZs are physically separated so they fail independently (no shared single point of failure), yet they are linked by high-bandwidth, low-latency private connections.
- **Edge location:** a site in a city near users, far more numerous than Regions. It hosts CloudFront caches and Global Accelerator entry points, not your servers.

**Multi-AZ vs multi-Region**

- **Multiple AZs = high availability inside one Region.** Survives a data-center or AZ failure. Does not help with a Region-wide outage or distant users.
- **Multiple Regions** for four reasons: disaster recovery, business continuity, low latency for users on other continents, and data sovereignty/residency.

**Edge services**

- **CloudFront:** CDN that caches content (static files, video, API responses) near users.
- **Global Accelerator:** no caching; gives static IP addresses and moves TCP/UDP traffic onto the AWS private network at the closest edge. Suits non-cacheable workloads such as gaming or VoIP.

**Infrastructure extensions**

| Extension | Where the hardware sits | Exam cue |
| --- | --- | --- |
| Local Zone | A metro area far from its parent Region (managed through that Region) | "single-digit millisecond latency" for users in a specific city |
| Wavelength Zone | Inside a telecom carrier's 5G network | "5G", "mobile edge", "carrier network" |
| Outposts | Your own data center | AWS infrastructure on premises |

📖 Full lesson: [AWS Global Infrastructure Explained: Regions, Availability Zones, and Edge](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-global-infrastructure/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

## 3.3 Identify AWS compute services

- Three signals decide compute questions: **who manages servers**, **runtime pattern** (always on vs short and event-driven), and **packaging** (code, container, or app).

| Service | What it is for | Exam cue |
| --- | --- | --- |
| Amazon EC2 | Virtual servers; you pick the AMI and instance type and control the OS | "full OS control", "custom software", "lift and shift", "runs 24/7" |
| AWS Lambda | Event-triggered functions; no servers; billed per request and compute time | "runs when a file is uploaded", "no servers", "pay only when code runs" |
| AWS Fargate | Serverless compute for containers under ECS or EKS | "containers without managing servers or clusters" |
| Amazon ECS | AWS-native container orchestrator | "simplest way to run containers on AWS" |
| Amazon EKS | Managed Kubernetes control plane | "Kubernetes", "existing Kubernetes tooling", "portability" |
| Elastic Beanstalk | PaaS: upload code, AWS provisions EC2, scaling, load balancing | "just upload code and deploy" |
| Amazon Lightsail | Simple bundled VPS at a predictable monthly price | "small website", "beginner", "predictable cost" |
| AWS Batch | Schedules and runs large volumes of batch jobs | "thousands of batch jobs", "job queues" |

- Lambda is for short tasks (15-minute cap per run); long-running or OS-dependent work goes to EC2, or Fargate if containerized.
- **Lambda runs functions; Fargate runs containers.** Fargate is where containers execute, not an orchestrator.
- ECS and EKS run containers on the **EC2 launch type** (you manage hosts) or on **Fargate**.

**EC2 instance families**

| Family | Bottleneck it solves | Example workloads |
| --- | --- | --- |
| General purpose | Balanced; nothing special | Web servers, dev/test |
| Compute optimized | CPU | Batch processing, media transcoding, game servers, HPC |
| Memory optimized | Data held in RAM | In-memory databases and caches, real-time big-data analytics |
| Storage optimized | Fast local disk I/O | Data warehousing, distributed file systems, log processing |
| Accelerated computing | GPUs and other accelerators | ML training/inference, graphics rendering |

- Memory optimized (RAM) vs storage optimized (local disk) is the classic swap.

**Scaling and load balancing**

- **Auto scaling = elasticity.** EC2 Auto Scaling groups (min, desired, max) scale out and in on metrics such as CPU and replace unhealthy instances.
- **Elastic Load Balancing distributes traffic** across healthy targets in multiple AZs behind one endpoint. It never adds capacity.
- Load balancer types: ALB (HTTP/HTTPS, layer 7), NLB (TCP/UDP, layer 4, high performance), Gateway Load Balancer (third-party virtual appliances such as firewalls).

📖 Full lesson: [AWS Compute Services Explained: EC2, Lambda, ECS, EKS, and Fargate (CLF-C02)](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-compute-services/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

## 3.4 Identify AWS database services

- **Self-managed on EC2:** any engine or version plus OS access; all patching, backups, and scaling are your job.
- **AWS managed:** AWS provisions, patches, backs up, and offers HA; you lose OS access.
- Cue: "reduce operational overhead" or "stop patching database servers" means managed. "Needs OS access" or "unsupported engine version" means EC2.

| Service | Data model | Typical use | Exam cue |
| --- | --- | --- | --- |
| Amazon RDS | Relational (MySQL, PostgreSQL, MariaDB, SQL Server, Oracle, Db2) | Orders, finance, existing SQL apps | "SQL", "joins", "transactions", "managed relational" |
| Amazon Aurora | Relational, MySQL/PostgreSQL-compatible, cloud-native storage | High-performance relational; variable load via Aurora Serverless | "MySQL/PostgreSQL compatible with higher performance", "auto-scaling relational" |
| Amazon DynamoDB | Serverless NoSQL key-value and document, flexible schema | Game state, carts, sessions, profiles, IoT | "key-value", "single-digit millisecond at any scale", "serverless database" |
| Amazon ElastiCache | In-memory, Redis or Memcached | Cache in front of a database, session stores, leaderboards | "cache", "microsecond reads", "offload reads" |
| Amazon MemoryDB | Durable, Redis-compatible in-memory primary database | In-memory speed without a separate durable store | "Redis-compatible durable primary" |
| Amazon Neptune | Graph | Social networks, recommendations, fraud detection | "highly connected data" |

- **RDS Multi-AZ = availability** (a standby in another AZ that takes over automatically and does not serve reads). **Read replicas = read scaling** (can be in other Regions). The exam swaps these.
- Aurora keeps copies of its storage across three AZs. Choose plain RDS when the engine is SQL Server, Oracle, or MariaDB.
- DynamoDB has no instances to size. RDS still has instance classes, even though AWS runs them.

**Migration tools**

- **AWS DMS moves the data** while the source stays online, and can keep replicating continuously.
- **AWS SCT converts the schema** and stored code (for example, procedures and functions) when source and target engines differ.
- Same engine (homogeneous) = DMS alone. Different engines (heterogeneous, for example Oracle to Aurora PostgreSQL) = SCT first, then DMS.

📖 Full lesson: [AWS Database Services for CLF-C02: RDS, Aurora, DynamoDB, ElastiCache, DMS](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-database-services/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

## 3.5 Identify AWS network services

- **Amazon VPC:** a logically isolated virtual network you define (its CIDR range) inside a Region. It spans all AZs of that Region.
- **Subnet:** a slice of the VPC range, always in exactly one AZ. For HA, use subnets in several AZs.
- **Route table:** rules deciding where a subnet's traffic goes. It is what makes a subnet public or private.

| Component | Role | Exam cue |
| --- | --- | --- |
| Internet gateway | Two-way traffic between the VPC and the internet | "allow the VPC to communicate with the internet" |
| Public subnet | Route table points to the internet gateway | "must be reachable from the internet" |
| Private subnet | No route to an internet gateway | "must not be directly reachable" |
| NAT gateway | Sits in a public subnet; gives private resources outbound-only internet access | "private instances need patches but stay unreachable" |
| Security group | Firewall on an individual resource | "instance level" |
| Network ACL | Firewall on a whole subnet | "subnet level" |


**Service-level identification**

| Service | Purpose | Exam cue |
| --- | --- | --- |
| Route 53 | DNS resolution, domain registration, health-check-based routing | "DNS", "register a domain", "route by latency or health" |
| CloudFront | CDN caching content at edge locations | "cache content close to users", "stream video globally" |
| Global Accelerator | Static anycast IPs; TCP/UDP traffic onto the AWS backbone | "static IP", "improve global app performance", "TCP/UDP" |
| Site-to-Site VPN | Encrypted IPsec tunnels over the internet, network to network | "encrypted over the internet" |
| Direct Connect | Dedicated private physical link | "bypasses the public internet" |
| Client VPN | Individual remote users connecting securely | "employees on laptops" |

- Route 53 routing policies: simple, weighted, latency-based, failover, geolocation. It resolves names; it does not carry or cache content.

📖 Full lesson: [AWS Network Services Explained: VPC, Route 53, CloudFront and More](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-network-services/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

## 3.6 Identify AWS storage services

- First classify the data's shape: **object** (S3, via API), **block** (EBS or instance store, a disk for one instance), **file** (EFS or FSx, shared by many instances).
- **Amazon S3:** objects (data + metadata + key) in buckets, accessed over HTTPS, no capacity to provision, designed for 11 nines of durability. Uses: backups, static websites, data lakes, media. Not a boot disk or mounted drive.

**S3 storage classes** (same durability design; they differ in availability, retrieval speed, and price)

| Class | Pick it when | Retrieval |
| --- | --- | --- |
| Standard | Data is accessed often | Milliseconds |
| Intelligent-Tiering | Access pattern is unknown or changing | Milliseconds; automatic tiering, no retrieval fees |
| Standard-IA | Rarely accessed but needed immediately | Milliseconds; retrieval fee |
| One Zone-IA | Infrequent and easily re-created (single AZ) | Milliseconds |
| Express One Zone | Latency-critical, highest performance (single AZ) | Single-digit ms |
| Glacier Instant Retrieval | Archive that still needs instant access | Milliseconds |
| Glacier Flexible Retrieval | Archive that can wait | Minutes to hours |
| Glacier Deep Archive | Long-term retention, lowest cost | Hours (typically up to 12) |

- **Lifecycle policies** do two things: *transition* objects to cheaper classes as they age and *expire* them after a retention period. This is the standard S3 cost-optimization answer.

**Block storage**

- **EBS:** network-attached volume in one AZ, attached to one instance. It persists through stop/start, and a non-root volume survives termination by default. Snapshots are incremental and stored in S3. SSD types suit transactional work; HDD types suit sequential throughput.
- **Instance store:** disks physically on the host. Very fast but ephemeral; the data is lost on stop, hibernate, termination, or hardware failure. No snapshots. Use only for caches, buffers, and scratch data.

**File storage**

| Service | For | Exam cue |
| --- | --- | --- |
| Amazon EFS | Elastic NFS shared by thousands of Linux instances across AZs | "many Linux instances share files" |
| FSx for Windows File Server | SMB shares with Active Directory | "Windows", "SMB", "Active Directory" |
| FSx for Lustre | High-throughput file system for HPC and ML, can link to S3 | "HPC", "ML training throughput" |

**Hybrid and backup**

- **Storage Gateway:** on-premises apps use AWS storage with hot data cached locally. Types: File (NFS/SMB to S3), Volume (iSCSI, snapshots to S3), Tape (virtual tape library). Ongoing hybrid use, not bulk migration.
- **AWS Backup:** centralized, policy-based backup plans across EBS, RDS, DynamoDB, EFS, FSx, EC2, Storage Gateway, and more. Cue: "one place to manage backups across services or accounts."

📖 Full lesson: [AWS Storage Services Explained: S3, EBS, EFS, FSx, and Storage Gateway](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-storage-services/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

## 3.7 Identify AWS artificial intelligence and machine learning (AI/ML) services and analytics services

- **SageMaker** is where you build, train, and deploy *your own* models. Every other AI service below is pre-trained: you call an API and need no ML expertise. "No ML experience" rules SageMaker out.
- Match by input and output.

| AI service | Input to output | Exam cue |
| --- | --- | --- |
| Transcribe | Speech to text | "call transcripts", "captions" |
| Polly | Text to speech | "read articles aloud", "lifelike voice" |
| Translate | Text in one language to another | "localize", "multilingual" |
| Comprehend | Text to sentiment, entities, key phrases | "analyze customer feedback sentiment" |
| Lex | Conversation to intent (chatbots, voice bots) | "chatbot", "virtual agent", "IVR" |
| Rekognition | Photos/video to objects, faces, moderation labels | "facial recognition", "moderate uploads" |
| Textract | Scanned documents to text, form fields, tables | "process invoices", "scanned forms" |
| Kendra | Natural-language questions to answers from internal docs | "employees search company knowledge" |

- A scanned invoice goes to Textract even though it is an image; photos and video go to Rekognition.

| Analytics service | Purpose | Exam cue |
| --- | --- | --- |
| Athena | Serverless SQL directly on data in S3, pay per query | "query S3 with SQL", "ad hoc" |
| AWS Glue | Serverless ETL plus the Glue Data Catalog | "ETL", "prepare data", "data catalog" |
| Kinesis | Collect and analyze streaming data as it arrives | "real time", "clickstream", "sensor stream" |
| QuickSight | BI dashboards and visualizations | "dashboards for executives" |
| Redshift | Data warehouse; load structured data for heavy SQL analytics | "data warehouse", "years of business data" |
| EMR | Managed Spark, Hadoop, and similar frameworks | "Spark", "Hadoop" |
| OpenSearch Service | Full-text search and log analytics inside applications | "product search", "analyze logs" |
| MSK | Managed Apache Kafka | "Kafka" |
| Data Exchange | Find and subscribe to third-party data sets | "third-party data" |

- Athena queries data where it sits in S3; Redshift needs the data loaded in first.
- Kinesis analyzes streams; SQS queues messages between components.

📖 Full lesson: [AWS AI/ML and Analytics Services: SageMaker, Athena, Kinesis and More](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-ai-ml-and-analytics-services/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

## 3.8 Identify services from other in-scope AWS service categories

- Identify the category first, then the service. Distractors tend to be real services from other categories.

**Application integration** (decoupling: components never call each other directly)

| Service | Shape | Exam cue |
| --- | --- | --- |
| SQS | Queue; consumers pull; each message handled by one consumer; buffers spikes | "decouple", "buffer", "queue" |
| SNS | Pub/sub topic; pushes a copy to every subscriber (email, SMS, push, Lambda, HTTP, SQS) | "notify", "fan out", "alerts" |
| EventBridge | Event bus with content-based rules across AWS, SaaS, and custom apps | "event-driven", "react to SaaS events" |
| Step Functions | Visual state machine for ordered, branching, retrying workflows | "orchestrate", "multi-step workflow" |

- Fan-out: publish once to SNS, and several SQS queues each get a copy to process at their own pace.

**Business applications and customer engagement**

- **Connect:** cloud contact center. **SES:** bulk and transactional email (SNS can email subscribers but is not an email platform).
- **Activate:** startup credits and training. **IQ:** hire third-party AWS-certified freelancers. **AMS:** AWS operates your infrastructure. **AWS Support:** tiered plans for help from AWS engineers.

**Developer tools**

| Service | Stage | Exam cue |
| --- | --- | --- |
| CodeCommit | Private Git repositories (closed to new customers, still in the guide) | "Git repository" |
| CodeBuild | Compile and test | "build and run tests" |
| CodeDeploy | Deploy to EC2, on-premises, Lambda, ECS | "automate deployments" |
| CodePipeline | Orchestrate the full release pipeline | "CI/CD pipeline" |
| CodeArtifact | Package repository (npm, Maven, PyPI) | "store dependencies" |
| Cloud9 | Browser-based IDE | "write and debug code in a browser" |
| CloudShell | Browser terminal with the CLI already authenticated | "run CLI commands from the console" |
| X-Ray | Distributed request tracing | "trace requests", "find latency bottleneck" |
| AppConfig | Configuration and feature flags without redeploying | "feature flags" |

**End-user computing, frontend/mobile, IoT**

| Service | Purpose | Exam cue |
| --- | --- | --- |
| WorkSpaces | Full persistent virtual desktops (DaaS) | "virtual desktops", "remote workforce" |
| AppStream 2.0 | Stream single applications to a browser | "stream an app, no install" |
| WorkSpaces Web | Secure browser access to internal web apps (now branded Secure Browser) | "secure access to internal sites" |
| Amplify | Build, deploy, host full-stack web/mobile apps | "quickly build and host an app" |
| AppSync | Managed GraphQL APIs with real-time and offline sync | "GraphQL" |
| Device Farm | Test apps on real devices hosted by AWS | "test on many real phones" |
| IoT Core | Secure cloud connection point for devices (MQTT, certificates) | "connect millions of sensors" |
| IoT Greengrass | Software on devices for local compute, even offline | "edge inference", "works offline" |

📖 Full lesson: [AWS Application Integration, Developer Tools & Other Service Categories](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-application-integration-and-other-services/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

[← Back to the study guide](../README.md)
