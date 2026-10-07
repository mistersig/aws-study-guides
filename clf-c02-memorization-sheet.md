# AWS Certified Cloud Practitioner (CLF-C02) — Master Memorization Sheet

Every enumerated list and distinction the exam expects you to recall cold. Drill by covering the right column and reciting — not by rereading.

Acronyms: AWS = Amazon Web Services throughout. Each service acronym is spelled out on first appearance in its section.

---

# START HERE — WHAT TO STUDY, IN PRIORITY ORDER

The exam guide lists dozens of in-scope services. You do not need them all equally. Everything in this document sorts into three tiers.

## Tier 1 — must know cold

These carry the majority of the exam. If time is short, this tier is the whole plan.

| Topic | Where in this document |
|---|---|
| **Shared Responsibility Model** — what AWS secures vs. what you secure, and how the line slides | §2.1, §2.1a |
| **IAM** — users, groups, roles, policies, least privilege, Multi-Factor Authentication, root user | §2.2, §2.2a, §2.2b |
| **EC2 and Lambda** — virtual machine vs. serverless, instance types, Auto Scaling, load balancing | §3.5, §3.5a, §3.5c |
| **S3 and EBS** — object vs. block storage, S3 storage classes, lifecycle policies | §3.3a, §3.4 |
| **RDS, DynamoDB, Aurora, ElastiCache** — relational vs. non-relational, and when each fits | §3.6, §3.6a, §3.6b |
| **VPC basics** — subnets, security groups vs. network ACLs, public vs. private subnets, internet gateways | §2.4, §3.7a |
| **Global infrastructure** — Regions, Availability Zones, edge locations; how to achieve high availability | §3.1 |
| **Pricing models** — On-Demand, Reserved, Savings Plans, Spot, and when each makes sense | §3.2, §3.3 |

## Tier 2 — understand conceptually

You will see questions on these, but not at Tier 1 depth.

| Topic | Where |
|---|---|
| **Well-Architected Framework** and its six pillars | §1.3, §1.4, §1.5 |
| **CloudWatch, CloudTrail, AWS Config** — metrics vs. who-did-what vs. is-it-compliant | §2.3 |
| **Route 53 and CloudFront** | §3.7 |
| **SNS and SQS** — messaging and decoupling | §3.8 |
| **KMS** and encryption | §2.0, §2.3 |
| **AWS Organizations** and consolidated billing | §3.9a, §4.5 |
| **Migration strategies** (the seven Rs), **Snow Family**, **Direct Connect** | §1.2, §3.4a, §3.7 |
| **Cloud Adoption Framework** | §1.6, §1.7 |
| **Support plans and cost tools** | §4.3, §4.4 |

## Tier 3 — awareness level only

Know what each service does in one line. A couple of questions at most — but note that **AWS now explicitly tests AI and machine learning services**, so do not skip this tier entirely. Your own score report has a task line for it (Task 3.7).

| Topic | Where |
|---|---|
| **SageMaker, Lex, Kendra, Amazon Q, Bedrock** and the purpose-built AI services | §3.11 |
| **ECS, EKS, Fargate** — containers | §3.5b |
| **DocumentDB, Keyspaces, Neptune, Redshift** | §3.6, §3.6a |
| **Step Functions, EventBridge, Kinesis** | §3.8 |
| **Athena, Glue, EMR, QuickSight** and the analytics family | §3.10 |
| **Connect, WorkSpaces, Amplify, Cognito** and the business services | §3.9b, §3.9c |

**The mindset:** this is a foundational certification. You are being tested on *what a service does and when you would pick it over another* — not on how to build with it. Depth is not the goal; coverage and discrimination are.

## How this document is organized

| Part | Contents |
|---|---|
| **Part 1** | The frameworks — pure recall lists (advantages, seven Rs, Well-Architected, Cloud Adoption Framework) |
| **Part 2** | Security and compliance — 30% of the exam, the largest single domain |
| **Part 3** | Technology and services — 34% of the exam, organized by the Core Four (§3.0) |
| **Part 4** | Billing, pricing and support — 12%, the most memorizable domain |
| **Part 5** | Concept pairs that get swapped — the single highest-value page if you only read one |
| **Sources** | What this was built from, and where sources were out of date |

## If you have only 48 hours

1. **Part 5** — the concept-pair table. Every distinction the exam turns on, in one page.
2. **§2.1 and §2.1a** — shared responsibility. The largest domain's foundation.
3. **§4.3 and §4.4** — support plans and cost tools. Pure memorization, fastest points available.
4. **§1.3 through §1.7** — the framework lists. Also pure recall, also fast.
5. Everything else, by tier order above.

---

# PART 1 — THE FRAMEWORKS (highest yield, pure recall)

## 1.1 The Six Advantages of Cloud Computing

| # | Advantage | Trigger words |
|---|---|---|
| 1 | Trade capital expense for variable expense | upfront cost, own hardware, pay only for what you use |
| 2 | Benefit from massive economies of scale | lower price per unit, AWS purchasing power, cheaper than we could |
| 3 | Stop guessing capacity | forecast, predict, over-provision, under-provision, idle servers |
| 4 | Increase speed and agility | minutes instead of weeks, experiment faster, innovate |
| 5 | Stop spending money running and maintaining data centers | racking, stacking, powering servers, focus on customers |
| 6 | Go global in minutes | deploy to multiple Regions, worldwide, low latency globally |

**The trap:** #2 and #3 both feel right. If the stem mentions *price*, it's #2. If it mentions *forecasting*, it's #3. No dollars in the stem = not the money answer.

## 1.2 The Seven Rs of Migration

| R | What it means | Signal |
|---|---|---|
| **Rehost** | Lift and shift, no changes | fastest, no code change, deadline, exit data center |
| **Replatform** | Lift, tinker, shift — minor optimization | move to managed database, small change, no core rewrite |
| **Repurchase** | Drop and shop — move to a different product | move to software as a service, buy instead of build |
| **Refactor / Re-architect** | Rewrite for cloud-native | most benefit, most cost, most time, microservices, serverless |
| **Retire** | Decommission — turn it off | no longer needed, unused, redundant |
| **Retain** | Do nothing for now — revisit later | not ready, recently upgraded, compliance blocker |
| **Relocate** | Move infrastructure wholesale without changes | VMware to AWS, move hypervisor-level |

**The trap:** Rehost vs. Refactor. Refactor sounds like the "best practice" answer and often is *wrong* — any mention of speed, deadline, or no-code-change means Rehost.

## 1.3 Well-Architected Framework — The Six GENERAL Design Principles

These are separate from the pillars. This distinction is a known exam trap.

1. Stop guessing your capacity needs
2. Test systems at production scale
3. Automate to make architectural experimentation easier
4. Allow for evolutionary architectures
5. Drive architectures using data
6. Improve through game days

**Memory hook: S-T-A-A-D-I** — Stop, Test, Automate, Allow, Drive, Improve.

## 1.4 Well-Architected Framework — The Six Pillars

| Pillar | One-line purpose |
|---|---|
| **Operational Excellence** | Run and monitor workloads; continuously improve processes and procedures |
| **Security** | Protect data, systems, and assets |
| **Reliability** | Recover from failure; meet demand; mitigate disruption |
| **Performance Efficiency** | Use computing resources efficiently as demand and technology change |
| **Cost Optimization** | Deliver business value at the lowest price point |
| **Sustainability** | Minimize environmental impact of cloud workloads |

**Memory hook: OSRPCS** — "Operations Secure Reliable Performance Costs Sustainably."

**A correction for older study material:** many slides, videos and books still say the framework has **five** pillars. It has **six**. **Sustainability** was added in 2021 and is fully testable on CLF-C02. If an answer choice offers five pillars or omits Sustainability, it is out of date.

## 1.5 Design Principles WITHIN Each Pillar

### Operational Excellence (5)
1. Perform operations as code
2. Make frequent, small, reversible changes
3. Refine operations procedures frequently
4. Anticipate failure
5. Learn from all operational failures

### Security (7)
1. Implement a strong identity foundation
2. Maintain traceability
3. Apply security at all layers
4. Automate security best practices
5. Protect data in transit and at rest
6. Keep people away from data
7. Prepare for security events

### Reliability (5)
1. Automatically recover from failure
2. Test recovery procedures
3. Scale horizontally to increase aggregate workload availability
4. Stop guessing capacity
5. Manage change through automation

### Performance Efficiency (5)
1. Democratize advanced technologies
2. Go global in minutes
3. Use serverless architectures
4. Experiment more often
5. Consider mechanical sympathy (use the technology that best matches the goal)

### Cost Optimization (5)
1. Implement Cloud Financial Management
2. Adopt a consumption model
3. Measure overall efficiency
4. Stop spending money on undifferentiated heavy lifting
5. Analyze and attribute expenditure

### Sustainability (6)
1. Understand your impact
2. Establish sustainability goals
3. Maximize utilization
4. Anticipate and adopt new, more efficient hardware and software offerings
5. Use managed services
6. Reduce the downstream impact of your cloud workloads

**The three collisions to watch:**
- "Stop guessing capacity" appears as BOTH a general design principle AND a Reliability pillar principle.
- "Go global in minutes" is BOTH an advantage of cloud AND a Performance Efficiency principle.
- "Test recovery procedures" is Reliability only — NOT a general principle.

## 1.6 Cloud Adoption Framework (CAF) — The Six Perspectives

| Perspective | Focus | Stakeholders |
|---|---|---|
| **Business** | Ensure cloud investments accelerate business outcomes | Chief Executive Officer, Chief Financial Officer, Chief Information Officer, Chief Operating Officer |
| **People** | Culture, skills, change management — bridge technology and business | Chief Information Officer, Human Resources, people managers |
| **Governance** | Orchestrate initiatives; maximize benefit, minimize risk | Chief Information Officer, Chief Transformation Officer, program and project managers, enterprise architects, business analysts |
| **Platform** | Build an enterprise-grade, scalable, hybrid cloud environment | Chief Technology Officer, technology leaders, architects, engineers |
| **Security** | Confidentiality, integrity, availability of data and workloads | Chief Information Security Officer, security architects, security engineers |
| **Operations** | Deliver cloud services to the agreed service level | Infrastructure and operations leaders, site reliability engineers, IT service managers |

**Memory hook: B-P-G-P-S-O** — "Business People Govern Platforms Securely, Operationally."

**Alternate stakeholder wording you may see.** AWS has published the perspectives with slightly different stakeholder lists across framework versions, and questions draw on both. The additional names worth recognizing:

| Perspective | Also listed as |
|---|---|
| Business | Business managers, finance managers, budget owners, strategy stakeholders |
| People | Human Resources, staffing, people managers |
| Governance | Chief Information Officer, program managers, project managers, enterprise architects, business analysts |
| Platform | Chief Technology Officer, IT managers, solutions architects |
| Security | Chief Information Security Officer, IT security managers, IT security analysts |
| Operations | IT operations managers, IT support managers |

