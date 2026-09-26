# Domain 4: Billing, Pricing, and Support (12%)

How you pay for AWS, which tools track that spend, and where to get help. Most questions are matching exercises: spot the cue and pick the option, tool, or plan that fits at the lowest cost.

## 4.1 Compare AWS pricing models

**Core trade-off:** you give up flexibility (time commitment or interruption tolerance) to get a lower rate. The purchasing option changes the rate, not how usage is metered.

| Option | What you commit to | Discount (per lesson) | Pick it when |
| --- | --- | --- | --- |
| On-Demand | Nothing | None, the baseline rate | Usage is unpredictable, short-term, or not yet measured |
| Reserved Instances | 1 or 3 years of specific instance attributes | Up to 72% | Steady, always-on workload with a known instance footprint |
| Savings Plans | 1 or 3 years of $/hour compute spend | Up to 72% | Steady spend, but you want to change instance types or Regions, or you use Fargate/Lambda |
| Spot Instances | Nothing, but AWS can reclaim capacity | Up to 90% | Fault-tolerant, restartable work: batch, CI, analytics, rendering |
| Dedicated Hosts | A whole physical server | None, the most expensive option | BYOL licenses tied to sockets/cores, strict compliance |
| Dedicated Instances | Hardware used only by your account | None (costs more than shared tenancy) | Isolation from other customers without host control |
| Capacity Reservations | Capacity in one AZ, any duration, cancel anytime | None on its own | You must be sure capacity exists when you launch |

**Reserved Instances**
- A billing discount on matching running instances, not something you launch. Unused RIs are still billed.
- Zonal RI also reserves AZ capacity; regional RI is discount-only but applies across the Region.
- Standard RI: deepest discount, cannot change instance family or OS.
- Convertible RI: smaller discount, exchangeable for a different family, type, OS, or tenancy.
- Payment: All Upfront > Partial Upfront > No Upfront in discount size. Three years beats one year.

**Savings Plans**
- Compute Savings Plans: most flexible. Cover any EC2 family, size, OS, tenancy, or Region, plus Fargate and Lambda.
- EC2 Instance Savings Plans: locked to one instance family in one Region, larger discount.
- Usage above the commitment bills On-Demand. No capacity is reserved.

**Spot, isolation, capacity**
- Spot gives a two-minute interruption warning. Never use it for databases or critical, deadline-bound work.
- A Dedicated Instance may move to other hardware after a stop/start. Stack a Capacity Reservation with a Savings Plan or regional RI to get both the discount and the guarantee.

**Consolidated billing effects on price (AWS Organizations)**
- By default, unused RI and Savings Plans discounts flow to matching usage in other accounts (buyer first; the management account can disable sharing per account).
- Pooled usage reaches volume tiers (e.g., S3, data transfer) sooner.

**Data transfer**
- Free: inbound from the internet; same-AZ traffic over private IPs; most EC2-to-service traffic in the same Region (e.g., EC2 to S3).
- Charged: outbound to the internet, cross-Region, and cross-AZ within a Region.
- Rule of thumb: in is free, out is paid, and cost rises with distance.

**Storage tiers**
- Pay per GB-month stored, plus requests, retrievals, and transfer out where they apply.
- Colder tiers have lower storage rates but add retrieval fees, minimum durations, and (for archives such as S3 Glacier) longer waits. Match the tier to how often the data is read.

