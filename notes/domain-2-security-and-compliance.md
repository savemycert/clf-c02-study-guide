# Domain 2: Security and Compliance (30%)

The second-largest domain on CLF-C02. Most questions are quick recognition items: who owns a given security task, which service fits a stated need, or which IAM identity suits a scenario.

## 2.1 Understand the AWS shared responsibility model

- **AWS = security OF the cloud**: data center physical security, hardware (including disposal of retired media), the global network (Regions, AZs, edge locations), host OS, and the hypervisor.
- **Customer = security IN the cloud**: your data, IAM (users, roles, permissions, MFA), guest OS on EC2, security group and NACL rules, service settings, and encryption choices.
- The line moves with the service type. The more managed the service, the more operational work AWS takes on.

| Task | EC2 | RDS | Lambda | S3 |
|---|---|---|---|---|
| Facilities, hardware, hypervisor | AWS | AWS | AWS | AWS |
| OS patching | Customer | AWS | AWS | AWS (no OS exposed) |
| Engine / runtime | Customer | AWS | AWS | AWS |
| Code, schema, settings | Customer | Customer | Customer | Customer |
| Data, IAM, encryption choices | Customer | Customer | Customer | Customer |

- **Three control types:**
  - *Inherited*: AWS runs them fully (physical and environmental controls).
  - *Shared*: both parties act at their own layer. Memorize three: **patch management, configuration management, awareness and training**.
  - *Customer-specific*: only the customer acts (data classification, protecting data contents, routing traffic within required zones).
- **Two absolutes:** data is always the customer's; physical infrastructure is always AWS's. Reject any option that contradicts either one.
- **Cues:**
  - "Security OF the cloud" → AWS. "IN the cloud" → customer.
  - "Patch the OS" → check the named service first (EC2 = customer; RDS/Lambda = AWS).
  - "Moving from EC2 to RDS transfers what?" → OS and database engine patching, never data or IAM.
- **Trap:** "managed" does not hand over your data, IAM, or firewall rules. An RDS database set to publicly accessible is a customer error.