The perspectives are also sometimes called the **six focus areas** — same thing.

**Stakeholder shortcuts:** Chief Financial Officer → Business. Human Resources → People. Chief Technology Officer / architects / engineers → Platform. Chief Information Security Officer → Security. Chief Information Officer appears in several, so it is rarely the deciding clue.

## 1.7 Cloud Adoption Framework — The Four Phases (IN ORDER)

| # | Phase | What happens |
|---|---|---|
| 1 | **Envision** | Identify and prioritize transformation opportunities; tie them to measurable business outcomes; application portfolio management |
| 2 | **Align** | Identify capability gaps and cross-organizational dependencies; build stakeholder alignment; create the cloud readiness plan |
| 3 | **Launch** | Deliver pilots **in production**; demonstrate incremental business value |
| 4 | **Scale** | Expand proven pilots to the desired scale; **sustain** the realized business benefits |

**The trap that got you twice:** Launch vs. Scale. **Launch = the first pilots reach production.** **Scale = proven pilots expand and the value is sustained.** If the word "pilot" is still in the sentence, it's Launch. If pilots are being *expanded* or value *sustained*, it's Scale.

---

# PART 2 — SECURITY AND COMPLIANCE

## 2.0 Security Foundations — CIA, Encryption, and Compliance

### The CIA triad

The model underlying all security thinking, and the source of several exam distractors.

| Principle | Means | In practice on AWS |
|---|---|---|
| **Confidentiality** | Protecting data from unauthorized viewers | Encryption with cryptographic keys; **envelope encryption** (using keys to encrypt keys) |
| **Integrity** | Keeping data accurate and complete over its whole lifecycle | Transactional databases; tamper-evident hardware security modules |
| **Availability** | Information is there when it is needed | High availability design, mitigating Distributed Denial of Service attacks |

### Cryptographic keys

| Type | How it works | Example algorithm |
|---|---|---|
| **Symmetric** | **One key** encrypts and decrypts | Advanced Encryption Standard (AES) |
| **Asymmetric** | **Two keys** — one encrypts, the other decrypts | Rivest–Shamir–Adleman (RSA) |

### Hardware security modules and FIPS

A **hardware security module (HSM)** is physical hardware built to store encryption keys, holding them in memory and never writing them to disk. **FIPS** (Federal Information Processing Standard) is the United States and Canadian government standard for cryptographic modules.

| Tenancy | FIPS level | AWS service |
|---|---|---|
| **Multi-tenant** (customers virtually isolated on shared hardware) | FIPS 140-2 **Level 2** | **AWS KMS** (Key Management Service) |
| **Single-tenant** (one customer on dedicated hardware) | FIPS 140-2 **Level 3** | **AWS CloudHSM** |

**The discriminator:** if a stem requires a **dedicated, single-tenant** hardware security module or names FIPS 140-2 Level 3, the answer is **CloudHSM**. Otherwise key management is **KMS**.

### Compliance programs worth recognizing

A compliance program is a set of policies and procedures for meeting laws, rules, and regulations.

| Program | Covers |
|---|---|
| **HIPAA** (Health Insurance Portability and Accountability Act) | United States legislation protecting medical information |
| **PCI DSS** (Payment Card Industry Data Security Standard) | Handling credit card information — selling online |
| **SOC** (System and Organization Controls) | Audit reports on service organization controls |
| **FedRAMP** | United States federal government cloud authorization |
| **GDPR** (General Data Protection Regulation) | European Union data privacy |
| **ISO 27001**, **NIST**, **ITAR**, **CJIS**, **FIPS** | Other standards AWS attests to |

You obtain AWS's reports for all of these from **AWS Artifact** (section 2.3).

## 2.1 Shared Responsibility Model

| AWS ("security OF the cloud") | Customer ("security IN the cloud") |
|---|---|
| Physical data centers and facilities | Customer data |
| Hardware and global infrastructure | Identity and Access Management configuration |
| Networking infrastructure | Operating system, network, and firewall configuration (on unmanaged services) |
| Virtualization / hypervisor layer | Client-side and server-side encryption choices |
| Managed service patching (RDS, Lambda, S3, DynamoDB) | Application code, platform, and access management |

**Never leaves the customer, on any service:** your data, your Identity and Access Management configuration, your data classification.

**The sliding-line trap:** operating system patching is the CUSTOMER's on Amazon Elastic Compute Cloud (EC2), and AWS's on Amazon Relational Database Service (RDS). Same task, opposite answer.

## 2.1a Shared Responsibility Across the Compute Service Models

The single best way to internalize the sliding line. As you move down this table, the customer's share shrinks and AWS's grows.

### Infrastructure as a Service (IaaS)

| Offering | Customer manages | AWS manages |
|---|---|---|
| **Bare Metal** (EC2 Bare Metal instance) | Host operating system configuration, hypervisor | Physical machine |
| **Virtual Machine** (Amazon EC2) | Guest operating system configuration, container runtime (if containers are run on it) | Hypervisor, physical machine |
| **Containers** (Amazon Elastic Container Service) | Container configuration, deployment, container storage | Operating system, hypervisor, container runtime |

### Platform as a Service (PaaS)

| Offering | Customer manages | AWS manages |
|---|---|---|
| **Managed platform** (AWS Elastic Beanstalk) | Uploading code, some environment configuration, deployment strategies, configuration of associated services | Servers, operating system, networking, storage, security |

### Software as a Service (SaaS)

| Offering | Customer manages | AWS manages |
|---|---|---|
| **Content collaboration** (a managed software-as-a-service application) | Contents of documents, management of files, configuration of sharing and access controls | Servers, operating system, networking, storage, security |

### Function as a Service (FaaS)

| Offering | Customer manages | AWS manages |
|---|---|---|
| **Functions** (AWS Lambda) | Upload your code — that is the entire customer scope | Deployment, container runtime, networking, storage, security, physical machine — essentially everything else |

**The one-sentence version:** Bare Metal → the customer owns nearly everything above the physical machine. Lambda → the customer owns only the code. Everything else falls between those two poles.

**Two corrections to the slide this came from:**
1. EC2 stands for **Elastic Compute Cloud**, not "Elastic Cloud Compute." The exam uses the correct expansion.
2. AWS owns the container instance operating system only on **AWS Fargate**. With Elastic Container Service or Elastic Kubernetes Service on the **EC2 launch type**, the customer still patches the underlying instances. If a question mentions Fargate, compute responsibility shifts to AWS; if it mentions EC2 launch type, it does not.

## 2.2 Identity and Access Management (IAM) Components

| Component | Purpose |
|---|---|
| **Root user** | Created with the account; full access; secure with Multi-Factor Authentication and never use for daily work |
| **IAM user** | Persistent identity with long-lived credentials |
| **IAM group** | Collection of users sharing permissions |
| **IAM role** | Temporary credentials that are assumed — used by services, applications, and cross-account access |
| **IAM policy** | JSON document defining permissions (allow or deny) |
| **IAM Identity Center** | Centralized single sign-on across multiple AWS accounts |

**The universal reflex:** anything accessing anything else gets a **role**. Any answer mentioning stored access keys, embedded credentials, or root user credentials is wrong.

## 2.2a The AWS Account Root User

Three things to keep straight:

| Term | What it is |
|---|---|
| **AWS account** | The container holding all your AWS resources |
| **Root user** | The special identity created **when the account is created**. Full access, cannot be deleted, one per account |
| **IAM user** | An identity you create for everyday tasks, with permissions you assign |

### Key facts

- The root user signs in with an **email address and password**. A regular IAM user signs in with an **account ID or alias, username, and password**. That difference occasionally appears as an answer choice.
- The root user **cannot be deleted**, and there is exactly **one per account**.
- The root user has full permissions that **cannot be limited by an IAM policy** — you cannot write an IAM policy that denies the root user. The only way to constrain it is an **AWS Organizations service control policy (SCP)**.
- It should be used only for rare, specialized tasks — **never for daily work**.
- Two strong recommendations: **never create or use root user access keys**, and **enable Multi-Factor Authentication (MFA) on the root user**.

### Tasks ONLY the root user can perform

This list is exam material. The ones in bold come up most:

- **Change account settings** — account name, email address, root user password, root user access keys. (Contact information, payment currency, and Region enablement do *not* require root.)
- **Restore IAM user permissions** — if the only IAM administrator revokes their own access, root is the way back in
- **Close the AWS account**
- **Change or cancel the AWS Support plan**
- Activate IAM access to the Billing and Cost Management console
- View certain tax invoices
- Register as a seller in the Reserved Instance Marketplace
- Enable MFA Delete on an S3 bucket
- Edit or delete an S3 bucket policy containing an invalid VPC or VPC endpoint ID
- Sign up for AWS GovCloud

**The pattern:** root is required for anything that affects **the account itself** — its identity, its billing relationship, its existence — rather than the resources inside it. If a stem describes changing account-level settings, closing the account, or changing the support plan, the answer is the root user. If it describes anything operational, the answer is an IAM user or role.

## 2.2b Principle of Least Privilege

**Grant a user, role, or application the minimum permissions needed to perform its task** — nothing more. This is the safe default answer to any vague IAM question.

Two dimensions it operates on:

| Concept | Meaning |
|---|---|
| **Just-Enough-Access (JEA)** | Permit only the exact **actions** the identity needs |
| **Just-In-Time (JIT)** | Permit those actions for the shortest **duration** necessary |

Least privilege is why **IAM roles** are preferred over users for service-to-service access: roles deliver temporary credentials, which satisfies both dimensions at once — scoped actions and a limited lifetime.

**Two items on the slide this came from that are NOT exam material:** **ConsoleMe** is an open-source Netflix project, not an AWS service, and **risk-based adaptive policies** are a general security concept that AWS IAM does not implement (the slide says so itself). Neither will appear as a correct answer. Skip both.

## 2.3 The Security Service Zoo

