# CLF-C02 Study Stack — All Resources

Exam: **AWS Certified Cloud Practitioner (CLF-C02)** — Friday, October 9, 2026, 8:00 AM Chicago time (check-in 7:30 AM).

AWS = Amazon Web Services throughout.

---

## Tier 1 — Official AWS (authoritative; start here)

| Resource | What it's for | Link |
|---|---|---|
| **CLF-C02 certification page** | Hub for everything official, including the exam guide PDF download | https://aws.amazon.com/certification/certified-cloud-practitioner/ |
| **CLF-C02 Exam Guide** | The scope document — domain weights and the in-scope service list | https://training.resources.awscloud.com/training-certification-get-certified/aws-certified-cloud-practitioner-exam-guide-c02 |
| **Official Practice Question Set** (free, 20 questions) | Calibrates you to real AWS question phrasing, with feedback on every answer choice | https://skillbuilder.aws/learn/E4W52ZKK6P/official-practice-question-set-aws-certified-cloud-practitioner-clfc02--english/RJSZKD3MG3 |
| **Official Practice Exam** | Full length, uses the **same scaled scoring model** as the real exam — your go/no-go check | https://skillbuilder.aws/learn/JSJ5VBDBRG/official-practice-exam-aws-certified-cloud-practitioner-clfc02--english/FHCY1FNYXJ |
| **AWS Skill Builder** (entry point) | If a deep link above breaks, search from here | https://skillbuilder.aws |
| **Sample questions PDF** | Free, on the certification page alongside the exam guide | https://aws.amazon.com/certification/certified-cloud-practitioner/ |

## Tier 2 — Official whitepapers for your two weakest areas

| Resource | Why it matters | Link |
|---|---|---|
| **Well-Architected Framework** | The exam lifts wording nearly verbatim; covers pillars and design principles | https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html |
| **Operational Excellence design principles** | The specific page for the five principles you keep being asked about | https://docs.aws.amazon.com/wellarchitected/latest/framework/oe-design-principles.html |
| **Cloud Adoption Framework (CAF)** overview | Six perspectives and their stakeholders | https://aws.amazon.com/cloud-adoption-framework/ |
| **CAF cloud transformation journey** | The four phases — Envision, Align, Launch, Scale | https://docs.aws.amazon.com/whitepapers/latest/overview-aws-cloud-adoption-framework/your-cloud-transformation-journey.html |

## Tier 3 — Practice questions (calibration)

| Resource | Notes |
|---|---|
| **Tutorials Dojo CLF-C02 practice exams** | Primary question bank. Runs harder than the real exam. Read every explanation, including for questions you got right. |
| **Stephane Maarek practice exams (Udemy)** | Six full-length sets, legitimate, usually under $20 on sale. Only worth adding if you exhaust Tutorials Dojo and need questions you haven't seen. https://www.udemy.com/course/practice-exams-aws-certified-cloud-practitioner/ |

**Tutorials Dojo cheat sheets** — free, and the fastest reference for the topics that have tripped you up:

- Cloud computing basics — https://tutorialsdojo.com/what-is-cloud-computing/
- Well-Architected Framework — https://tutorialsdojo.com/aws-well-architected-framework-six-pillars/
- Cloud Adoption Framework — https://tutorialsdojo.com/aws-cloud-adoption-framework-aws-caf/
- Global infrastructure — https://tutorialsdojo.com/aws-global-infrastructure/
- Amazon Virtual Private Cloud (security groups vs. network access control lists) — https://tutorialsdojo.com/amazon-vpc/
- Amazon Elastic Compute Cloud (EC2) — https://tutorialsdojo.com/amazon-elastic-compute-cloud-amazon-ec2/
- AWS pricing — https://tutorialsdojo.com/aws-pricing/
- Billing and cost management — https://tutorialsdojo.com/aws-billing-and-cost-management/
- AWS Compute Optimizer — https://tutorialsdojo.com/aws-compute-optimizer

## Tier 4 — Video

| Resource | Use it for |
|---|---|
| **AWS Certified Cloud Practitioner Course 2026 (CLF-C02)** — https://www.youtube.com/watch?v=7HKot-brXFE | Coverage. Fills the CAF, Well-Architected Tool, and support/billing gaps. Skip the console demos — not scored. |
| **Learn 97% of AWS in Under 30 Minutes** — https://www.youtube.com/watch?v=ujeEIbu_JxE | Structure. The ten-step ticket platform — the mental model that makes service-matching automatic. |
| **The 10 cloud building blocks (multi-cloud)** — https://www.youtube.com/watch?v=De4V2czb-8A | Optional, 5 minutes. Compute, containers, serverless, object storage, databases, networking, DNS, load balancing, identity, monitoring. Reinforces the same model as the ticket platform. **The Azure and Google Cloud equivalents are out of scope for CLF-C02 — do not memorize them.** |

## Tier 5 — Your own materials

| Resource | Link |
|---|---|
| **Master Memorization Sheet** — all content, opening with the three-tier priority guide | https://claude.ai/artifact/HJQBzayh4R6bPKTZFpKU7q |
| **Recall Deck** — 127 flashcards, filter by domain, flag and drill | https://claude.ai/artifact/YSWgU29r4Wtk7VXqd7AgA6 |
| Personal study notes (uploaded markdown) | Local file |
| Quiz sessions in chat | Ongoing — Domains 1–3 covered, Domain 4 pending |

## Exam logistics

| Topic | Link |
|---|---|
| Certification FAQs (retake, scoring, results timing) | https://aws.amazon.com/certification/faqs/ |
| Before-testing policies (reschedule, cancel, refunds) | https://aws.amazon.com/certification/policies/before-testing/ |

**Key policies:** reschedule or cancel free up to 24 hours before the appointment; each appointment can be rescheduled twice. A failed attempt means a 14-calendar-day wait and the full fee again. Results arrive within five business days. Passing any AWS exam unlocks a 50% discount voucher toward the next one.

---

## What NOT to use

- **Braindump sites** advertising "real exam questions" or hundreds of verbatim items. These violate the AWS Certification Agreement and can get a certification revoked.
- **Another full video course** (Stephane Maarek, Adrian Cantrill). Both are good, but a 15-hour course does not fit in three weeks alongside everything else, and it would re-cover ground you already have.

---

## Current status

| Date | Test | Result |
|---|---|---|
| 18 Sep | Tutorials Dojo, 65 questions | 58% raw, **~55% weighted** |
| 25 Sep | Framework gap drill, 8 questions | 63% |
| 4 Oct | AWS Cloud assessment, 20 questions | **40%** |

| Domain | Weight | Last measured | Priority |
|---|---|---|---|
| Security and Compliance | 30% | 25–50% | **1 — largest point pool, weakest showing** |
| Billing, Pricing and Support | 12% | 25–33% | **2 — cheapest points on the exam** |
| Cloud Concepts | 24% | 58–75% | 3 — mostly the two frameworks |
| Cloud Technology and Services | 34% | 33–69% | 4 — broadest, but strongest |

**Outstanding:** no full 65-question timed test since 18 September. That number is the one decision input still missing.

**Exam:** Friday 9 October, 8:00 AM Chicago (check-in 7:30 AM). Free reschedule closes **Thursday 8:00 AM** — one reschedule remaining on this booking.

## Study order for the remaining days

1. Full 65-question timed test — the diagnostic that decides whether to keep the date
2. Tier 1 topics from the memorization sheet's "Start here" section
3. Recall deck in flagged-only mode, Security and Billing filters first
4. Part 5 of the memorization sheet — the concept-pair table — the night before
