# CLF-C02 Sample Questions with Answers

5 worked practice questions for the **AWS Certified Cloud Practitioner (CLF-C02)** exam. Try each one before you open the answer.

For many more, with the same explanation on every option, use the [CLF-C02 practice questions](https://www.savemycert.com/practice/aws-cloud-practitioner/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide) on SaveMyCert.

## Question 1

*Cloud Concepts*

**Which statement best describes the value proposition of the AWS Cloud?** Choose one.

- **a.** Customers consume computing resources on demand with pay-as-you-go pricing instead of buying and operating their own hardware.
- **b.** Customers purchase AWS hardware upfront and install it in their own data centers to reduce network latency.
- **c.** Customers receive a fixed monthly fee that covers unlimited use of all AWS services.
- **d.** Customers lease dedicated AWS staff to manage their on-premises servers.

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ Correct. The AWS value proposition is on-demand resources delivered over the internet with metered, pay-as-you-go pricing, replacing ownership of physical infrastructure.
- **b** ❌ This reverses the model: the AWS Cloud removes the need to purchase and house hardware; it is not an upfront hardware purchase program.
- **c** ❌ AWS pricing is variable and metered by actual usage, not a flat fee for unlimited consumption.
- **d** ❌ AWS provides cloud services, not outsourced staffing for customer-owned on-premises equipment.

**The concept.** The AWS Cloud value proposition is the core answer to why organizations choose AWS over traditional on-premises IT: on-demand resources with pay-as-you-go pricing instead of owning hardware.

**Why this is correct.** Option a captures both halves of the value proposition: resources are available on demand (no procurement cycle) and billing is pay-as-you-go (costs track usage). Option b describes the opposite of cloud computing, since the whole point is that customers stop buying and racking hardware. Option c is wrong because AWS billing is variable and metered, not a flat unlimited-use fee. Option d confuses a cloud provider with a managed-services staffing arrangement for on-premises gear, which is not what AWS sells.

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

*Security and Compliance*

**Which statement best describes the AWS shared responsibility model?** Choose one.

- **a.** AWS is responsible for security of the cloud, and the customer is responsible for security in the cloud.
- **b.** AWS assumes full responsibility for all security once a workload is migrated to the cloud.
- **c.** The customer is responsible for security of the cloud, and AWS is responsible for security in the cloud.
- **d.** AWS and the customer split every individual security control equally between them.

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ This is the model's exact formulation: AWS secures the infrastructure that runs its services, and the customer secures what they deploy and store on that infrastructure.
- **b** ❌ Moving to AWS redistributes security work; it does not outsource it. The customer keeps responsibility for data, access, and configuration.
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

## Question 3

*Cloud Technology and Services*

**A newly hired administrator wants to explore the services in a company's AWS account by using a visual, web-based interface with guided wizards and dashboards. Which access method should the administrator use?** Choose one.

- **a.** AWS Management Console
- **b.** AWS CLI
- **c.** An AWS SDK
- **d.** AWS CloudFormation

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ The Management Console is the web-based graphical interface designed for humans to explore services visually through wizards, forms, and dashboards.
- **b** ❌ The CLI is a text-based terminal tool for typing commands and writing scripts, not a visual interface with wizards and dashboards.
- **c** ❌ SDKs are language libraries for calling AWS from application code; they offer no visual interface for a person to explore an account.
- **d** ❌ CloudFormation provisions infrastructure from templates; it is an infrastructure-as-code service, not an interactive way to browse an account.

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

## Question 4

*Billing, Pricing, and Support*

**A startup is launching a brand-new web application and has no historical data about how much traffic it will receive. The team wants to avoid any long-term commitment while it measures real usage. Which EC2 purchasing option should the startup use?** Choose one.

- **a.** Standard Reserved Instances
- **b.** Spot Instances
- **c.** On-Demand Instances
- **d.** Dedicated Hosts

<details>
<summary>Show answer and explanation</summary>

**Answer: c**

- **a** ❌ Reserved Instances require a one- or three-year commitment to specific instance attributes, which makes no sense before real usage is known.
- **b** ❌ Spot Instances can be interrupted with a two-minute warning, which is unsuitable for a customer-facing application that must stay available.
- **c** ✅ On-Demand requires no commitment and lets the team start, stop, and resize freely while measuring the new workload's real usage.
- **d** ❌ Dedicated Hosts allocate an entire physical server for licensing or compliance needs and are the most expensive option, none of which applies here.

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

## Question 5

*Cloud Concepts*

**For years, a company purchased servers based on demand forecasts made two years in advance, and it frequently ended up with idle hardware. After moving to AWS, the company provisions resources for current demand and adjusts them as demand changes. Which advantage of the AWS Cloud does this describe?** Choose one.

- **a.** Stop guessing capacity
- **b.** Benefit from massive economies of scale
- **c.** Go global in minutes
- **d.** Increase speed and agility

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ Correct. The scenario is about replacing long-range demand forecasting and overprovisioning with provisioning for actual demand, which is exactly the stop-guessing-capacity advantage.
- **b** ❌ Economies of scale explains why AWS unit prices are low due to aggregated customer usage; the scenario is about capacity forecasting, not pricing.
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

[← Back to the CLF-C02 study guide](README.md)