| Service | One-line job |
|---|---|
| **Amazon GuardDuty** | Threat detection from log analysis — **behavior** |
| **Amazon Inspector** | Vulnerability scanning of workloads — **software** |
| **Amazon Macie** | Finds sensitive data in Amazon Simple Storage Service (S3) — **data** |
| **AWS Security Hub** | Aggregates findings from all of the above |
| **AWS Artifact** | Downloads AWS's own compliance reports (SOC, ISO, PCI DSS) |
| **AWS Audit Manager** | Assesses YOUR workloads against a compliance framework |
| **AWS Config** | Records resource configuration over time; evaluates compliance |
| **AWS CloudTrail** | Logs who made which application programming interface call, when |
| **Amazon CloudWatch** | Metrics, logs, alarms — performance and operational health |
| **AWS Trusted Advisor** | Best-practice recommendations across five categories |
| **AWS Key Management Service** | Creates and manages encryption keys |
| **AWS CloudHSM** | Dedicated single-tenant hardware security module |
| **AWS Secrets Manager** | Stores AND automatically rotates credentials |
| **AWS Certificate Manager** | Free Transport Layer Security / Secure Sockets Layer certificates |
| **AWS Web Application Firewall** | Blocks SQL injection, cross-site scripting at layer 7 |
| **AWS Shield** | Distributed Denial of Service protection (Standard free, Advanced paid) |
| **AWS Firewall Manager** | Centrally manages Web Application Firewall, Shield Advanced, Network Firewall rules across accounts |
| **AWS Network Firewall** | Stateful firewall at the whole Virtual Private Cloud perimeter |

**Trusted Advisor's five categories:** Cost Optimization, Performance, Security, Fault Tolerance, Service Limits (Service Quotas).

## 2.4 Security Groups vs. Network Access Control Lists

| | Security group | Network ACL |
|---|---|---|
| Level | Resource (attached to network interface) | Subnet |
| State | **Stateful** (return traffic auto-allowed) | **Stateless** (return traffic must be allowed explicitly) |
| Rules | **Allow only** | Allow **and deny** |
| Evaluation | All rules evaluated together | In numbered order, first match wins |
| Default | Deny all inbound, allow all outbound | Default NACL allows all |

**The discriminator:** if the question needs to **block** a specific address, it must be a Network ACL — security groups cannot express deny.

**Why security groups can't deny:** a security group **implicitly denies all traffic** and you then write only **allow** rules to open holes in it. There is no deny rule to write, because everything not explicitly allowed is already blocked. A network ACL, by contrast, lets you write both allow and deny rules, evaluated in number order.

| Example task | Answer |
|---|---|
| Allow an EC2 instance to accept Secure Shell (SSH) connections on port 22 | **Security group** |
| Block a specific IP address known for abuse | **Network ACL** |
| Let the application tier accept traffic only from the web tier | **Security group** (a security group can reference another security group) |
| Apply one rule set to everything in a subnet at once | **Network ACL** |

**One capability only security groups have:** a security group can **reference another security group** as its source. That's how tiered architectures are built — the application tier's rule says "allow from the web tier's security group," so anything not in the web tier is denied automatically, without managing IP addresses.

---

# PART 3 — TECHNOLOGY AND SERVICES

## 3.0 The Core Four — how to hold the service catalog in your head

Before the individual services, the four categories everything sits in:

| Category | The question it answers | The services |
|---|---|---|
| **Compute** | Raw processing power — *where does my application run?* | EC2, Lambda, ECS, EKS, Fargate, Elastic Beanstalk, Lightsail, Batch |
| **Networking** | How everything connects — *how do requests reach it and move between parts?* | VPC, Route 53, CloudFront, Elastic Load Balancing, Direct Connect, Site-to-Site VPN, Global Accelerator, API Gateway |
| **Storage** | Where your data lives | S3, EBS, EFS, FSx, Storage Gateway, Snowball Edge, AWS Backup — plus the databases: RDS, Aurora, DynamoDB, Redshift |
| **Security** | Who is allowed to do what | IAM, Cognito, security groups, network ACLs, KMS, Secrets Manager, WAF, Shield, GuardDuty, Inspector, Macie |

**Why this helps on the exam:** a scenario question is almost always asking about one of these four. Identify the category first and the candidate list drops from sixty services to roughly eight. Only then compare within the category.

The longer version of the same idea is the **six questions** to ask of any architecture:

1. Where does my application run? → **Compute**
2. Where does it store data? → **Storage and databases**
3. How does it communicate? → **Networking and integration**
4. How does traffic get distributed? → **Load balancing and scaling**
5. Who has access? → **Identity and network security**
6. How do I know when something goes wrong? → **Observability** (CloudWatch, CloudTrail, Config)

Question six is the one worth drilling, because CloudWatch, CloudTrail and Config are three of the most-confused services on the exam and they all live in the same bucket. Metrics versus who-did-what versus is-it-compliant.

## 3.1 Global Infrastructure

| Component | Definition |
|---|---|
| **Region** | Geographic area containing multiple Availability Zones — chosen for compliance, latency, price, service availability |
| **Availability Zone** | One or more discrete data centers with redundant power and networking; at least three per Region; within 100 km of each other |
| **Edge location** | Hundreds worldwide; caches content for CloudFront; also serves Route 53 and Global Accelerator |
| **Local Zone** | Extends a Region closer to large population centers for single-digit millisecond latency |
| **Wavelength Zone** | AWS infrastructure inside 5G networks for mobile edge computing |
| **AWS Outposts** | AWS hardware in your own data center — truly hybrid |

**Resilience ladder:** Multiple Availability Zones = high availability (the default right answer). Multiple Regions = disaster recovery and data residency. Multiple subnets alone does NOT guarantee resilience — subnets can share one Availability Zone.

## 3.2 EC2 Purchasing Options (5)

| Option | Label | Use when | Savings |
|---|---|---|---|
| **On-Demand** | **Least commitment** | Short-term, spiky, unpredictable; **cannot be interrupted**; first-time apps you're still sizing | Baseline |
| **Reserved Instances** | **Best long-term** | Steady-state, predictable usage; commit 1 or 3 years to a specific instance family and Region | Up to ~72% |
| **Savings Plans** | Flexible commitment | 1 or 3 years, committed dollars-per-hour; **covers more than EC2** — also Lambda and Fargate | Up to ~72% |
| **Spot Instances** | **Biggest savings** | Fault-tolerant and interruptible — batch jobs, big data, continuous integration, non-critical background work | Up to 90% |
| **Dedicated Hosts / Dedicated Instances** | Isolation | Regulatory or compliance requirement for isolated physical hardware; bring-your-own software licenses | Most expensive |

### The detail behind each

| Option | What defines it |
|---|---|
| **On-Demand** | Pay per hour or per second with no commitment. The default, and the answer whenever a workload can't tolerate interruption and the duration is unknown |
| **Spot** | You're requesting AWS's **spare capacity**, so AWS can reclaim it. Requires flexible start and end times and tolerance for the server stopping and starting at random |
| **Reserved** | A 1- or 3-year commitment. Unused Reserved Instances can be **resold on the Reserved Instance Marketplace** — a detail that occasionally appears as an answer choice |
| **Dedicated** | Physically isolated hardware. Can itself be purchased **on-demand, reserved, or spot**. Dedicated *Hosts* additionally expose the physical sockets and cores, which is what makes bring-your-own-license possible |
| **Savings Plans** | Not EC2-specific — see section 3.3 |

**The ordering to memorize** (the exact percentages vary by source and instance type, so learn the *ranking*, not the decimals):

Spot (deepest discount, most interruption risk) → Reserved Instances and Savings Plans (deep discount, locked into a term) → On-Demand (no discount, no commitment) → Dedicated (most expensive, buys isolation).

**The two trigger words that decide most questions:** if the stem says the workload **can be interrupted**, it's Spot. If it says the workload **cannot be interrupted** and usage is unpredictable, it's On-Demand. Commitment language — "1 or 3 years," "steady state," "predictable" — means Reserved Instances or Savings Plans, and Lambda or Fargate in the stem forces Savings Plans.

## 3.3 Savings Plans — Three Types

| Type | Covers | Savings |
|---|---|---|
| **Compute Savings Plans** | EC2 across any family, size, Region, operating system, tenancy — **plus AWS Lambda and AWS Fargate** | Up to 66% |
| **EC2 Instance Savings Plans** | One instance family in one Region | Up to 72% |
| **Amazon SageMaker Savings Plans** | SageMaker machine learning instances | Up to 64% |

**Three payment options (for both Savings Plans and Reserved Instances):** All Upfront (cheapest) → Partial Upfront → No Upfront (most expensive).

**The discriminator:** if the question mentions Lambda or Fargate, it must be **Compute** Savings Plans. Reserved Instances never cover those.

## 3.3a The Three Storage Types — Block, File, Object

This is the first decision in any storage question. Get the *type* right and the service follows.

| | **Block** — Amazon Elastic Block Store (EBS) | **File** — Amazon Elastic File System (EFS) | **Object** — Amazon Simple Storage Service (S3) |
|---|---|---|---|
| **Unit of storage** | Data split into evenly sized blocks | File stored with its data and metadata | Object stored with data, metadata, and a unique identifier |
| **Access protocol** | Fibre Channel, iSCSI | Network File System (NFS), Server Message Block (SMB) | HyperText Transfer Protocol Secure (HTTP/S) via application programming interface |
| **How it's reached** | Directly by the operating system, like a physical disk | Through a network share / network-attached storage export | Over the internet |
| **Concurrency** | Attaches to **one instance at a time** | **Multiple reads**; writing locks the file | **Multiple reads and writes**, no locks |
| **Scaling** | Provisioned volume size, resizable | Grows and shrinks automatically | Virtually unlimited — no file count or storage limit |
| **Use when** | You need a virtual hard drive attached to one instance | Multiple instances or users need the **same drive** | You're storing files, images, videos, backups, logs — anything web-accessible |

### Trigger phrases

| Stem says | Answer |
|---|---|
| Virtual hard drive, boot volume, attached disk, database storage on EC2 | **EBS** (block) |
| Shared file system, multiple instances need the same files, lift-and-shift a file server | **EFS** (file) |
| Store objects, static website assets, backups, data lake, virtually unlimited | **S3** (object) |
| Windows file shares specifically, or high-performance computing | **Amazon FSx** (FSx for Windows File Server, FSx for Lustre) |

### Scope — a detail the slide omits and the exam uses

| Service | Scope |
|---|---|
| **EBS** | **One Availability Zone.** A volume can only attach to an instance in the same Availability Zone. Snapshots are stored in S3 and can be copied across Regions. |
| **EFS** | **Regional** — accessible from multiple Availability Zones simultaneously. |
| **S3** | **Regional** — highly durable across Availability Zones automatically. |

**Two corrections to the slide this came from:**
1. EFS stands for Elastic **File System**, not "Elastic File Storage." The exam uses the correct name.
2. "Supports only a single write volume" is the correct default to memorize, but EBS Multi-Attach does allow certain volume types to attach to several instances in one Availability Zone. For CLF-C02, treat EBS as one-instance-at-a-time — that is the tested behavior.

## 3.4 S3 Storage Classes

**The governing idea:** every class below Standard trades **retrieval time and accessibility** for **cheaper storage**. Read any storage-class question as "how fast do they need it back, and how often do they touch it?"