📖 Full lesson: [AWS Shared Responsibility Model: Security OF the Cloud vs IN the Cloud](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-shared-responsibility-model/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

## 2.2 Understand AWS Cloud security, governance, and compliance concepts

- **AWS Artifact**: a no-cost console portal for *AWS's own* compliance documents.
  - *Artifact Reports*: third-party audit reports such as SOC 1/2/3, PCI DSS attestations, and ISO certifications.
  - *Artifact Agreements*: accept and manage agreements with AWS, for example the HIPAA Business Associate Addendum (BAA).
  - It proves that AWS's side is compliant. Proving that your own workload is compliant is still your job.
- **Why compliance differs between customers:**
  - *Geography*: data residency and data protection law (GDPR). You choose the Region, and data stays there unless you move it. AWS GovCloud (US) serves US government workloads.
  - *Industry*: HIPAA (US healthcare), PCI DSS (card payments), FedRAMP (public sector).
  - *Service*: each compliance program has a services-in-scope list. HIPAA workloads must use HIPAA-eligible services.
- **Encryption:**
  - *At rest* = stored data (S3, EBS, RDS, DynamoDB). Uses **KMS**. **CloudHSM** provides dedicated single-tenant hardware key storage.
  - *In transit* = moving data. Uses **TLS/HTTPS**, with certificates from **ACM** on ELB and CloudFront.
  - The two are complementary, not alternatives.
- **Where security logs are stored:**
  - CloudTrail: event history in the console, plus a trail delivered to S3 (optionally also to CloudWatch Logs).
  - VPC Flow Logs: sent to CloudWatch Logs or S3.
  - S3 server access logs: sent to another S3 bucket.
  - The pattern: **S3 for long-term archive, CloudWatch Logs for live search and alarms.**
- **Services that secure resources:**
  - **GuardDuty**: detects active threats by analyzing CloudTrail, VPC Flow Logs, and DNS logs. Agentless.
  - **Inspector**: scans EC2, ECR images, and Lambda for CVEs and unintended network exposure.
  - **Security Hub**: aggregates findings from other tools and runs best-practice standard checks. It does not detect threats itself.
  - **Shield**: DDoS protection. Standard is automatic and free. Advanced is paid and adds the Shield Response Team, attack visibility, and cost protection.
- **Governance services, one question each:**

| Service | Answers |
|---|---|
| CloudWatch | How is it performing? (metrics, logs, alarms) |
| CloudTrail | Who did what, when, from where? (API calls) |
| Config | What did the resource look like, and is it compliant? (config history, rules) |
| Audit Manager | Collect evidence for *my* audit against a framework |

- IAM access reports (the credential report and last-accessed data) support access reviews.
- **Cues:**
  - "Download a SOC/PCI report" → Artifact.
  - "Who deleted the security group?" → CloudTrail.
  - "Alert when a bucket becomes public" → Config.
  - "CPU alarm" → CloudWatch.

📖 Full lesson: [AWS Security, Governance, and Compliance Concepts for CLF-C02](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-security-governance-and-compliance/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

## 2.3 Identify AWS access management capabilities

- IAM is **global** (not tied to a Region) and **free**.
- *Authentication* asks who you are (passwords, keys, MFA). *Authorization* asks what you may do (policies).
- IAM denies by default, and an explicit deny beats any allow.

| Identity | Credentials | Pick it when |
|---|---|---|
| User | Long-term password and/or access keys | One person needs ongoing sign-in |
| Group | None (it cannot sign in, and groups cannot nest) | Many people share one job function |
| Role | Temporary, auto-rotated | EC2/Lambda apps, cross-account access, federation |
| Policy | N/A (a JSON document) | Defining allowed or denied actions |

- **Policy types:**
  - *AWS managed*: prebuilt and broad. You cannot edit them.
  - *Customer managed*: you write them, they are reusable, and they are precise. This is the least-privilege pick.
  - *Inline*: embedded in a single identity and not reusable.
  - *Identity-based* policies attach to a user, group, or role. *Resource-based* policies attach to a resource such as an S3 bucket.
- **Least privilege**: grant only what the job needs. If two answers both work, choose the narrower one. It limits the damage from a leaked credential.
- **Root user**: unrestricted, and IAM policies cannot limit it.
  - *Protect it*: MFA, a strong password, no access keys, an IAM admin for daily work, a secure recovery email and phone, and monitoring for root sign-ins.
  - *Root-only tasks*: close the account; change the account name, root email, or root password; change or cancel the Support plan; some tax and billing settings; recover from a bucket policy that locks everyone out; register as a Reserved Instance Marketplace seller.
- **Credentials:**
  - *MFA*: authenticator apps, security keys, hardware tokens.
  - *Access keys*: for CLI/SDK/API use only. Rotate them, never put them in code, and delete unused ones.
  - *Password policy*: sets length, complexity, expiry, and reuse rules.
- **Scenarios:**
  - "App on EC2 needs S3 access" → **IAM role**. Stored access keys are always the wrong answer.
  - "Access resources in another account" → **cross-account role**.
  - "Sign in with corporate credentials" → **federation**.
  - "Many accounts, one portal, single sign-on" → **IAM Identity Center** (formerly AWS SSO).
- **Storing secrets:**
  - *Secrets Manager*: stores secrets and **rotates them automatically**.
  - *Systems Manager Parameter Store*: config values and secure strings, with no built-in rotation.

📖 Full lesson: [AWS IAM Explained: Users, Groups, Roles, Policies & Root User Best Practices](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-iam-access-management/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

## 2.4 Identify components and resources for security

- **Layers:** a NACL checks traffic at the subnet edge, then a security group checks it at the instance (ENI). AWS WAF inspects HTTP(S) content at layer 7 at the entry point.

| | Security group | Network ACL |
|---|---|---|
| Scope | Instance / ENI | Subnet |
| State | Stateful (return traffic allowed automatically) | Stateless (return traffic needs its own rules) |
| Rules | Allow only | Allow and deny |
| Evaluation | All rules evaluated | Numbered order, first match wins |
| Default | New SG: no inbound, all outbound | Default NACL allows all; a custom NACL denies all |

- A security group rule can reference another security group as its source (for example, the DB accepts traffic only from the web-tier SG).
- **Cues:**
  - "Block a specific IP range" → NACL, because security groups cannot deny.
  - "Stateful" → security group.
  - "SQL injection / XSS" → **AWS WAF**. It uses web ACLs, attaches to CloudFront, ALB, and API Gateway, and supports managed rule groups.
  - "DDoS" → Shield, not WAF.
- **AWS Marketplace**: third-party security products (firewalls, endpoint protection, SIEM, scanners). Pricing can be trial, pay-as-you-go, annual, or BYOL, and charges land on your AWS bill.
- **Where to find security information:**
  - *Knowledge Center* (on re:Post): short answers to common Support questions.
  - *Security Blog*: announcements and deep dives.
  - *Security Center*: the AWS Cloud Security site, with whitepapers, compliance information, and security bulletins.
- **Trusted Advisor**: checks your account against best practices in the cost, performance, security, fault tolerance, service limits, and operational excellence categories.
  - Security checks flag open security groups, public S3 buckets, no MFA on root, and public snapshots.
  - Core checks are free. The full set needs Business, Enterprise On-Ramp, or Enterprise Support.
  - **Trap:** it checks configuration only. It is not a threat detector or a vulnerability scanner.

📖 Full lesson: [AWS Security Components: Security Groups vs Network ACLs, WAF, Trusted Advisor](https://www.savemycert.com/revision/aws-cloud-practitioner/aws-security-components-and-resources/?utm_source=github&utm_medium=readme&utm_campaign=clf-c02-study-guide)

[← Back to the study guide](../README.md)