📖 Full lesson: [AWS Pricing Models Explained: On-Demand, Reserved, Spot & Savings Plans](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-pricing-models/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

## 4.2 Understand resources for billing, budget, and cost management

**Sort the tools by timing:** estimate before you build, get alerts while you spend, analyze afterward, and go to raw data when you need maximum detail.

| Tool | Job | Cue words |
| --- | --- | --- |
| AWS Pricing Calculator | Prices a planned architecture from public rates | estimate, planned migration, compare designs |
| AWS Budgets | Tracks thresholds and sends alerts | alert, notify, threshold, stay under a limit |
| AWS Cost Explorer | Charts and analyzes past spend, forecasts from history | visualize, trends, which service cost most |
| Cost and Usage Report (CUR) | Line-item billing data delivered to S3 | most detailed, granular, line items |
| Consolidated billing | One real bill across Organizations accounts | single bill, many accounts, volume discounts |
| AWS Billing Conductor | Pro-forma bills at custom rates | reseller, chargeback, custom margin |
| Cost allocation tags | Attribute spend to teams/projects | by department, by project, tag |

- **Billing and Cost Management console:** bills, invoices, payment methods, tag activation. Billing and account cases are free on every support plan.
- **Pricing Calculator:** free, and no AWS account is needed. Estimates can be grouped, shared by link, and exported.
- **Budgets:** four budget types: cost, usage, RI/Savings Plans utilization, and RI/Savings Plans coverage.
  - Alerts go by email or Amazon SNS and can fire on **actual** or **forecasted** values.
  - Filters by service, linked account, or tag.
  - Budget actions can respond automatically (for example, attach a restrictive IAM policy or stop EC2/RDS instances).
  - Related: Free Tier usage alerts; CloudWatch billing alarms (the older method).
- **Cost Explorer:** group by service, account, Region, instance type, purchase option, or tag. Forecasts come from history (unlike the calculator). Surfaces rightsizing and RI/Savings Plans recommendations.
- **CUR:** per-resource, per-hour detail with tags as columns. Refreshed at least daily in your S3 bucket. Query it with Athena and visualize with QuickSight or Redshift. It is now delivered through Data Exports (CUR 2.0).
- **Consolidated billing:** also itemizes per account and costs nothing. **Billing Conductor** uses billing groups and custom pricing rules; the real AWS charge is unchanged.
- **Cost allocation tags:**
  - AWS-generated (`aws:` prefix, e.g., `aws:createdBy`, not editable) vs user-defined (`user:` prefix in billing data).
  - Tags must be **activated** in the Billing console first. They can take up to 24 hours to appear and do not apply to usage from before activation.
  - Once active, they appear in Cost Explorer, CUR, and Budgets filters. Cost categories group costs by rules.

📖 Full lesson: [AWS Billing and Cost Management Tools: Budgets, Cost Explorer, CUR and More](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-billing-and-cost-management-tools/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

## 4.3 Identify AWS technical resources and AWS Support options

**Self-service resources (free, public, no support plan needed)**

| Resource | Go there for |
| --- | --- |
| AWS Documentation | Service guides, API references, and tutorials |
| AWS Whitepapers | In-depth papers on architecture, security, economics, and migration (e.g., Well-Architected Framework) |
| AWS Blogs | Launch news, feature deep dives, and walkthroughs |
| AWS Prescriptive Guidance | Proven strategies and patterns from AWS experts and Partners |
| AWS Knowledge Center | Answers to the most common support questions (hosted on re:Post) |
| AWS re:Post | Community Q&A, the replacement for AWS Forums |

**Support plans** (each tier includes everything in the tiers below it)

| Feature | Basic | Developer | Business | Ent. On-Ramp | Enterprise |
| --- | --- | --- | --- | --- | --- |
| Cost | Free | Paid | Paid | Paid | Paid |
| Technical cases | No | Business-hours email | 24/7 phone, email, chat | 24/7 phone, email, chat | 24/7 phone, email, chat |
| Trusted Advisor | Core checks | Core checks | Full checks | Full checks | Full checks |
| AWS Health API | No | No | Yes | Yes | Yes |
| Fastest response (per lesson) | None | Impaired system <12 business hrs | Production down <1 hr | Business-critical down <30 min | Business-critical down <15 min |
| TAM | No | No | No | Shared pool | Designated |
| Other extras | Account/billing customer service 24/7 | Lowest-cost technical support | Suited to production | Annual consultative review | Concierge Support Team, Well-Architected reviews, game days, Infrastructure Event Management |

- **Choose the cheapest plan that meets the need.** A higher tier also qualifies but is wrong because it costs more. "Designated" TAM means Enterprise only.
- **Trusted Advisor:** best-practice checks across cost optimization, performance, security, fault tolerance, service limits, and operational excellence.
- **AWS Health Dashboard:** public service status plus a personal view of events and maintenance affecting your resources, for all accounts. The Health API exposes the same data from Business upward.
- **Trust & Safety:** report spam, DoS, malware, phishing, or intrusions from AWS resources via the abuse form or email, with IPs, timestamps, and logs. No account needed; not a support case.
- **AWS Partner Network:** ISVs build software; system integrators (consulting partners) design, migrate, and manage workloads. Partner benefits: training, enablement, go-to-market, funding.
- **AWS Marketplace:** buy and deploy third-party software, billed on your AWS bill.
- **People:** Solutions Architect = advises on design; Professional Services = paid consulting that delivers projects; TAM = ongoing operational advocate.
- **AWS Support Center:** the console page for opening cases and reaching customer service.

📖 Full lesson: [AWS Support Plans and Technical Resources: The Complete CLF-C02 Guide](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-support-plans-and-technical-resources/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

[← Back to the study guide](../README.md)