| Class | Availability | Retrieval | Cost position | Use case |
|---|---|---|---|---|
| **S3 Standard** (default) | 99.99% | Immediate | Baseline | Frequently accessed, general purpose. Replicated across at least three Availability Zones |
| **S3 Intelligent-Tiering** | 99.9% | Immediate | Small monitoring fee | **Unknown or changing** access patterns — uses machine learning to move objects to the most cost-effective tier with no performance impact |
| **S3 Standard-Infrequent Access (Standard-IA)** | 99.9% | Immediate (still fast) | ~50% less than Standard | Accessed **less than once a month**, but needed fast when called. **Retrieval fee applies** |
| **S3 One Zone-Infrequent Access (One Zone-IA)** | 99.5% | Immediate (still fast) | ~20% less than Standard-IA | Infrequent AND **recreatable** — stored in a single Availability Zone, so data is lost if that zone is destroyed. **Retrieval fee applies** |
| **S3 Glacier Instant Retrieval** | 99.9% | Milliseconds | Cheaper than Standard-IA | Archive that still needs instant access |
| **S3 Glacier Flexible Retrieval** | 99.99% | Minutes to hours | Very cheap | Long-term cold storage, retrieval delay acceptable |
| **S3 Glacier Deep Archive** | 99.99% | **12 hours** (up to 48 bulk) | **Lowest cost of any class** | Compliance archives, 7–10 year retention, retrieved once or twice a year |
| **S3 Express One Zone** | 99.95% | Single-digit milliseconds | Highest cost | Highest performance, single Availability Zone |

### The durability point — and where the slide is wrong

**Durability is 99.999999999% (11 nines) across every storage class, including One Zone-IA.** Availability and resilience are what differ.

The slide this came from labels One Zone-IA as "reduced durability." That's a common misstatement. One Zone-IA is still designed for 11 nines of durability; what it loses is **resilience to the loss of an entire Availability Zone**, because the objects exist in only one. The practical risk the slide describes is real, but the durability *number* is unchanged — and the exam sometimes asks for that number directly.

**How to answer either version:** if a question asks for the durability figure, it's 11 nines regardless of class. If a question asks which class risks data loss from a zone failure, it's One Zone-IA (or Express One Zone).

### Trigger phrases

| Stem says | Answer |
|---|---|
| Access pattern is unknown, changing, or unpredictable | **Intelligent-Tiering** |
| Accessed less than monthly, still needs fast access | **Standard-IA** |
| Infrequent and can be regenerated if lost; lowest cost with fast access | **One Zone-IA** |
| Archive, retrieval in minutes to hours acceptable | **Glacier Flexible Retrieval** |
| Cheapest possible, retrieval within 12 hours acceptable, long retention | **Glacier Deep Archive** |
| Archive but must be instant | **Glacier Instant Retrieval** |
| Move objects between classes automatically on a schedule | **S3 Lifecycle policy** (not a class) |


## 3.4a Data Transfer, Backup, and File System Services

### AWS Snow Family — physically moving data

Storage and compute devices used to **physically move data in or out of the cloud** when transferring over the internet or a private connection would be too slow, difficult, or costly.

| Device | Capacity | Status |
|---|---|---|
| **Snowball Edge — Storage Optimized** | 80 TB | **Current.** The Snow Family answer on the exam |
| **Snowball Edge — Compute Optimized** | 39.5 TB | **Current.** Adds processing power for edge computing workloads |
| **Snowcone** | 8 TB (hard disk) / 14 TB (solid state) | **Retired** — discontinued November 2024 |
| **Snowmobile** | 100 PB per 45-foot trailer | **Retired** — discontinued April 2024 |

**Read this carefully, because the slide this came from is out of date.** AWS retired Snowmobile in April 2024 and Snowcone in November 2024, and since November 2025 Snow Family devices can only be ordered by existing customers. AWS now points new customers to online transfer instead.

**What to do on the exam:**
- If a stem describes shipping a physical device to move a large dataset offline, the answer is **Snowball Edge**.
- Know the Snowcone and Snowmobile *concepts* — an older question bank may still key them — but don't spend memory on their exact capacities.
- If a stem emphasizes transferring data **over the network** rather than by shipping, the answer is **AWS DataSync**, now AWS's recommended default for data migration.

### The other storage services

| Service | What it does | Exam trigger |
|---|---|---|
| **AWS DataSync** | Automated **online** data transfer between on-premises storage and AWS, or between AWS services | move data over the network, automated transfer, recurring sync |
| **AWS Storage Gateway** | **Hybrid** storage — on-premises applications use cloud storage as though it were local | hybrid, keep on-premises access, extend local storage to cloud |
| **AWS Backup** | Fully managed service to **centralize and automate backups** across services including EC2, EBS, RDS, DynamoDB, EFS, and Storage Gateway. You define **backup plans** | centralize backups, one place, automate across services |
| **AWS Elastic Disaster Recovery (AWS DRS)** | Continuously replicates servers into a low-cost staging area in a target AWS Region for fast recovery after a data center failure | disaster recovery, replicate servers, recover after outage |
| **Amazon FSx** | Feature-rich, high-performance managed **file systems** | see the two variants below |
| **Amazon FSx for Windows File Server** | Uses the Server Message Block (SMB) protocol; mounts to **Windows** servers | Windows file share, Active Directory integration, SMB |
| **Amazon FSx for Lustre** | Uses the Lustre file system; mounts to **Linux** servers | high-performance computing, machine learning training, Linux, fast scratch storage |

**A second dated item on that slide:** it lists **CloudEndure Disaster Recovery**, which AWS discontinued on March 31, 2024 in all Regions except China and GovCloud, with GovCloud following in September 2025. The replacement is **AWS Elastic Disaster Recovery (AWS DRS)**, built on the same technology. If a disaster recovery question offers both, pick AWS Elastic Disaster Recovery.

### The four-way transfer discriminator

| Stem says | Answer |
|---|---|
| Ship a physical device, network is too slow or costly | **Snowball Edge** |
| Transfer over the network, automated or recurring | **AWS DataSync** |
| On-premises app needs to keep using local protocols while data lives in AWS | **Storage Gateway** |
| Centralize and automate backups across many AWS services | **AWS Backup** |


## 3.5 Compute Options

| Service | Use when |
|---|---|
| **Amazon EC2** | Full control, long-running, needs an operating system |
| **AWS Lambda** | Event-driven, short (max 15 min), no servers, zero cost when idle |
| **Amazon Elastic Container Service** | AWS-native container orchestration |
| **Amazon Elastic Kubernetes Service** | Kubernetes-compatible containers |
| **AWS Fargate** | Serverless compute engine for containers — no instances to manage |
| **AWS Elastic Beanstalk** | Upload code, AWS provisions the platform — easiest deployment |
| **AWS Batch** | Batch computing jobs at scale |
| **Amazon Lightsail** | Simplest, bundled virtual private servers, predictable pricing |
| **Amazon EC2 Mac instances** | macOS, iOS, iPadOS, Xcode builds |
| **AWS Outposts** | Run AWS compute on-premises |

**Load balancing vs. Auto Scaling:** the load balancer **distributes traffic** across servers that exist. Auto Scaling **changes how many exist**. A load balancer can never create capacity.

**Rightsizing vs. scaling:** **AWS Compute Optimizer** recommends the correct instance *type* for under-utilized or over-provisioned resources. Auto Scaling changes *count*, never *type*, so it cannot fix over-provisioning.

## 3.5a EC2 Fundamentals — what you choose when you launch
**Amazon EC2 (Elastic Compute Cloud) is a highly configurable virtual server with resizable compute capacity.** New instances launch in **minutes**, not weeks — that speed is the point the exam keeps testing.

### The four launch decisions

| Step | What you pick | Notes |
|---|---|---|
| **1. Choose the operating system** | An **Amazon Machine Image (AMI)** | A template containing the operating system and any preinstalled software. Options include Amazon Linux, Ubuntu, Red Hat, SUSE, and Windows Server |
| **2. Choose the instance type** | Family, generation, and size — e.g. `t3.micro`, `c5.4xlarge` | Determines virtual CPUs, memory, and network performance |
| **3. Add storage** | **Amazon EBS** (block volumes) or **Amazon EFS** (shared file system) | Solid-state drive, hard disk drive, and multiple volumes are all options |
| **4. Configure the instance** | Security groups, key pairs, user data, IAM roles, placement groups | See below |

### Step 4 items, one line each

| Item | What it does |
|---|---|
| **Security group** | The instance-level firewall — which traffic may reach it |
| **Key pair** | The public/private key used to connect securely (Secure Shell for Linux, password decryption for Windows). **AWS does not keep your private key** — lose it and you cannot recover it |
| **User data** | A script that runs at first boot — used to install software or bootstrap configuration automatically |
| **IAM role** | Grants the instance permission to call other AWS services, without storing credentials on it |
| **Placement group** | Controls how instances are physically positioned — clustered for low latency, spread for fault isolation |

### Instance families worth recognizing

| Family letter | Category | Use case |
|---|---|---|
| **T, M** | General purpose | Balanced compute, memory, and networking — web servers, small databases |
| **C** | Compute optimized | Processor-heavy — batch processing, modeling, gaming servers |
| **R, X** | Memory optimized | Large in-memory datasets, high-performance databases |
| **I, D, H** | Storage optimized | High sequential read/write, large local storage |
| **P, G, Inf** | Accelerated computing | Graphics processing units for machine learning, rendering, graphics |

**Naming convention:** the letter is the family, the number is the generation, and the word after the dot is the size. So `c5.4xlarge` is compute optimized, fifth generation, 4xlarge size. Newer generation numbers are generally faster and cheaper per unit of work — which is part of what Compute Optimizer recommends.

**Two things not to memorize from the slide this came from:**
1. **The prices.** Instance pricing changes constantly and CLF-C02 does not ask you to recall dollar figures per hour. Understand that larger instances cost more; skip the numbers.
2. **"Everything on AWS uses EC2 underneath"** is a useful intuition but not literally true — several AWS services run on their own purpose-built infrastructure. Don't carry it into an exam answer.

## 3.5b Container Services

### The orchestration layer

| Service | What it is | Pick it when |
|---|---|---|
| **Amazon Elastic Container Service (ECS)** | AWS's own container orchestrator | You want containers on AWS with the least complexity; no Kubernetes requirement |
| **Amazon Elastic Kubernetes Service (EKS)** | Managed **Kubernetes** | The stem says **Kubernetes**, or emphasizes **open source** and **avoiding vendor lock-in** |
| **AWS Fargate** | **Serverless compute engine** that runs containers — no EC2 instances to manage | The stem says "without managing servers" or "no infrastructure to provision" |

