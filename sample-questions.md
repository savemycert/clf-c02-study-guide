# CLF-C02 Sample Questions with Answers

20 worked practice questions for the **AWS Certified Cloud Practitioner (CLF-C02)** exam. Try each one before you open the answer.

For many more, with the same explanation on every option, use the [CLF-C02 practice questions](https://www.savemycert.com/practice/aws-cloud-practitioner/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide) on SaveMyCert.

## Question 1

*Cloud Concepts*

**Which statement best describes the value proposition of the AWS Cloud?** Choose one.

- **a.** Customers receive a fixed monthly fee that covers unlimited use of all AWS services.
- **b.** Customers lease dedicated AWS staff to manage their on-premises servers.
- **c.** Customers consume computing resources on demand with pay-as-you-go pricing instead of buying and operating their own hardware.
- **d.** Customers purchase AWS hardware upfront and install it in their own data centers to reduce network latency.

<details>
<summary>Show answer and explanation</summary>

**Answer: c**

- **a** ❌ AWS pricing is variable and metered by actual usage, not a flat fee for unlimited consumption.
- **b** ❌ AWS provides cloud services, not outsourced staffing for customer-owned on-premises equipment.
- **c** ✅ Correct. The AWS value proposition is on-demand resources delivered over the internet with metered, pay-as-you-go pricing, replacing ownership of physical infrastructure.
- **d** ❌ This reverses the model: the AWS Cloud removes the need to purchase and house hardware; it is not an upfront hardware purchase program.

**The concept.** The AWS Cloud value proposition is the core answer to why organizations choose AWS over traditional on-premises IT: on-demand resources with pay-as-you-go pricing instead of owning hardware.

**Why this is correct.** Option c captures both halves of the value proposition: resources are available on demand (no procurement cycle) and billing is pay-as-you-go (costs track usage). Option d describes the opposite of cloud computing, since the whole point is that customers stop buying and racking hardware. Option a is wrong because AWS billing is variable and metered, not a flat unlimited-use fee. Option b confuses a cloud provider with a managed-services staffing arrangement for on-premises gear, which is not what AWS sells.

**How to reason it out**

1. Recall that a value proposition states what the customer gains versus the alternative, which here is traditional on-premises IT.
2. Identify the two defining traits of the AWS model: on-demand consumption and pay-as-you-go pricing.
3. Eliminate any option that involves buying hardware upfront, flat unlimited fees, or managing on-premises equipment.
4. Select the option that pairs on-demand resources with usage-based billing.

> **Exam tip:** AWS value proposition = on-demand resources + pay only for what you use, instead of owning hardware.

</details>

📖 Learn this topic: [Benefits of the AWS Cloud: Value Proposition, Elasticity & Global Reach](https://www.savemycert.com/revision/aws-cloud-practitioner/benefits-of-the-aws-cloud/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 2

*Cloud Concepts*

**For years, a company purchased servers based on demand forecasts made two years in advance, and it frequently ended up with idle hardware. After moving to AWS, the company provisions resources for current demand and adjusts them as demand changes. Which advantage of the AWS Cloud does this describe?** Choose one.

- **a.** Benefit from massive economies of scale
- **b.** Stop guessing capacity
- **c.** Go global in minutes
- **d.** Increase speed and agility

<details>
<summary>Show answer and explanation</summary>

**Answer: b**

- **a** ❌ Economies of scale explains why AWS unit prices are low due to aggregated customer usage; the scenario is about capacity forecasting, not pricing.
- **b** ✅ Correct. The scenario is about replacing long-range demand forecasting and overprovisioning with provisioning for actual demand, which is exactly the stop-guessing-capacity advantage.
- **c** ❌ Going global concerns deploying to new geographic Regions quickly; nothing in the scenario involves geography.
- **d** ❌ Agility is about faster experimentation and time to market; the scenario focuses on eliminating capacity forecasts and idle hardware, not innovation speed.

**The concept.** Stop guessing capacity is the advantage that removes long-range demand forecasting: instead of overprovisioning or underprovisioning years ahead, you provision for actual demand and adjust at any time.

**Why this is correct.** The stem's signals are multi-year forecasts and idle hardware from overbuying, followed by provisioning to actual demand in AWS. That is the textbook description of stop guessing capacity. Economies of scale is tempting because both relate to cost, but it explains low unit prices from aggregated customer demand, not capacity planning. Go global in minutes involves geographic expansion, which is absent here. Speed and agility would require language about experimentation or time to market, which the scenario never mentions.

**How to reason it out**

1. Identify the pain in the scenario: forecasting demand years ahead and buying hardware that sits idle.
2. Identify the change after AWS: capacity matches current demand and can be adjusted anytime.
3. Map forecasting-and-overprovisioning language to the stop-guessing-capacity advantage.
4. Rule out economies of scale (pricing), global reach (geography), and agility (experimentation speed).

> **Exam tip:** Forecasting demand and overprovisioning or underprovisioning hardware points to stop guessing capacity.

</details>

📖 Learn this topic: [Benefits of the AWS Cloud: Value Proposition, Elasticity & Global Reach](https://www.savemycert.com/revision/aws-cloud-practitioner/benefits-of-the-aws-cloud/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 3

*Cloud Concepts*

**A company wants its engineers to stop spending time on racking servers, replacing failed disks, and managing data center power and cooling so they can focus on building customer-facing applications. Which advantage of the AWS Cloud addresses this goal?** Choose one.

- **a.** Benefit from massive economies of scale
- **b.** Stop spending money running and maintaining data centers
- **c.** Go global in minutes
- **d.** Trade fixed expense for variable expense

<details>
<summary>Show answer and explanation</summary>

**Answer: b**

- **a** ❌ Economies of scale is about lower unit prices from aggregated demand, not about freeing staff from hardware maintenance tasks.
- **b** ✅ Correct. Offloading the undifferentiated heavy lifting of physical infrastructure operations to AWS is exactly this advantage.
- **c** ❌ This advantage concerns deploying applications to Regions worldwide, which is unrelated to relieving staff of data center chores.
- **d** ❌ That advantage is about the cost model shifting from upfront purchases to pay-as-you-go, not about who performs facility maintenance work.

**The concept.** One of the six advantages is stop spending money running and maintaining data centers: AWS takes over the undifferentiated heavy lifting of physical infrastructure so customer teams can focus on their applications.

**Why this is correct.** The scenario lists physical operations tasks: racking, disk replacement, power, and cooling. In the AWS Cloud those become AWS's responsibility, which is the advantage AWS describes as stop spending money running and maintaining data centers, often called removing undifferentiated heavy lifting. Trading fixed for variable expense is a plausible distractor because both involve data center costs, but it describes the billing structure, not the operational burden. Economies of scale explains pricing, and go global in minutes concerns geographic deployment, so neither matches the staffing-focus goal in the stem.

**How to reason it out**

1. List the tasks in the scenario: racking hardware, replacing disks, managing power and cooling.
2. Recognize these as physical data center operations, not cost structure or geography.
3. Match physical facility work being offloaded to AWS with the stop-running-data-centers advantage.
4. Confirm the stated goal, letting engineers focus on applications, matches removing undifferentiated heavy lifting.

> **Exam tip:** Scenarios about offloading hardware and facility upkeep map to stop spending money running data centers.

</details>

📖 Learn this topic: [Benefits of the AWS Cloud: Value Proposition, Elasticity & Global Reach](https://www.savemycert.com/revision/aws-cloud-practitioner/benefits-of-the-aws-cloud/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 4

*Cloud Concepts*

**How many pillars does the AWS Well-Architected Framework contain?** Choose one.

- **a.** Six
- **b.** Five
- **c.** Seven
- **d.** Four

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ The current framework has six pillars: operational excellence, security, reliability, performance efficiency, cost optimization, and sustainability.
- **b** ❌ The framework originally had five pillars, but sustainability was added in late 2021, so five is out of date.
- **c** ❌ There is no seventh pillar; seven overcounts the framework.
- **d** ❌ The framework has never had four pillars; this undercounts even the original version.

**The concept.** The AWS Well-Architected Framework organizes AWS architectural best practices into exactly six pillars. Knowing the correct count is a directly testable structural fact on CLF-C02.

**Why this is correct.** Six is correct because the framework consists of operational excellence, security, reliability, performance efficiency, cost optimization, and sustainability. Five is the classic trap: the framework launched with five pillars, and sustainability was added as the sixth in late 2021, so older study material still says five. Four and seven are simple miscounts with no basis in AWS documentation. If you can recite all six pillar names, you can never be fooled by an outdated count.

**How to reason it out**

1. Recall the six pillar names: operational excellence, security, reliability, performance efficiency, cost optimization, sustainability.
2. Count them: that is six pillars.
3. Remember that sustainability was added in late 2021, which is why 'five' appears in outdated materials.
4. Select six.

> **Exam tip:** The AWS Well-Architected Framework has exactly six pillars; sustainability (added 2021) made it six.

</details>

📖 Learn this topic: [AWS Well-Architected Framework: The Six Pillars Explained for CLF-C02](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-well-architected-framework-pillars/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 5

*Cloud Concepts*

**Before starting its AWS migration, a company launches a training program to build cloud skills across its IT staff and appoints change leaders to drive a culture of continuous learning. Which perspective of the AWS Cloud Adoption Framework does this work belong to?** Choose one.

- **a.** Operations
- **b.** People
- **c.** Business
- **d.** Governance

<details>
<summary>Show answer and explanation</summary>

**Answer: b**

- **a** ❌ Operations is a technical perspective about running cloud services day to day (observability, incident management), not workforce readiness.
- **b** ✅ The People perspective treats cloud adoption as a workforce and culture transformation, covering skills training, leadership, and organizational change.
- **c** ❌ The Business perspective ensures cloud investments deliver business outcomes and accelerate digital transformation; it is not about staff skills or culture.
- **d** ❌ Governance orchestrates the transformation while managing risk (program management, cloud financial management); training staff is a People capability.

**The concept.** The AWS CAF organizes cloud transformation capabilities into six perspectives. The People perspective serves as a bridge between technology and business, focusing on culture, leadership, workforce skills, and organizational change.

**Why this is correct.** Skills training, change leadership, and building a learning culture are the defining capabilities of the CAF People perspective, so any scenario about preparing the workforce for cloud adoption maps to People. Business is tempting because training supports business goals, but that perspective is about aligning cloud investments with business outcomes, owned by executives like CEOs and CFOs. Operations sounds plausible because IT staff do operational work, but the Operations perspective covers running cloud workloads (monitoring, incident and change management), not developing the people who will run them. Governance covers managing the transformation program and its risks, not culture or training.

**How to reason it out**

1. Identify the altitude of the scenario: it describes organizational readiness work, so it is a CAF perspective question.
2. Extract the key activities: skills training, change leadership, and culture building.
3. Match those activities to the perspective that owns workforce and culture capabilities: People.
4. Eliminate Business (outcomes alignment), Governance (program and risk management), and Operations (day-to-day running of workloads).

> **Exam tip:** Any AWS CAF scenario about training, culture, or workforce change is the People perspective.

</details>

📖 Learn this topic: [AWS Cloud Adoption Framework & Migration Strategies: The 7 Rs, DMS, and Snowball](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-cloud-adoption-framework-migration-strategies/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 6

*Cloud Concepts*

**A company is comparing cost behaviors before migrating to AWS. Which of the following is a variable cost?** Choose one.

- **a.** A storage array purchased upfront for the data center
- **b.** A three-year lease on data center floor space
- **c.** On-demand compute capacity billed per second while instances are running
- **d.** A prepaid multi-year hardware support contract

<details>
<summary>Show answer and explanation</summary>

**Answer: c**

- **a** ❌ A purchased asset costs the same whether it is heavily used or sits idle, so it is a fixed cost.
- **b** ❌ The lease payment is committed in advance and does not change with how much the space is used, making it a fixed cost.
- **c** ✅ The charge rises and falls directly with consumption: run more, pay more; stop, and the cost stops. That behavior is the definition of a variable cost.
- **d** ❌ The contract is paid regardless of how often support is actually needed, so the cost does not track usage — it is fixed.

**The concept.** A variable cost rises and falls with consumption, while a fixed cost stays the same regardless of how much the asset is used. The classification test is behavioral: if usage doubles, does the cost double?

**Why this is correct.** On-demand compute billed per second is the textbook variable cost: the bill tracks actual usage moment by moment, and dropping usage to zero drops the charge to zero. The three distractors are all classic fixed costs — a purchased storage array, a floor-space lease, and a prepaid support contract are committed before any usage occurs and do not shrink when demand falls. This is exactly the pattern CLF-C02 tests: purchased and leased assets are fixed; metered, pay-as-you-go consumption is variable.

**How to reason it out**

1. Recall the test: a cost is variable if it changes in proportion to usage.
2. Check each option: does the amount paid go up or down as consumption changes?
3. The storage array, lease, and support contract are all committed in advance and stay flat regardless of utilization — fixed.
4. Per-second on-demand compute is metered against actual use, so it is the variable cost.

> **Exam tip:** Purchased hardware, leases, and prepaid contracts are fixed; metered pay-as-you-go usage is variable.

</details>

📖 Learn this topic: [AWS Cloud Economics: CapEx vs OpEx, TCO, and Managed Services (CLF-C02)](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-cloud-economics-fundamentals/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 7

*Security and Compliance*

**Which statement best describes the AWS shared responsibility model?** Choose one.

- **a.** AWS assumes full responsibility for all security once a workload is migrated to the cloud.
- **b.** AWS is responsible for security of the cloud, and the customer is responsible for security in the cloud.
- **c.** The customer is responsible for security of the cloud, and AWS is responsible for security in the cloud.
- **d.** AWS and the customer split every individual security control equally between them.

<details>
<summary>Show answer and explanation</summary>

**Answer: b**

- **a** ❌ Moving to AWS redistributes security work; it does not outsource it. The customer keeps responsibility for data, access, and configuration.
- **b** ✅ This is the model's exact formulation: AWS secures the infrastructure that runs its services, and the customer secures what they deploy and store on that infrastructure.
- **c** ❌ This inverts the model. Customers can never secure the physical infrastructure, and AWS never manages the customer's data or permissions.
- **d** ❌ Most controls belong entirely to one party; only a small set of controls, such as patch management, are shared, and even those are split by layer rather than equally.

**The concept.** The AWS shared responsibility model divides security duties: AWS handles security OF the cloud (the infrastructure running AWS services), while the customer handles security IN the cloud (everything they put on that infrastructure).

**Why this is correct.** The correct answer restates AWS's own six-word summary of the model: security OF the cloud belongs to AWS, security IN the cloud belongs to the customer. The claim that AWS takes over all security after migration is the most dangerous misconception the model exists to correct, because misconfigured customer resources cause most real cloud incidents. The inverted phrasing swaps the two sides, which is a classic exam trap that relies on reading too quickly. The equal-split option fails because the model assigns most controls wholly to one party; only patch management, configuration management, and awareness and training are shared, and each party acts in its own layer rather than splitting work fifty-fifty.

**How to reason it out**

1. Recall the model's summary phrase: OF the cloud = AWS, IN the cloud = customer.
2. Eliminate any option claiming one party owns everything, since the model is a partnership.
3. Eliminate the option that swaps OF and IN, keeping the mapping mechanical.
4. Reject the equal-split idea because sharing applies only to a few named controls, each split by layer.

> **Exam tip:** Memorize the mapping: AWS = security OF the cloud; customer = security IN the cloud.

</details>

📖 Learn this topic: [AWS Shared Responsibility Model: Security OF the Cloud vs IN the Cloud](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-shared-responsibility-model/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 8

*Security and Compliance*

**Which task is an example of security OF the cloud under the AWS shared responsibility model?** Choose one.

- **a.** Assigning permissions to IAM users
- **b.** Configuring security group rules for an application
- **c.** Enabling encryption on objects stored in Amazon S3
- **d.** Maintaining physical security controls at data center facilities

<details>
<summary>Show answer and explanation</summary>

**Answer: d**

- **a** ❌ Every permission granted is a customer decision and a customer responsibility, so it is security IN the cloud.
- **b** ❌ Firewall rules control what traffic can reach the customer's resources, a decision only the customer can make, so this is security IN the cloud.
- **c** ❌ AWS provides encryption capabilities, but choosing to turn them on for your data is a customer choice, making it security IN the cloud.
- **d** ✅ Protecting the buildings, guards, badge access, and environmental controls at AWS facilities is infrastructure protection, which is AWS's side of the model.

**The concept.** Security OF the cloud covers the infrastructure AWS operates: physical facilities, hardware, networking, and virtualization software. Security IN the cloud covers what customers deploy, configure, and store.

**Why this is correct.** Physical security of data centers is the textbook example of security OF the cloud: customers can never visit an AWS facility or touch its hardware, so protecting facilities is entirely and permanently AWS's job. The three distractors all describe decisions that depend on the customer's intent. Security group rules define which traffic the customer permits, IAM permissions define who the customer allows to act, and enabling S3 encryption is the customer's choice about protecting their own data. AWS supplies the features in each case, but supplying a tool is not the same as being responsible for how it is used.

**How to reason it out**

1. Translate OF the cloud to mean the infrastructure layer that AWS operates.
2. Test each option: does the task require access to AWS facilities or host systems, or does it depend on customer decisions?
3. Physical facility security requires access to AWS buildings, so it is AWS's responsibility.
4. Security groups, IAM permissions, and encryption choices all encode customer intent, so they are security IN the cloud.

> **Exam tip:** If a task requires physical access to AWS facilities or hardware, it is security OF the cloud and belongs to AWS.

</details>

📖 Learn this topic: [AWS Shared Responsibility Model: Security OF the Cloud vs IN the Cloud](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-shared-responsibility-model/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 9

*Security and Compliance*

**An external auditor asks a company to provide the SOC 2 report and PCI DSS attestation that cover the AWS infrastructure hosting its workloads. Which AWS service provides on-demand access to these documents?** Choose one.

- **a.** AWS CloudTrail
- **b.** AWS Trusted Advisor
- **c.** AWS Artifact
- **d.** AWS Audit Manager

<details>
<summary>Show answer and explanation</summary>

**Answer: c**

- **a** ❌ AWS CloudTrail records API activity in an AWS account; it is an activity log, not a repository of compliance reports about AWS infrastructure.
- **b** ❌ AWS Trusted Advisor provides best-practice checks across cost, performance, security, and other categories; it does not provide AWS compliance reports or attestations.
- **c** ✅ AWS Artifact is the self-service, no-cost portal where AWS publishes its own third-party audit reports, including SOC 1/2/3 reports, PCI DSS attestations, and ISO certifications, for customers to download on demand.
- **d** ❌ AWS Audit Manager collects evidence about the customer's own AWS usage to support the customer's audits; it does not distribute AWS's third-party audit reports.

**The concept.** AWS Artifact is the central self-service portal for AWS's own compliance documentation. Its Reports section provides on-demand downloads of third-party audit reports covering AWS infrastructure, such as SOC reports, PCI DSS attestations, and ISO 27001 certifications.

**Why this is correct.** The auditor is asking for evidence that AWS (the provider) has been audited against SOC 2 and PCI DSS. That evidence is AWS's compliance documentation, and AWS distributes it exclusively through AWS Artifact at no charge. Audit Manager is the classic distractor, but it gathers evidence about the customer's own resources, not reports about AWS. CloudTrail logs API calls, and Trusted Advisor runs best-practice checks; neither holds audit reports.

**How to reason it out**

1. Identify what is being requested: audit reports that cover AWS infrastructure itself (SOC 2, PCI DSS).
2. Recall that AWS publishes its own compliance evidence through a single self-service portal: AWS Artifact.
3. Eliminate Audit Manager because it collects the customer's evidence, and eliminate CloudTrail and Trusted Advisor because neither distributes compliance reports.

> **Exam tip:** Any question about downloading SOC, PCI, or ISO reports that cover AWS itself points to AWS Artifact.

</details>

📖 Learn this topic: [AWS Security, Governance, and Compliance Concepts for CLF-C02](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-security-governance-and-compliance/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 10

*Security and Compliance*

**A company has 25 developers who all need the same set of AWS permissions. An administrator wants to grant and manage these permissions in one place instead of configuring each developer individually. Which IAM feature should the administrator use?** Choose one.

- **a.** Create an IAM group, attach the required policies to it, and add the 25 developers as members.
- **b.** Create an IAM role and have each developer sign in to the console with the role's password.
- **c.** Create a single IAM user and share its password among the 25 developers.
- **d.** Attach an identical inline policy to each of the 25 IAM users.

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ Correct. A group is a collection of IAM users; policies attached to the group are inherited by every member, so shared permissions are managed once.
- **b** ❌ Roles have no password or long-term credentials; they are assumed temporarily and are not the tool for organizing standing permissions for a set of people.
- **c** ❌ Sharing one identity destroys accountability and violates security best practices; each person should have their own identity.
- **d** ❌ Inline policies are embedded in a single identity and cannot be reused, so this creates 25 separate copies to maintain instead of one shared attachment.

**The concept.** An IAM group is a collection of IAM users used purely to manage permissions at scale: attach a policy to the group once and every member inherits it. Groups cannot sign in and cannot be nested.

**Why this is correct.** The scenario describes many people who need identical, ongoing permissions, which is exactly what groups exist for. Attaching policies to a group means adding or removing a developer instantly grants or revokes the shared permissions, with a single policy attachment to audit. A shared user removes individual accountability, a role is an assumable identity for temporary access rather than a container for people, and duplicating inline policies across 25 users multiplies maintenance work and drift risk.

**How to reason it out**

1. Spot the pattern: multiple humans needing the same standing permissions points to a group.
2. Eliminate shared credentials and per-user policy copies as anti-patterns.
3. Remember that roles are assumed temporarily and have no sign-in password, so they do not organize people.
4. Choose the group with policies attached once and users added as members.

> **Exam tip:** Same permissions for many people means an IAM group; groups organize users and cannot sign in themselves.

</details>

📖 Learn this topic: [AWS IAM Explained: Users, Groups, Roles, Policies & Root User Best Practices](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-iam-access-management/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 11

*Security and Compliance*

**A virtual firewall in AWS controls inbound and outbound traffic at the instance level and automatically allows return traffic for any connection it permits. Which component does this describe?** Choose one.

- **a.** Security group
- **b.** AWS Trusted Advisor
- **c.** Network ACL
- **d.** AWS WAF

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ Security groups operate at the instance (elastic network interface) level and are stateful, so return traffic for an allowed connection is permitted automatically.
- **b** ❌ Trusted Advisor is a best-practice checker that inspects your account configuration; it does not filter network traffic at all.
- **c** ❌ Network ACLs operate at the subnet level and are stateless, so return traffic must be explicitly allowed by a separate rule.
- **d** ❌ AWS WAF is a layer-7 web application firewall that inspects HTTP and HTTPS request content; it does not act as an instance-level port firewall.

**The concept.** Security groups are stateful virtual firewalls attached to individual resources such as EC2 instances via their elastic network interfaces.

**Why this is correct.** The two clues in the stem are the level and the state behavior. Instance level plus automatic return traffic means stateful, and the stateful instance-level firewall in a VPC is the security group. A network ACL fails both tests: it sits at the subnet boundary and is stateless, requiring explicit rules for responses. AWS WAF works at layer 7 on web request content rather than ports and protocols, and Trusted Advisor only reports on configuration; neither is a traffic filter for an instance.

**How to reason it out**

1. Identify the level named in the stem: instance level points to a security group, subnet level points to a network ACL.
2. Check the state behavior: return traffic allowed automatically means stateful, which is the security group.
3. Confirm both attributes match one component before selecting it; here both point to the security group.

> **Exam tip:** Stateful plus instance level always identifies a security group on the exam.

</details>

📖 Learn this topic: [AWS Security Components: Security Groups vs Network ACLs, WAF, Trusted Advisor](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-security-components-and-resources/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 12

*Cloud Technology and Services*

**A newly hired administrator wants to explore the services in a company's AWS account by using a visual, web-based interface with guided wizards and dashboards. Which access method should the administrator use?** Choose one.

- **a.** AWS CloudFormation
- **b.** An AWS SDK
- **c.** AWS CLI
- **d.** AWS Management Console

<details>
<summary>Show answer and explanation</summary>

**Answer: d**

- **a** ❌ CloudFormation provisions infrastructure from templates; it is an infrastructure-as-code service, not an interactive way to browse an account.
- **b** ❌ SDKs are language libraries for calling AWS from application code; they offer no visual interface for a person to explore an account.
- **c** ❌ The CLI is a text-based terminal tool for typing commands and writing scripts, not a visual interface with wizards and dashboards.
- **d** ✅ The Management Console is the web-based graphical interface designed for humans to explore services visually through wizards, forms, and dashboards.

**The concept.** AWS offers several ways to access its services: the web-based Management Console for humans, the CLI for terminal scripting, SDKs for application code, and infrastructure as code for provisioning environments.

**Why this is correct.** The scenario describes a person who is new to the account and wants a visual, guided experience — the defining use case for the AWS Management Console, which provides browser-based sign-in, wizards, forms, and dashboards with no scripting or coding required. The CLI is wrong because it is a text-only terminal tool aimed at scripted administration. An SDK is wrong because it exists for software, not people, to call AWS from inside application code. CloudFormation is wrong because it is a provisioning service driven by templates, not an interactive exploration tool.

**How to reason it out**

1. Identify the actor: a human, not a script or an application.
2. Identify the need: visual exploration with wizards and dashboards.
3. Match a human doing visual, low-stakes work to the Management Console.
4. Eliminate CLI, SDK, and CloudFormation because each targets scripted, programmatic, or template-driven work.

> **Exam tip:** A person exploring AWS visually or performing one-time tasks uses the AWS Management Console.

</details>

📖 Learn this topic: [Deploying and Operating in AWS: Console, CLI, SDKs, IaC, and Connectivity](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-deployment-and-operation-methods/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 13

*Cloud Technology and Services*

**A developer is building a web application in Python that must upload user files to Amazon S3 as part of the application's normal operation. Which access method should the developer use to call AWS services from the application code?** Choose one.

- **a.** AWS Management Console
- **b.** AWS Site-to-Site VPN
- **c.** AWS CloudFormation
- **d.** An AWS SDK

<details>
<summary>Show answer and explanation</summary>

**Answer: d**

- **a** ❌ The console is a web interface for humans; an application cannot click through browser forms to upload files during normal operation.
- **b** ❌ A Site-to-Site VPN is a network connectivity option between an on-premises network and AWS, not a method for code to call AWS services.
- **c** ❌ CloudFormation provisions infrastructure from templates; it does not provide a way for running application code to upload files.
- **d** ✅ SDKs are language-specific libraries that let application code call AWS services as ordinary functions, handling request signing and retries.

**The concept.** AWS SDKs are libraries for specific programming languages, such as Python, JavaScript, and Java, that expose AWS API operations as functions inside application code.

**Why this is correct.** The actor here is software, not a person: the application itself must interact with S3 as part of its normal logic, which is exactly what SDKs exist for — they wrap the underlying AWS APIs in the syntax of the developer's language and handle signing, retries, and response parsing. The Management Console fails because it is a browser interface for humans, not something code can drive in production. CloudFormation fails because it provisions resources rather than performing runtime operations like file uploads. A Site-to-Site VPN fails because it is a connectivity option, not an access method for application code.

**How to reason it out**

1. Identify the actor: an application, not a person at a terminal or in a browser.
2. Recognize the trigger phrase for SDKs: calling AWS services from application code.
3. Confirm the SDK matches the language mentioned — AWS publishes SDKs for Python and other major languages.
4. Eliminate the console (human interface), CloudFormation (provisioning), and VPN (networking).

> **Exam tip:** When application code needs to call AWS services, the answer is an AWS SDK.

</details>

📖 Learn this topic: [Deploying and Operating in AWS: Console, CLI, SDKs, IaC, and Connectivity](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-deployment-and-operation-methods/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 14

*Cloud Technology and Services*

**Which statement best describes an AWS Region?** Choose one.

- **a.** A logical grouping of AWS accounts for consolidated billing
- **b.** A single data center that hosts AWS services for a city
- **c.** One of hundreds of sites worldwide that cache content close to users
- **d.** A separate geographic area of the world that contains multiple isolated Availability Zones

<details>
<summary>Show answer and explanation</summary>

**Answer: d**

- **a** ❌ Grouping accounts for billing describes AWS Organizations, an account-management concept unrelated to physical infrastructure.
- **b** ❌ A Region is never a single data center; it is a geographic area containing multiple Availability Zones, each of which is one or more data centers.
- **c** ❌ That describes edge locations, which are far more numerous than Regions and serve content near users rather than hosting core workloads.
- **d** ✅ This is the definition of a Region: a geographic area, such as Frankfurt or Singapore, holding multiple isolated Availability Zones.

**The concept.** AWS organizes its physical infrastructure into a hierarchy: Regions are separate geographic areas of the world, each containing multiple isolated Availability Zones, with edge locations sitting outside that hierarchy near users.

**Why this is correct.** A Region is defined by two facts the exam tests constantly: it is a geographic area, and it contains multiple isolated Availability Zones. Dozens of Regions exist worldwide, and data placed in one stays there unless the customer moves it. The single-data-center option is wrong by definition — even one Availability Zone can span multiple data centers, and a Region always spans multiple AZs. The hundreds-of-sites option describes edge locations, the content-delivery layer. The account-grouping option confuses physical infrastructure with AWS Organizations, a billing and governance construct.

**How to reason it out**

1. Recall the hierarchy: Regions contain Availability Zones; edge locations sit separately near users.
2. Match geographic area plus multiple isolated AZs to the Region definition.
3. Reject the single-data-center description, which is not even a full Availability Zone.
4. Reject the edge-location and account-grouping descriptions as different concepts entirely.

> **Exam tip:** A Region is a separate geographic area containing multiple isolated Availability Zones.

</details>

📖 Learn this topic: [AWS Global Infrastructure Explained: Regions, Availability Zones, and Edge](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-global-infrastructure/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 15

*Cloud Technology and Services*

**A company is migrating a licensed enterprise application that must run continuously for months and requires administrator access to the underlying operating system so the team can install a proprietary monitoring agent. Which AWS compute service should the company choose?** Choose one.

- **a.** AWS Batch
- **b.** AWS Lambda
- **c.** AWS Fargate
- **d.** Amazon EC2

<details>
<summary>Show answer and explanation</summary>

**Answer: d**

- **a** ❌ AWS Batch schedules and runs finite batch computing jobs; it is not intended for a continuously running application that needs hands-on OS administration.
- **b** ❌ Lambda runs short-lived functions in response to events and gives no access to the underlying operating system, so a long-running application with a custom OS agent does not fit.
- **c** ❌ Fargate runs containers serverlessly, which means AWS manages the hosts and the customer cannot install agents on the underlying operating system.
- **d** ✅ EC2 provides virtual servers with full control of the guest operating system, so the team can install custom agents and run the application continuously for as long as needed.

**The concept.** Amazon EC2 provides resizable virtual servers where the customer controls the guest operating system, making it the default choice for long-running workloads that need OS-level access.

**Why this is correct.** The two requirements in the stem are the classic EC2 triggers: the application runs continuously for months, and the team needs administrator access to the operating system to install software. Only EC2 satisfies both, because serverless options deliberately hide the servers from you. Lambda fails on both counts: it is built for short, event-driven functions and exposes no OS to administer. Fargate removes host management entirely, so while containers can run for long periods, there is no underlying instance for the team to install a monitoring agent on. AWS Batch is a job scheduler for workloads that start, process, and finish; a continuously running enterprise application is not a batch job.

**How to reason it out**

1. Identify the workload characteristics: continuous operation and required OS-level access.
2. Eliminate serverless options (Lambda, Fargate) because they abstract away the operating system.
3. Eliminate AWS Batch because it targets finite jobs, not always-on applications.
4. Select EC2, which offers full control of the guest OS and unlimited run duration.

> **Exam tip:** Full OS control plus a long-running workload points to Amazon EC2.

</details>

📖 Learn this topic: [AWS Compute Services Explained: EC2, Lambda, ECS, EKS, and Fargate (CLF-C02)](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-compute-services/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 16

*Cloud Technology and Services*

**A database team must run a legacy database engine version that Amazon RDS does not support, and the team needs root access to the operating system for custom kernel tuning. Which approach fits, and what responsibility comes with it?** Choose one.

- **a.** Install the database on Amazon EC2; the team becomes responsible for OS patching, backups, and failover
- **b.** Use Amazon Aurora, which provides root access to its underlying servers
- **c.** Use Amazon RDS, because it supports every database engine and version
- **d.** Use Amazon DynamoDB, which can host any relational database engine

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ Self-hosting on EC2 is the only way to run unsupported engine versions with root OS access, and it shifts patching, backups, and high availability onto the team.
- **b** ❌ Aurora is a fully managed service; customers never receive OS or root access to Aurora's infrastructure.
- **c** ❌ RDS supports a specific set of engines and versions and never grants root OS access, so an unsupported legacy version cannot run there.
- **d** ❌ DynamoDB is a NoSQL service with no concept of installing a relational engine; it cannot host third-party database software.

**The concept.** Databases on EC2 trade convenience for control: you can run any engine and version with full OS access, but you take on patching, backups, scaling, and failover yourself.

**Why this is correct.** The stem imposes two constraints only self-hosting satisfies: an engine version RDS does not offer and root-level OS access, so the database must run on EC2, and the answer correctly pairs that choice with its cost, namely that the team inherits the undifferentiated operational work AWS would otherwise handle. Option c overstates RDS, which supports a curated engine list and hides the OS entirely. Option d misunderstands DynamoDB, a managed NoSQL service, not a host for relational software. Option b invents root access on Aurora, which is fully managed with no OS exposure.

**How to reason it out**

1. Identify the constraints: unsupported engine version plus required root OS access.
2. Recognize that managed services (RDS, Aurora, DynamoDB) never expose the OS and limit engine choice.
3. Choose a self-managed database on EC2 as the only fit.
4. Attach the trade-off: the team now owns patching, backups, and failover.

> **Exam tip:** EC2-hosted databases give full control over engine and OS, but you take on patching, backups, and high availability yourself.

</details>

📖 Learn this topic: [AWS Database Services for CLF-C02: RDS, Aurora, DynamoDB, ElastiCache, DMS](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-database-services/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 17

*Cloud Technology and Services*

**A company wants to launch EC2 instances and databases inside a logically isolated section of the AWS Cloud where it defines its own private IP address range. Which AWS service provides this?** Choose one.

- **a.** AWS Direct Connect
- **b.** Amazon VPC
- **c.** Amazon CloudFront
- **d.** Amazon Route 53

<details>
<summary>Show answer and explanation</summary>

**Answer: b**

- **a** ❌ Direct Connect is a dedicated physical connection between an on-premises network and AWS, not a virtual network inside AWS.
- **b** ✅ Amazon VPC is a logically isolated virtual network in the AWS Cloud where you define the IP address range and launch resources such as EC2 instances and databases.
- **c** ❌ CloudFront is a content delivery network that caches content at edge locations; it is not a virtual network for launching resources.
- **d** ❌ Route 53 is a DNS service that translates domain names to IP addresses; it does not provide an isolated network for launching resources.

**The concept.** Amazon VPC (Virtual Private Cloud) is the foundational networking service in AWS. It gives each customer a logically isolated virtual network in which they define a private IP address range and launch resources with a network presence.

**Why this is correct.** The phrase logically isolated section of the AWS Cloud where you define your own IP range is the textbook definition of Amazon VPC, so it is the only service that fits. Route 53 is name resolution, not a network container, so it cannot host EC2 instances. Direct Connect only links an existing on-premises network to AWS over a dedicated line; it is a connectivity option, not a place to launch resources. CloudFront delivers cached content from edge locations and has nothing to do with defining a private network.

**How to reason it out**

1. Spot the trigger phrase: logically isolated virtual network with a customer-defined IP range.
2. Recall that resources with a network presence, such as EC2 and RDS, are launched inside a VPC.
3. Eliminate Route 53 (DNS), Direct Connect (connectivity to AWS), and CloudFront (content delivery) because none of them is a network container.
4. Select Amazon VPC as the service that matches the definition exactly.

> **Exam tip:** A logically isolated virtual network with a self-defined IP range in AWS is always Amazon VPC.

</details>

📖 Learn this topic: [AWS Network Services Explained: VPC, Route 53, CloudFront and More](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-network-services/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 18

*Billing, Pricing, and Support*

**A startup is launching a brand-new web application and has no historical data about how much traffic it will receive. The team wants to avoid any long-term commitment while it measures real usage. Which EC2 purchasing option should the startup use?** Choose one.

- **a.** Standard Reserved Instances
- **b.** Dedicated Hosts
- **c.** On-Demand Instances
- **d.** Spot Instances

<details>
<summary>Show answer and explanation</summary>

**Answer: c**

- **a** ❌ Reserved Instances require a one- or three-year commitment to specific instance attributes, which makes no sense before real usage is known.
- **b** ❌ Dedicated Hosts allocate an entire physical server for licensing or compliance needs and are the most expensive option, none of which applies here.
- **c** ✅ On-Demand requires no commitment and lets the team start, stop, and resize freely while measuring the new workload's real usage.
- **d** ❌ Spot Instances can be interrupted with a two-minute warning, which is unsuitable for a customer-facing application that must stay available.

**The concept.** On-Demand Instances are the default EC2 pricing model: pay the published rate while the instance runs, with no upfront payment and no long-term contract.

**Why this is correct.** A first-time application with unknown usage is the classic On-Demand trigger. The team cannot forecast a baseline, so committing to a Reserved Instance would risk paying for capacity that is never used, and the workload is customer-facing, so Spot interruption is unacceptable. Dedicated Hosts solve hardware isolation and BYOL licensing problems, not commitment problems, and carry the highest cost. The common AWS pattern is to run new workloads On-Demand first, measure steady-state usage, and only then cover that measured baseline with a commitment.

**How to reason it out**

1. Identify the workload traits: brand new, unpredictable usage, no commitment desired.
2. Eliminate commitment-based options (Reserved Instances) because usage cannot be forecast yet.
3. Eliminate Spot because a customer-facing app cannot tolerate a two-minute interruption.
4. Eliminate Dedicated Hosts because there is no licensing or physical-isolation requirement.
5. Choose On-Demand: full flexibility now, commit later once usage is measured.

> **Exam tip:** Unpredictable, short-term, or first-time workloads point to On-Demand Instances.

</details>

📖 Learn this topic: [AWS Pricing Models Explained: On-Demand, Reserved, Spot & Savings Plans](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-pricing-models/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 19

*Billing, Pricing, and Support*

**A company has run the same application servers 24/7 on On-Demand Instances for two years and expects the workload to continue unchanged for several more years. Which statement best describes the company's situation?** Choose one.

- **a.** The company is paying the highest effective long-run rate and could cut costs with a one- or three-year commitment
- **b.** AWS automatically converts long-running On-Demand usage to Reserved Instance pricing
- **c.** On-Demand is the most cost-effective choice for any workload that runs continuously
- **d.** The workload should move to Spot Instances because it runs continuously

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ On-Demand carries the highest long-run price because it requires no commitment; a Reserved Instance or Savings Plan would discount this steady usage by up to 72 percent.
- **b** ❌ AWS never converts usage automatically; Reserved Instances and Savings Plans must be purchased deliberately by the customer.
- **c** ❌ The opposite is true: continuous, predictable workloads are exactly where commitment-based discounts save the most money.
- **d** ❌ Continuous production application servers cannot tolerate Spot's two-minute interruption; running continuously is a reason for a commitment, not for Spot.

**The concept.** Every discount AWS offers requires giving something up, either a time commitment or interruption tolerance. On-Demand gives up neither, so it is the most expensive option over the long run.

**Why this is correct.** A workload that has already run steadily for two years and will continue for years is the textbook case for a Reserved Instance or Savings Plan, which discount that usage by up to 72 percent versus On-Demand. Staying On-Demand means paying the full baseline rate indefinitely. The automatic-conversion option fails because AWS never changes your purchasing option for you, and the Spot option fails because Spot is for interruptible work, not always-on production servers. The first option inverts the actual rule: On-Demand is cost-effective for unpredictable workloads, not continuous ones.

**How to reason it out**

1. Recognize the workload profile: steady, predictable, running continuously for years.
2. Recall that On-Demand has no discount mechanism, so long-run cost is the highest of all options.
3. Match steady multi-year usage to commitment options: Reserved Instances or Savings Plans at up to 72 percent off.
4. Reject Spot because production servers cannot tolerate interruption.
5. Conclude the company is overpaying and should purchase a commitment for the measured baseline.

> **Exam tip:** Steady long-running workloads left on On-Demand pay the highest long-run rate; cover them with a commitment.

</details>

📖 Learn this topic: [AWS Pricing Models Explained: On-Demand, Reserved, Spot & Savings Plans](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-pricing-models/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

## Question 20

*Billing, Pricing, and Support*

**A company is planning to migrate an on-premises application to AWS and wants to estimate the monthly cost of the proposed architecture before deploying anything. Which tool should it use?** Choose one.

- **a.** AWS Budgets
- **b.** AWS Cost Explorer
- **c.** AWS Pricing Calculator
- **d.** AWS Cost and Usage Report

<details>
<summary>Show answer and explanation</summary>

**Answer: c**

- **a** ❌ Budgets alerts on spending thresholds during the month; it cannot price a planned architecture.
- **b** ❌ Cost Explorer analyzes spend that has already happened; it has no data about a workload that does not exist yet.
- **c** ✅ Pricing Calculator models a planned architecture from published prices and produces monthly cost estimates before anything is built.
- **d** ❌ The CUR is raw line-item data about actual charges; a workload that has not run yet generates no line items.

**The concept.** AWS Pricing Calculator estimates what a planned architecture will cost before deployment, working purely from published AWS pricing rather than from account usage.

**Why this is correct.** The scenario's tense settles it: the workload is being priced before deployment, and Pricing Calculator is the only tool in the billing toolkit that can price something that does not exist yet. Cost Explorer and the CUR both operate on historical, actual charges, so a not-yet-migrated application gives them nothing to work with, and Budgets watches live spend against thresholds rather than producing estimates. The lifecycle rule is estimate before, alert during, analyze after.

**How to reason it out**

1. Identify the tense of the scenario: costs are needed before anything is deployed.
2. Recall the lifecycle mapping: before means Pricing Calculator, during means Budgets, after means Cost Explorer and the CUR.
3. Eliminate Cost Explorer and the CUR, which require actual historical usage.
4. Eliminate Budgets, which alerts on live spend rather than estimating planned spend.
5. Choose AWS Pricing Calculator.

> **Exam tip:** Estimating costs before deployment always points to AWS Pricing Calculator.

</details>

📖 Learn this topic: [AWS Billing and Cost Management Tools: Budgets, Cost Explorer, CUR and More](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-billing-and-cost-management-tools/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

---

[← Back to the CLF-C02 study guide](README.md)