**The relationship that the slide gets slightly wrong:** Fargate is **not** a third orchestrator competing with ECS and EKS. It's a **launch type** underneath them. You run ECS or EKS, and choose either the **EC2 launch type** (you manage the instances, you patch their operating system) or the **Fargate launch type** (AWS manages the compute, you just define the container). This matters for shared responsibility questions — see section 2.1a.

### Supporting container services

| Service | What it does | Trigger |
|---|---|---|
| **Amazon Elastic Container Registry (ECR)** | Stores and manages your **container images** | store Docker images, image repository, push and pull images |
| **AWS App Runner** | Platform as a service built specifically for **containerized web applications** — from source or image to a running service | deploy a containerized web app with no infrastructure setup |
| **AWS X-Ray** | **Traces and debugs** requests as they move between microservices | trace requests, find bottlenecks, debug a distributed application |
| **AWS Step Functions** | Orchestrates Lambda functions and ECS tasks into a workflow | multi-step workflow, coordinate services |
| **AWS Elastic Beanstalk** | Platform as a service; upload code and AWS provisions the environment | easiest deployment, don't want to configure infrastructure |

### Lambda vs. Fargate — the compute distinction

| | **AWS Lambda** | **AWS Fargate** |
|---|---|---|
| Unit | A function | A container |
| Duration | Short tasks, 15-minute maximum | Long-running, no time limit |
| Cost when idle | **Nothing** — truly scales to zero | You pay while tasks run |
| Use when | Event-driven, short, bursty | Containerized services that need to run continuously |

If a stem emphasizes **no cost when nothing is happening**, that's Lambda. If it emphasizes **containers without managing servers**, that's Fargate.

## 3.5c Cost and Capacity Management for Compute

Two questions this group of services answers:

- **Cost management** — how do we save money?
- **Capacity management** — how do we meet demand by adding or upgrading servers?

| Service | What it does | Exam trigger |
|---|---|---|
| **EC2 Spot Instances, Reserved Instances, Savings Plans** | Save on compute by paying upfront or partially upfront, committing to a 1- or 3-year term, or being flexible about interruption | reduce cost, commitment, interruptible |
| **AWS Batch** | Plans, schedules, and executes batch computing workloads across AWS compute services; can run on Spot Instances to cut cost further | batch jobs, queued processing, scientific or rendering workloads |
| **AWS Compute Optimizer** | Uses **machine learning** on your past usage history to recommend how to reduce cost and improve performance — i.e. rightsizing | over-provisioned, under-utilized, wrong instance type |
| **EC2 Auto Scaling groups** | Automatically adds or removes EC2 instances to match current demand; saves money by running only what is needed | traffic spike, scale out and in, only pay for what's needed |
| **Elastic Load Balancing** | Distributes traffic across multiple instances; reroutes away from unhealthy instances to healthy ones; can route across Availability Zones | distribute traffic, health checks, multiple Availability Zones |
| **AWS Elastic Beanstalk** | Deploys web applications without the developer configuring the underlying AWS services (comparable to Heroku) | just upload my code, don't want to manage infrastructure, easiest deployment |

### The three-way split that keeps catching you

| Problem | Service | What it changes |
|---|---|---|
| Instances are the wrong **size** | AWS Compute Optimizer | Instance **type** |
| There are the wrong **number** of instances | EC2 Auto Scaling | Instance **count** |
| Traffic is hitting instances unevenly, or hitting unhealthy ones | Elastic Load Balancing | Traffic **distribution** |

Each fixes exactly one of these and cannot fix the other two. Read the stem for which of the three is actually broken.

### Two machine-learning services that get confused

Both of these are described as using machine learning, so the giveaway is *what* they analyze:

| Service | Analyzes | Tells you |
|---|---|---|
| **AWS Compute Optimizer** | Resource configuration and utilization metrics | Your instances are the wrong size |
| **AWS Cost Anomaly Detection** | Cost and usage patterns | Your spending is unusual this month |

*Rightsizing* → Compute Optimizer. *Unexpected spend, anomaly, cost spike* → Cost Anomaly Detection.

## 3.6 Database Services

| Service | Use when |
|---|---|
| **Amazon RDS** | Relational, structured, joins, SQL |
| **Amazon Aurora** | Relational, MySQL/PostgreSQL-compatible, 5x / 3x faster, AWS-built |
| **Amazon DynamoDB** | Key-value / NoSQL, single-digit millisecond, massive scale, serverless |
| **Amazon Redshift** | Data warehouse, analytics, petabyte-scale, business intelligence |
| **Amazon Redshift ML** | Train and run machine learning models in the warehouse **using SQL** |
| **Amazon ElastiCache** | In-memory cache (Redis / Memcached) |
| **Amazon MemoryDB** | Durable in-memory database, microsecond reads |
| **Amazon DocumentDB** | MongoDB-compatible document database |
| **Amazon Keyspaces** | Managed Apache Cassandra-compatible database |
| **Amazon Neptune** | Graph database — relationships, social networks, fraud rings |
| **Amazon QLDB** | Immutable, cryptographically verifiable ledger |
| **Amazon Timestream** | Time-series data — Internet of Things, operational metrics |
| **AWS Database Migration Service** | Migrate databases with minimal downtime |

## 3.6a The NoSQL Services in Detail

AWS offers three distinct NoSQL services, and the exam separates them by **which engine or data model the question names**.

| Service | Model | Pick it when the stem says |
|---|---|---|
| **Amazon DynamoDB** | Serverless **key-value and document** | Massively scalable, billions of records, single-digit millisecond, no servers or shards to manage, cost-effective at scale |
| **Amazon DocumentDB** | **Document**, MongoDB-compatible | The workload uses or is migrating from **MongoDB** |
| **Amazon Keyspaces** | **Wide-column**, Apache Cassandra-compatible | The workload uses or is migrating from **Apache Cassandra** |

**The simple rule:** if a specific engine is named — MongoDB or Cassandra — take the compatible service. If no engine is named and the emphasis is scale, speed, and serverless, take **DynamoDB**.

**Why DynamoDB is the default NoSQL answer:** it's the service AWS built for its own scale. Amazon's retail business finished migrating off Oracle to DynamoDB in 2019, retiring 7,500 Oracle databases holding 75 petabytes, and cut costs around 60% and latency around 40%. That's the reason exam stems describing "massively scalable, fast, no infrastructure management" almost always key to DynamoDB.

**Supporting service worth knowing:** **DynamoDB Accelerator (DAX)** is an in-memory cache for DynamoDB that takes read latency from milliseconds to microseconds. If a stem asks to speed up DynamoDB reads specifically, that's DAX rather than ElastiCache.

**A correction to the slide this came from:** it says DynamoDB guarantees "consistent data return in at least a second." That's garbled and backwards. DynamoDB delivers **single-digit millisecond** performance — thousandths of a second, not seconds. The exam uses "single-digit millisecond" as the trigger phrase, so memorize it that way.

**One more distinction the slide doesn't make:** DynamoDB offers both *eventually consistent* reads (the default, cheaper) and *strongly consistent* reads (an option, more expensive). CLF-C02 rarely tests the difference, but if you see "eventually consistent" in an answer choice, it's a DynamoDB concept, not a flaw.

## 3.6b The Relational Database Services in Detail

**Relational is synonymous with SQL (Structured Query Language) and OLTP (Online Transaction Processing)** — structured data in tables that relate to each other. It's the most common database type in industry, and the default assumption unless a stem says otherwise.

### Engines Amazon RDS supports

| Engine | Note |
|---|---|
| **MySQL** | Most popular open-source SQL database; now owned by Oracle |
| **MariaDB** | A fork of MySQL created after Oracle's acquisition, under a different open-source license |
| **PostgreSQL** | Most popular open-source SQL database among developers; richer features than MySQL at more complexity |
| **Oracle** | Proprietary, common in enterprises; requires a purchased license |
| **Microsoft SQL Server** | Proprietary; requires a purchased license |
| **IBM Db2** | Added in late 2023; the sixth engine |
| **Amazon Aurora** | AWS's own fully managed engine (see below) |

**Memory aid for the open-source versus licensed split:** MySQL, MariaDB, PostgreSQL and Db2 lean open or free-tier; Oracle and SQL Server require you to bring or buy a license. If a stem mentions **licensing cost** as a concern, the answer usually moves toward MySQL, MariaDB, PostgreSQL, or Aurora.

### Aurora and Aurora Serverless

| Service | What it is | Pick it when |
|---|---|---|
| **Amazon Aurora** | Fully managed, AWS-built engine compatible with **MySQL (up to 5x faster)** and **PostgreSQL (up to 3x faster)** | A highly available, durable, scalable, secure relational database compatible with MySQL or PostgreSQL |
| **Amazon Aurora Serverless** | The on-demand, auto-scaling version of Aurora — capacity scales with load | Traffic is intermittent or unpredictable, and occasional cold starts are an acceptable trade for not paying for idle capacity |

**The trigger split:** *steady, predictable traffic* → Aurora. *Infrequent, spiky, or unpredictable traffic; don't pay when idle* → Aurora Serverless.

**A correction to the slide this came from:** it lists **RDS on VMware**, which AWS has discontinued. New customers can no longer use it, and AWS now points hybrid database workloads to RDS on EC2 or **AWS Outposts**. If a stem asks for managed AWS databases running in your own data center, the current answer is **AWS Outposts**.

## 3.7 Networking and Content Delivery

| Service | Job |
|---|---|
| **Amazon Virtual Private Cloud** | Your isolated network — subnets, route tables, gateways |
| **Amazon Route 53** | Domain registration and Domain Name System resolution |
| **Amazon CloudFront** | Content delivery network — caches at edge locations |
| **AWS Global Accelerator** | Routes over the AWS backbone; static anycast IP addresses |
| **AWS Direct Connect** | Dedicated physical line — **weeks to months** to provision |
| **AWS Site-to-Site VPN** | Encrypted tunnel over the internet — **hours** to set up |
| **AWS PrivateLink** | Private connectivity between Virtual Private Clouds and services |
| **AWS Transit Gateway** | Hub connecting many Virtual Private Clouds and on-premises networks |

### Elastic Load Balancing — the four types

| Type | Layer | Pick it when |
|---|---|---|
| **Application Load Balancer (ALB)** | Layer 7 — HTTP/S | Web traffic, **routing rules based on the content of the request** (path, host, headers). **An AWS WAF can be attached to it** |
| **Network Load Balancer (NLB)** | Layers 3 and 4 — TCP, UDP, TLS | **Extreme performance**, millions of requests per second, **ultra-low latency**, sudden volatile traffic, **a static IP address per Availability Zone** |
| **Gateway Load Balancer (GWLB)** | Layer 3 | Deploying a fleet of **third-party virtual appliances** (firewalls, intrusion detection) |
| **Classic Load Balancer (CLB)** | Layers 3, 4 and 7 | **Legacy only** — built for the retired EC2-Classic network. Does not use target groups |

**The discriminator:** *routing based on what's in the request, or attaching a web application firewall* → **ALB**. *Raw speed, static IP addresses, TCP or UDP* → **NLB**. *Third-party security appliances* → **GWLB**. *Legacy* → **CLB**.

**The deadline rule:** whenever a question imposes a time limit, Direct Connect loses to Site-to-Site VPN. Direct Connect is the better connection and the slower one to obtain.

## 3.7a Anatomy of a VPC — the pieces and their levels

Read any networking question by asking **which level it operates at**. That single question resolves most of them.

| Component | What it is | Level |
|---|---|---|
| **Region** | The geographical location of your network | Global infrastructure |
| **Availability Zone** | The data center (or group of them) holding your resources | Within a Region |
| **Virtual Private Cloud (VPC)** | A logically isolated section of the AWS Cloud where you launch resources | Within a Region, spans Availability Zones |
| **Subnet** | A logical partition of the VPC's IP address range into smaller segments | Within **one** Availability Zone |
| **Public subnet** | A subnet with a route to the internet gateway — put load balancers and bastion hosts here | Subnet |
| **Private subnet** | No direct route from the internet — put application servers and databases here | Subnet |
| **Internet gateway (IGW)** | Enables access to and from the internet | VPC |
| **NAT gateway** | Lets private-subnet resources reach *out* to the internet without being reachable *from* it | Subnet (placed in a public subnet) |
| **Route table** | Determines where network traffic from a subnet is directed | Subnet |
| **Router** | Moves traffic between subnets and gateways according to the route tables | VPC |
| **Security group** | Firewall at the **instance / resource** level — stateful, allow-only | Resource |
| **Network access control list (NACL)** | Firewall at the **subnet** level — stateless, allows and denies | Subnet |

### The traffic path, in order

Internet → **internet gateway** → **router** → **route table** → **network ACL** (subnet boundary) → **security group** (resource boundary) → **EC2 instance**.

Reversed for outbound, except that a private subnet's outbound traffic goes through the **NAT gateway** first.

**Why the order matters:** a NACL rule blocks traffic before it ever reaches a security group. If a question describes traffic being denied at the subnet edge, or asks to block a specific IP address, the answer is the NACL — security groups cannot deny, and they sit one layer further in. See section 2.4 for the full comparison.

**The subnet-to-Availability-Zone rule the exam tests:** a subnet lives in exactly **one** Availability Zone, but an Availability Zone can hold many subnets. This is why "deploy across multiple subnets" does **not** guarantee resilience, while "deploy across multiple Availability Zones" does.

**Private does not mean cut off.** Resources in a private subnet can still reach AWS services securely — through a NAT gateway for internet-bound traffic, or a **VPC endpoint** to reach AWS services without the traffic leaving the AWS network. The internet can't reach in; your servers can still reach out.

## 3.8 Application Integration

**Application integration is letting two independent applications communicate through an intermediate system.** Cloud architecture favors **loosely coupled** components — one piece can fail or be replaced without taking down the others — which is why AWS has a whole service category for it.

### The six integration patterns, mapped to services

| Pattern | AWS service | What it does |
|---|---|---|
| **Queueing** | **Amazon Simple Queue Service (SQS)** | Buffers messages; each is consumed once, then deleted |
| **Streaming** | **Amazon Kinesis** | Events persist in the stream so many consumers can read the same data |
| **Publish/subscribe** | **Amazon Simple Notification Service (SNS)** | One message pushed to many subscribers at once |
| **API gateway** | **Amazon API Gateway** | Front door for synchronous request/response application programming interface calls |
| **State machine** | **AWS Step Functions** | Orchestrates a multi-step workflow with visual definition |
| **Event bus** | **Amazon EventBridge** | Routes events between AWS services, custom apps, and software-as-a-service providers |

Plus two adjacent services: **Amazon Simple Email Service (SES)** sends email at scale, and **Amazon AppFlow** transfers data between software-as-a-service apps and AWS.

### Queue vs. stream vs. publish/subscribe — the distinction that gets tested

| | **SQS (queue)** | **Kinesis (stream)** | **SNS (publish/subscribe)** |
|---|---|---|---|
| **Message lifetime** | **Deleted once consumed** | **Persists** in the stream for a retention period | Not stored — delivered and gone |
| **Consumers** | One consumer per message | **Many consumers can read the same events** | Many subscribers receive every message |
| **Delivery** | Consumers **pull** | Consumers read from the stream | AWS **pushes** to subscribers |
| **Timing** | Asynchronous, processed when ready | **Real-time** | Immediate push |
| **Use case** | Queue transactional emails, decouple a purchase flow, buffer work | Real-time analytics, clickstreams, Internet of Things telemetry, log ingestion | Alerts, notifications, fanning one event out to several systems |

**How publish/subscribe actually works** (the mechanism behind the SNS column): publishers never send messages to receivers directly. They send to a **topic** on an event bus, which groups messages by category. Subscribers subscribe to those groups, and any new message is **pushed to them immediately**. Two consequences the exam leans on:

- **Publishers have no knowledge of who their subscribers are.** That's the decoupling — you can add or remove subscribers without touching the publisher.
- **Subscribers never poll.** Messages are pushed automatically. This is the cleanest way to remember the SQS/SNS split: SQS consumers **ask**, SNS subscribers **are told**.

"Message" and "event" mean the same thing in this context.

**The three-way discriminator:**

- *Buffer work, process later, each item handled once, decouple* → **SQS**
- *Real-time, multiple consumers need the same data, analytics on a live feed, retain events for reprocessing* → **Kinesis**
- *Notify, broadcast, fan out, alert several subscribers* → **SNS**

**Kinesis consumers** commonly include Amazon Redshift, Amazon DynamoDB, Amazon S3, and Amazon EMR — if a stem describes a live data feed landing in a warehouse or data lake, Kinesis is the pipe.

**One nuance the slide understates:** it calls SQS "not real-time." More precisely, SQS is **pull-based** — consumers poll for messages rather than being pushed to — and messages are removed once processed. That pull-versus-push and delete-versus-retain pair is the real distinction the exam tests, not latency.

### Amazon SNS in detail

**Simple Notification Service is a highly available, durable, secure, fully managed publish/subscribe messaging service** for decoupling microservices, distributed systems, and serverless applications.

| Element | Detail |
|---|---|
| **Publishers** | The AWS Software Development Kit (SDK), the AWS Command Line Interface (CLI), Amazon CloudWatch, and other AWS services |
| **SNS topic** | The named channel messages are published to — the unit subscribers attach to |
| **Message filtering and fanout** | A topic can filter which messages reach which subscriber, then deliver one message to all matching subscribers at once |
| **Subscribers** | **AWS Lambda**, **Amazon SQS**, **email**, **HTTP/S endpoints** (also Short Message Service and mobile push) |

**Memorize the four subscriber types** — Lambda, SQS, email, HTTP/S. They appear directly in answer choices.

**The SNS-to-SQS fanout pattern** is worth recognizing: one SNS topic publishes to several SQS queues, so each downstream system gets its own copy of the message to process at its own pace. If a stem describes one event needing to trigger several independent workflows that each process at different speeds, that's SNS fanning out to SQS.

### Amazon API Gateway in detail

**An API gateway sits between a single entry point and multiple backends.** Amazon API Gateway creates secure application programming interfaces at any scale, acting as the **front door** for applications to reach data, business logic, or backend services.

| Capability | What it gives you |
|---|---|
| **Throttling** | Rate-limits callers so a traffic spike can't overwhelm the backend |
| **Logging** | Request and response logging, integrated with Amazon CloudWatch |
| **Routing logic** | Sends different paths and methods to different backends |
| **Request/response formatting** | Transforms payloads between client and backend |
| **Caching** | An API Gateway cache reduces repeated backend calls |

**Typical callers:** mobile apps, web apps, Internet of Things devices — all over HTTP/S. **Typical backends:** Lambda, DynamoDB, Kinesis, EC2, and other AWS services.

**The discriminator against the messaging services:** API Gateway is **synchronous request/response** — the caller waits for an answer. SQS, SNS, and Kinesis are **asynchronous** — the sender hands off and moves on. If a stem describes a client calling an endpoint and expecting a reply, it's API Gateway, not a queue.

### Amazon EventBridge and AWS Step Functions in detail

**Amazon EventBridge — the serverless event bus.** Events are JSON objects emitted by services; rules decide which events go where.

| Element | What it is |
|---|---|
| **Producers** | AWS services (and your own applications) that emit events |
| **Event** | The data emitted — a JSON object travelling on the bus |
| **Event bus** | Holds the events. Three kinds: **default** (every account has one), **custom** (your own applications, shareable across accounts), and **partner/SaaS** (third-party providers such as monitoring or identity vendors) |
| **Rules** | Determine which events to capture and which targets to pass them to |
| **Targets** | The AWS services that consume the matched events — Lambda, Step Functions, SQS, and others |

*Don't memorize the numeric limits on the slide (rules per bus, targets per rule). CLF-C02 does not test service quotas at that level.*

**AWS Step Functions — the state machine.** A state machine decides how one state moves to the next based on conditions; think of it as a flow chart where each step can invoke an AWS service.

What Step Functions gives you:
- Coordinates multiple AWS services into a **serverless workflow**
- A **graphical console** showing your application as a series of steps, with each one's status
- **Automatic triggering, tracking, and retry on error**, so steps execute in order every time
- **Logs the state of each step**, so a failure can be diagnosed at the exact point it occurred

**The EventBridge vs. Step Functions discriminator:** EventBridge **routes** events to whatever should react to them — it doesn't know or care what happens next. Step Functions **sequences** a known set of steps in a defined order, with retries and branching. *Route an event to interested consumers* → EventBridge. *Run step one, then step two, retry if it fails* → Step Functions.

### Three more integration services — the "named engine" group

These follow the same rule as the NoSQL databases: **when a stem names a specific open-source technology, take the AWS managed version of it.**

| Service | What it is | The trigger |
|---|---|---|
| **Amazon MQ** | Managed **message broker** supporting Apache ActiveMQ and RabbitMQ | An existing application already uses a standard message broker or protocol (JMS, AMQP, MQTT) and is being **migrated without rewriting** |
| **Amazon Managed Streaming for Apache Kafka (MSK)** | Fully managed **Apache Kafka** | The word **Kafka** appears, or an existing Kafka pipeline is moving to AWS |
| **AWS AppSync** | Fully managed **GraphQL** service for querying data from many sources | The word **GraphQL** appears |

**The Amazon MQ versus SQS discriminator** — this is the one that gets tested. Both are messaging, but:

- **Building something new on AWS** → **SQS** (AWS-native, serverless, no broker to manage)
- **Migrating an existing app that already speaks a standard broker protocol** → **Amazon MQ** (so you don't have to rewrite the messaging code)

Same logic for **MSK versus Kinesis**: Kinesis is the AWS-native streaming answer for new work; MSK exists so teams already running Kafka can move without rewriting.

**One correction to the slide this came from:** it lists Amazon MQ as using Apache ActiveMQ only. Amazon MQ supports **both ActiveMQ and RabbitMQ** — if RabbitMQ appears in a stem, Amazon MQ is still the answer.

## 3.9 Management and Governance

| Service | Job |
|---|---|
| **AWS CloudFormation** | Infrastructure as code — template defines resources |
| **AWS Systems Manager** | Operational management, patching, Parameter Store, Session Manager |
| **AWS Organizations** | Multi-account management, consolidated billing, Service Control Policies |
| **AWS Control Tower** | Sets up and governs a secure multi-account landing zone |
| **AWS Service Catalog** | Curated catalog of approved products |
| **AWS Launch Wizard** | Guides sizing and deployment of third-party applications |
| **EC2 Image Builder** | Automates creation, testing, patching of custom machine images |
| **AWS Compute Optimizer** | Rightsizing recommendations |
| **AWS Well-Architected Tool** | Reviews workloads against the Well-Architected Framework |
| **AWS License Manager** | Tracks software licenses |
| **AWS Health Dashboard** | Service health and events affecting your account |
| **AWS OpsWorks** | **Configuration management** using managed **Chef** and **Puppet** |
| **AWS Marketplace** | Digital catalog of third-party software you can find, buy, and deploy |
| **AWS QuickStarts** | Pre-built reference packages that launch and configure a whole workload |

**The provisioning trio, distinguished:** **CloudFormation** defines infrastructure as code in JSON or YAML templates. **Elastic Beanstalk** takes your code and provisions the environment for you (it is itself powered by CloudFormation underneath, setting up load balancing, Auto Scaling, RDS, EC2, and CloudWatch). **OpsWorks** manages configuration on existing servers using Chef or Puppet. *Define the infrastructure* → CloudFormation. *Just deploy my app* → Beanstalk. *Chef or Puppet named* → OpsWorks.

**Service Control Policies are guardrails, not grants.** They set the maximum available permission; they never give permission by themselves.

---

## 3.9a AWS Organizations and Multi-Account Structure

**AWS Organizations lets you create and centrally manage multiple AWS accounts** — consolidating billing, controlling access, enforcing compliance, and sharing resources across them.

| Element | What it is |
|---|---|
| **Management account** | The account that creates the organization and pays the consolidated bill. There is exactly one |
| **Member accounts** | Every other account in the organization |
| **Organizational unit (OU)** | A group of accounts inside the organization. OUs can contain other OUs, creating a hierarchy |
| **Service control policy (SCP)** | Sets the **maximum available permissions** for the accounts it applies to |
| **Consolidated billing** | One bill for all accounts, with usage aggregated for volume discounts and Reserved Instance sharing |

### Three points the exam tests

**Service control policies are guardrails, not grants.** An SCP defines the ceiling on what an account *may* do. It never gives permission by itself — an identity still needs an IAM policy allowing the action. Both must permit it.

**An SCP is the only way to restrict the root user.** As covered in section 2.2a, no IAM policy can limit the root user. An SCP applied through Organizations can.

**Once an organization is created, it cannot be switched off casually** — you can remove accounts and delete the organization, but there's no "turn it off" toggle.

### A terminology trap worth separating

The word **root** means two different things here:

| Term | Meaning |
|---|---|
| **Root user** | The identity created with each AWS account — email and password, full access, cannot be deleted |
| **Root** (in Organizations) | The **top-level container** of the organizational unit hierarchy — the node every OU and account sits under |

They are unrelated. A stem about sign-in credentials means the root user; a stem about the structure of OUs means the organization's root container.

**One naming correction to the slide this came from:** it calls the payer account the **Master Account**. AWS renamed this the **management account**, and that's the term the current exam uses. If both appear as options, pick management account.

## 3.9b Developer and Front-End Services

These appear as answer choices but are tested only at the one-line level. Know what each *is*; don't go deeper.

| Service | One line |
|---|---|
| **AWS Amplify** | Framework and managed hosting for building **web and mobile applications** — front-end hosting plus backend integration |
| **Amazon Cognito** | **User sign-up, sign-in, and access control for your applications** — the identity service for your app's end users |
| **AWS Cloud9** | Cloud-based integrated development environment in the browser |
| **AWS CloudShell** | Browser-based shell with the AWS Command Line Interface preinstalled |
| **AWS AppSync** | Managed GraphQL (see section 3.8) |
| **AWS Device Farm** | **Tests** web and mobile apps on real devices and browsers — testing, not building |

### The Cognito vs. IAM distinction — this one is tested

| Service | Who it manages |
|---|---|
| **AWS Identity and Access Management (IAM)** | **Your team's** access to AWS resources — employees, services, roles |
| **Amazon Cognito** | **Your application's end users** — customers signing up and logging into the app you built |

If a stem describes customers creating accounts in a mobile or web app, it's **Cognito**. If it describes staff or services accessing AWS resources, it's **IAM**. Mixing these up is a common Domain 2 error.

**On the Amplify slide this came from:** the breakdown into Amplify CLI, SDK, UI, Hosting, and Studio, and the list of supported JavaScript frameworks, are well beyond CLF-C02 scope. Know Amplify as "build and host web and mobile apps" and move on. The slide's commentary about Amplify's developer experience is the instructor's opinion, not exam content.

---

## 3.9c Business-Centric and Analytics Services

One line each. These appear as answer choices and are tested only at the "what is it" level.

| Service | What it is |
|---|---|
| **Amazon Connect** | **Virtual call center** — route callers, record calls, manage a queue of callers |
| **Amazon WorkSpaces** | **Virtual remote desktops** (Windows or Linux) provisioned in minutes and scalable to thousands |
| **Amazon WorkMail** | Managed **business email, contacts, and calendar**, compatible with existing desktop and mobile mail clients |
| **Amazon Simple Email Service (SES)** | **Transactional email** sent from your application — order confirmations, password resets. Templates, open-rate tracking, sender reputation |
| **Amazon Pinpoint** | **Marketing campaign management** — targeted outreach by email, Short Message Service, push notification, and voice, with A/B testing and multi-step journeys |
| **Amazon QuickSight** | **Business intelligence** — connect data sources and build dashboards and visualizations with little or no programming |

### Three discriminators

**SES vs. Pinpoint.** Both send email, and the stem decides which:
- *Transactional, triggered by an application event, one message to one user* → **SES**
- *Marketing campaign, targeted segments, A/B testing, scheduled outreach* → **Pinpoint**

**SES vs. SNS.** SES sends **email to people**. SNS is publish/subscribe messaging **between systems** (though it can deliver to email as one of its subscriber types). If the stem is about an email product, it's SES; if it's about decoupling components, it's SNS.

**QuickSight vs. Redshift.** QuickSight is the **dashboard**; Redshift is the **warehouse** the data sits in. A stem about visualizing or reporting on data points to QuickSight; a stem about storing and querying petabytes points to Redshift.

### Two services on that slide that no longer exist

| Service | Status |
|---|---|
| **Amazon WorkDocs** | Stopped accepting new customers in April 2024; **support ended April 25, 2025** |
| **Amazon Chime** | Stopped accepting new customers February 2025; **support ended February 20, 2026**. AWS points users to Zoom, Slack, or AWS Wickr. Note the **Amazon Chime SDK** is a separate product and is unaffected |

Know what each *was* — WorkDocs as shared document collaboration, Chime as video conferencing — in case an older question bank keys them. But neither is current AWS, and a well-maintained exam won't test them.

## 3.10 Big Data and Analytics Services

**Big data** means volumes of structured or unstructured data too large to move and process with traditional database techniques.

| Service | What it does | Trigger |
|---|---|---|
| **Amazon Athena** | **Serverless interactive query** — run SQL directly against files sitting in S3 | query CSV or JSON files in S3, no infrastructure, pay per query |
| **Amazon Redshift** | Petabyte-scale **data warehouse** for Online Analytical Processing (OLAP). Keeps data "hot" so complex queries over huge datasets return fast | data warehouse, analytics, reporting on large volumes |
| **Amazon EMR** (Elastic MapReduce) | Big data processing framework (Hadoop, Spark) — good at **transforming unstructured data into structured** on the fly | Hadoop, Spark, process raw unstructured data |
| **Amazon OpenSearch Service** | Managed **full-text search and log analytics** cluster | search, log analytics, operational dashboards |
| **Amazon CloudSearch** | Simpler managed **full-text search** | add search to a website with minimal setup |
| **AWS Glue** | Serverless **Extract, Transform, Load (ETL)** — move data and transform it en route | ETL, transform before loading, data catalog |
| **AWS Lake Formation** | Builds a **data lake** — centralized, curated, secured repository holding raw data in native format | data lake, centralize all our data |
| **AWS Data Exchange** | Catalog of **third-party datasets** you can subscribe to or purchase | buy or subscribe to external data |
| **AWS Data Pipeline** | Older service for automating data movement between compute and storage | legacy; for new ETL work the answer is **Glue** |
| **Amazon QuickSight** | Business intelligence dashboards (section 3.9c) | visualize, dashboard, report |

### The Kinesis family

| Service | What it does |
|---|---|
| **Kinesis Data Streams** | Real-time streaming — producers write, **multiple consumers** read, you manage capacity |
| **Kinesis Data Firehose** | **Serverless** delivery stream — simpler, pay for what flows through, loads into S3, Redshift, OpenSearch |
| **Kinesis Data Analytics** | Run **queries against data while it is still flowing** through the stream |
| **Kinesis Video Streams** | Ingest and process **real-time video** |

**The three that get confused:**
- *Query files already in S3 with SQL* → **Athena**
- *Transform data on the way to a destination* → **Glue**
- *Warehouse for fast complex analytics* → **Redshift**

**Athena vs. Redshift:** Athena queries files in place with no infrastructure and no loading step. Redshift requires loading data into a warehouse but is far faster for repeated complex queries. *Occasional queries over files* → Athena. *A warehouse powering regular analytics* → Redshift.

## 3.11 Machine Learning and Artificial Intelligence Services

Tested at the "what does it do" level only. Know the job, not the implementation.

### The core platform

| Service | What it does |
|---|---|
| **Amazon SageMaker** | The full **build, train, and deploy** machine learning platform |
| **Amazon Bedrock** | **Generative artificial intelligence** — foundation models for text and image generation |
| **Amazon Q Developer** | AI coding assistant that suggests code (**formerly Amazon CodeWhisperer**) |
| **Amazon Q Business** | Generative AI assistant that answers questions over your company's own data |

### The purpose-built services — match the job to the name

| Service | Job |
|---|---|
| **Amazon Rekognition** | Image and video analysis — object and face detection |
| **Amazon Comprehend** | Natural language processing — sentiment, entities, key phrases in text |
| **Amazon Transcribe** | Speech to text |
| **Amazon Polly** | Text to speech |
| **Amazon Translate** | Language translation |
| **Amazon Textract** | Extract text and data **from scanned documents** |
| **Amazon Lex** | Conversational chatbots (the technology behind Alexa) |
| **Amazon Forecast** | **Time-series forecasting** — demand, resource needs, financial performance |
| **Amazon Personalize** | Real-time recommendations |
| **Amazon Fraud Detector** | Detects online fraud — payment fraud, fake account creation |
| **Amazon Kendra** | **Enterprise search** using natural language rather than keyword matching |
| **Amazon DevOps Guru** | Uses machine learning to detect **operational abnormalities** in your applications |
| **Amazon Lookout** (for Equipment / Metrics / Vision) | Machine learning for quality control and automated inspection |
| **Amazon Monitron** | Predicts **equipment failure** using an Internet of Things vibration sensor |
| **Amazon Augmented AI (A2I)** | Adds **human review** to machine learning predictions |

### The learning and hardware extras

| Service | What it is |
|---|---|
| **AWS DeepRacer** | Toy race car for learning reinforcement learning |
| **AWS DeepLens** | Deep-learning-enabled video camera |
| **AWS DeepComposer** | Machine-learning musical keyboard |
| **AWS Deep Learning AMIs / Containers** | EC2 images and Docker images **pre-installed** with frameworks like TensorFlow and PyTorch |
| **AWS Inferentia / AWS Trainium** | AWS's own chips for machine learning **inference** and **training** |
| **AWS Neuron** | The software development kit for running workloads on Inferentia and Trainium |

**Not exam material:** the slide listing MXNet, PyTorch, TensorFlow, Keras, Spark, Chainer, and Hugging Face covers third-party frameworks, not AWS services. Recognize that SageMaker supports them; don't memorize the list.

# PART 4 — BILLING, PRICING, AND SUPPORT

## 4.0 Capital vs. Operational Expenditure

| | **Capital expenditure (CapEx)** | **Operational expenditure (OpEx)** |
|---|---|---|
| What it is | Spending money **upfront on physical infrastructure**, deducted from tax over time | Ongoing costs where the **physical** burden has shifted to the provider |
| Examples | Servers, storage hardware, network equipment, backup systems, data center rent, cooling, physical security, technical staff | Leasing software, training staff, paying for support, billing based on compute and storage **usage** |
| The catch | **You have to guess upfront** what you will need | You can **try a service without investing in equipment** |

**Moving to the cloud converts CapEx into OpEx.** That's advantage number one in section 1.1, and the exam phrases it as "trade capital expense for variable expense."

## 4.1 The Three Pricing Fundamentals
1. **Pay as you go** — pay only for what you use
2. **Save when you reserve** — commit for 1 or 3 years for a discount
3. **Pay less by using more** — volume-based tiered pricing

**Data transfer rule:** inbound data transfer is free. Outbound data transfer is charged. Transfer within the same Availability Zone (private IP) is free.

## 4.2 AWS Free Tier — Three Types
1. **Always Free** — never expires (e.g. 1 million Lambda requests per month, 25 GB DynamoDB, 62,000 SES emails per month sent from an application)
2. **12 Months Free** — from account creation. The commonly cited examples: **750 hours per month of t2.micro EC2**, 750 hours per month of db.t2.micro RDS, 750 hours per month of Elastic Load Balancing
3. **Trials** — short-term from service activation

## 4.3 The Cost Management Tools

| Tool | Use it for | Time direction |
|---|---|---|
| **AWS Pricing Calculator** | Estimate the cost of a planned architecture | **Future** |
| **AWS Cost Explorer** | Visualize and analyze past spending, up to 12 months forecast | **Past** |
| **AWS Budgets** | Set thresholds and receive alerts before overspending | **Alerting** |
| **AWS Cost and Usage Report** | Most granular raw billing data available | **Detailed data** |
| **AWS Cost Anomaly Detection** | **Machine learning** detects unusual spend automatically | **Automatic** |
| **AWS Billing Conductor** | Custom billing views for internal chargeback | **Reporting** |
| **Cost Allocation Tags** | Attribute costs to teams, projects, environments | **Attribution** |

**The discriminator:** *machine learning, unusual, anomaly, unexpected spike* → Cost Anomaly Detection. *Estimate before building* → Pricing Calculator. *Alert me at a threshold* → Budgets. *Analyze what we already spent* → Cost Explorer.

## 4.4 The Five Support Plans

| Plan | Cost | Technical support | Trusted Advisor | Technical Account Manager |
|---|---|---|---|---|
| **Basic** | Free | None (forums, documentation) | 7 core checks | No |
| **Developer** | From $29/mo | Business hours, email, 1 primary contact | 7 core checks | No |
| **Business** | From $100/mo | 24/7 phone, email, chat, unlimited contacts | **Full set** | No |
| **Enterprise On-Ramp** | From $5,500/mo | 24/7 + pool of Technical Account Managers | Full set | Pool |
| **Enterprise** | From $15,000/mo | 24/7 + **designated** Technical Account Manager | Full set | Designated |

**Response times (memorize the fastest tier of each):**

| Severity | Developer | Business | Enterprise On-Ramp | Enterprise |
|---|---|---|---|---|
| General guidance | 24 business hours | 24 hours | 24 hours | 24 hours |
| System impaired | 12 business hours | 12 hours | 12 hours | 12 hours |
| Production system impaired | — | 4 hours | 4 hours | 4 hours |
| Production system down | — | 1 hour | 1 hour | 1 hour |
| Business-critical system down | — | — | **30 minutes** | **15 minutes** |

**The three discriminators:** full Trusted Advisor starts at **Business**. Any Technical Account Manager starts at **Enterprise On-Ramp**. **15 minutes** means Enterprise, and only Enterprise.

---

# PART 5 — CONCEPT PAIRS THAT GET SWAPPED

| If the stem says... | The answer is... | Not... |
|---|---|---|
| Automatically grows **and shrinks** | Elasticity | Scalability |
| Can grow when needed | Scalability | Elasticity |
| Minimizes downtime, brief failover acceptable | High availability | Fault tolerance |
| Zero loss of function during failure | Fault tolerance | High availability |
| How much **data** can we lose | Recovery Point Objective | Recovery Time Objective |
| How long can we be **down** | Recovery Time Objective | Recovery Point Objective |
| Provider guarantees uptime, credits if missed | Service Level Agreement | Recovery objectives |
| Which **user** performed an action | CloudTrail | Config |
| Is this resource **compliant / changed** | Config | CloudTrail |
| Application **configuration variables** | AWS AppConfig | AWS Config |
| Performance metrics, logs, alarms | CloudWatch | CloudTrail |
| Runs continuously, needs an operating system | EC2 | Lambda |
| Triggered, short, no cost when idle | Lambda | EC2 |
| Wrong instance **size** | Compute Optimizer | Auto Scaling |
| Wrong instance **count** | Auto Scaling | Compute Optimizer |
| Need it **this week** | Site-to-Site VPN | Direct Connect |
| Dedicated, consistent, high bandwidth | Direct Connect | Site-to-Site VPN |
| Keeping the data center **and** adding AWS | Hybrid | Fully managed cloud |

---

# HOW TO DRILL THIS

Active recall only. Rereading this sheet will feel productive and will not work.

1. **Cover the right-hand column** and recite the answer aloud before looking.
2. **Write the six-item lists from blank paper** daily: six advantages, six general design principles, six pillars, six Cloud Adoption Framework perspectives, four CAF phases, seven Rs.
3. **Take full 65-question timed sets**, then categorize every miss by domain and return to that section here.
4. **Go in tier order.** Tier 1 cold before Tier 2; Tier 2 before Tier 3.

The failure mode this document exists to prevent: recognizing an answer when you see it, but not producing it when you don't. Those feel identical while studying and are completely different on the exam.


---

# SOURCES

1. **AWS Certified Cloud Practitioner (CLF-C02) exam guide and official AWS documentation** — domain weights, service definitions, and current service names and statuses. https://aws.amazon.com/certification/certified-cloud-practitioner/
2. **Personal study notes** (uploaded markdown) — the original four-domain outline, trap list, and quick-fire contrast table this sheet grew from.
3. **AWS Certified Cloud Practitioner Certification Course 2026 (CLF-C02)** — Andrew Brown / freeCodeCamp, ~13.5 hours. https://www.youtube.com/watch?v=7HKot-brXFE
4. **ExamPro CLF-C02 course slides** — shared responsibility, storage, databases, networking, integration, analytics, machine learning. https://www.exampro.co/clf-c02
5. **Learn 97% of AWS in Under 30 Minutes** — the ten-step ticket-platform architecture that supplies the service-matching mental model. https://www.youtube.com/watch?v=ujeEIbu_JxE
6. **The 10 cloud building blocks** — multi-cloud concept overview. https://www.youtube.com/watch?v=De4V2czb-8A
7. **Tutorials Dojo CLF-C02 practice exams and cheat sheets** — question style, explanations, and the misses that shaped the trap tables. https://tutorialsdojo.com/
8. **AWS Well-Architected Framework whitepaper** — https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html
9. **AWS Cloud Adoption Framework whitepaper** — https://aws.amazon.com/cloud-adoption-framework/

## Where sources were out of date

Several source slides predate current AWS. Where they conflicted, this sheet follows current AWS documentation:

| Source said | Current reality |
|---|---|
| Well-Architected has **five** pillars | **Six** — Sustainability was added in 2021 |
| Amazon CodeWhisperer | Now **Amazon Q Developer** (April 2024) |
| Amazon Elasticsearch Service | Now **Amazon OpenSearch Service** |
| Snowmobile, Snowcone | **Retired** (April 2024, November 2024) |
| CloudEndure Disaster Recovery | Replaced by **AWS Elastic Disaster Recovery** |
| RDS on VMware | **Discontinued** — use RDS on EC2 or Outposts |
| Amazon WorkDocs, Amazon Chime | **Discontinued** (April 2025, February 2026) |
| RDS supports five engines | **Six** — IBM Db2 added late 2023 |
| Organizations "master account" | Now the **management account** |
| One Zone-IA has "reduced durability" | Durability is **11 nines for every class**; One Zone-IA loses zone resilience |
| DynamoDB returns "within a second" | **Single-digit millisecond** |
