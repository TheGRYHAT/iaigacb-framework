# Curriculum & Examination — What Each Level Must Know

IAiGACB · v0.1 · 2026-09-18

**Authored by the Curriculum & Examination Committee — sitting CISOs and faculty — from real deployments, not from vendor documentation.** Every domain below traces to something that has gone wrong in production. The exam refreshes twice a year against the incident record.

---

## 1. Design rules

1. **Scenario-based, not trivia.** Items present a deployment situation and ask what the operator does. No "which company released model X."
2. **Vendor-neutral.** Products appear only as examples. The competency is the same whether the model is from Anthropic, OpenAI, Google or an open-weight lab.
3. **Incident-driven refresh.** Each S1/S2 incident in the Registry generates a candidate item within 90 days.
4. **Practical component from L2 up.** L2 has a lab; L3 has a capstone; L4 has a domain board interview.
5. **Proctored.** Online proctored for L1/L2, testing-center or Board-proctored for L3/L4.

---

## 2. L1 — Licensed AI Operator

**Who:** anyone putting AI to work in a business. The baseline license. Target: pass rate ~75% for a diligent candidate with 20 hours' preparation.

| Domain | Weight | What they must be able to do |
|---|---|---|
| 1. How these systems work | 15% | Explain, at a working level, what a model does and doesn't know; context windows; hallucination; why output isn't fact |
| 2. Data handling | 25% | Recognize regulated data (PII, PHI, CUI, card data); know what may not go into a prompt; vendor data-retention settings; the difference between a consumer app and an enterprise tenant |
| 3. Prompt injection & manipulation | 20% | Recognize that content the AI reads can carry instructions; why "the document told the AI to do it" is a real attack; basic hygiene |
| 4. Acceptable use & restricted domains | 15% | What the Board's tiers are; what T4 means; what you must never ask for; the reporting duty |
| 5. Output verification | 15% | Check citations, check code before running it, check numbers; when a human must sign off |
| 6. The license itself | 10% | Your certification number, what it binds, serials, renewal, incident reporting |

**Exam:** 60 items · 90 minutes · online proctored · pass 70%.
**Renewal:** 2 years · 10 hours continuing education.

---

## 3. L2 — Licensed AI Professional

**Who:** builds and runs AI in production — agents with tool access, RAG over company data, AI in customer-facing workflows, AI touching regulated data.

| Domain | Weight | What they must be able to do |
|---|---|---|
| 1. Agent architecture & tool access | 20% | Design least-privilege tool scopes; sandbox execution; approve/deny gates on irreversible actions; separate read from write |
| 2. Agent identity & accountability | 15% | **One identity per agent** — own credential, own home, own audit trail, own egress; never let an agent act under a human's credentials ("evil twin"); map to IA.L2-3.5.1 / AU.L2-3.3.2 |
| 3. Data pipelines & retrieval | 15% | RAG data classification; embedding stores as a data breach surface; tenant isolation; vendor training opt-outs |
| 4. Prompt injection defense | 15% | Indirect injection via web, email, documents; instruction/data separation; output filtering; testing for it |
| 5. Logging, monitoring & incident response | 15% | What to log per instance; detecting autonomous misbehavior; the Board's severity scale; the 7-day clock; rollback |
| 6. Evaluation & testing | 10% | Building an eval set; regression on model upgrade; red-team basics |
| 7. Governance & the sale rule | 10% | Org certification; RLO duties; serialization at purchase and upgrade; vendor agreement obligations from the buyer side |

**Exam:** 100 items · 3 hours · online proctored · pass 72%.
**Lab:** 4-hour practical — candidate is handed a misconfigured agent deployment and must find and fix the tool-scope, identity and injection defects, then write the incident report.
**Prerequisite:** L1 + 1 year documented AI deployment experience, **or** an active CISSP / CISM / GIAC / CCSP in lieu of the year.
**Renewal:** 2 years · 20 hours CE, 5 of which from incident case studies.

---

## 4. L3 — Licensed AI Systems Manager

**Who:** governs frontier (T2/T3) deployments for an organization. The person the Board expects to pick up the phone in an incident.

| Domain | Weight | What they must be able to do |
|---|---|---|
| 1. Frontier-model governance | 20% | Tier assessment reading; what T3 capability means operationally; deployment decision frameworks; when *not* to deploy |
| 2. Evaluation & red-teaming | 20% | Design and run pre-deployment evals; adversarial testing; restricted-domain probing within legal limits; interpreting vendor red-team reports |
| 3. Multi-agent systems | 15% | Orchestration risk; agent-to-agent trust; cascade failures; kill-switch design across a fleet |
| 4. Supply chain | 10% | Model provenance; weights integrity; third-party tools and MCP-style connectors as supply chain; vendor Safety Officer relationship |
| 5. Incident command | 15% | Running an S1/S2; authority notification; evidence preservation; post-incident review; Register feedback |
| 6. Regulatory mapping | 10% | EU AI Act obligations; NIST AI RMF; sector rules; how IAiGACB certification satisfies each |
| 7. Program leadership | 10% | Building the org's AI governance program; RLO duties at scale; board reporting; budgeting for assessment |

**Exam:** 120 items · 4 hours · testing center · pass 75%.
**Capstone:** written governance program for a provided T3 deployment scenario, defended in a 45-minute interview with two L3 assessors.
**Prerequisite:** L2 + 3 years experience (1 governing T2+ systems) + endorsement by an L3 licensee or Board member.
**Renewal:** 3 years · 40 hours CE · one capstone refresh.

---

## 5. L4 — Restricted-Domain Licensee

**Who:** named individuals authorized to operate T4 capability in a specific domain. Issued **per domain**; each is its own endorsement.

| Component | Requirement |
|---|---|
| Base | Active L3 |
| Domain qualification | Documented professional standing in the domain (e.g., for BIO: BSL-2+ lab credential or equivalent; for OFC: recognized offensive-security credential + employer authorization letter; for CIC: ICS/OT credential + asset-owner sponsorship) |
| Background check | Board-contracted; refreshed every 2 years |
| Sponsoring organization | Must hold Org-L4 in the same domain |
| Domain board interview | 90 minutes with the domain panel (two L4 practitioners + one faculty) — purpose, oversight plan, failure modes, stop conditions |
| Registered purpose | Filed as part of the first Use Registration |

**Renewal:** annual · re-interview every 3 years · immediate review on any S1/S2 incident involving the licensee's serials.

---

## 6. Organizational Certification

| Level | Requires |
|---|---|
| **Org-L1** | One L1 RLO · AI acceptable-use policy · self-attestation |
| **Org-L2** | One L2 RLO · policies for data handling, agent identity, incident response · annual self-attestation signed by an executive · ISO/IEC 42001 accepted in lieu of the policy review |
| **Org-L3** | One L3 RLO · Board-conducted assessment every 3 years (C3PAO pattern) · evidence of eval program, logging, kill-switch · annual attestation between assessments |
| **Org-L4** | Org-L3 + domain-specific controls + named L4 licensees + Use Registration process · annual Board audit |

---

## 7. Item development process

1. **Source.** Committee members submit anonymized scenarios from their own environments; Registry incidents feed candidates automatically.
2. **Draft.** Two-person authoring; one CISO, one faculty.
3. **Review.** Blind technical review + bias/clarity review.
4. **Pilot.** Unscored items seeded into live exams; kept if they discriminate.
5. **Publish.** Twice yearly. Retired items go into the public study guide 12 months later.

**Year one** produces the L1 and L2 item banks and pilots both exams free of charge. L3 and L4 are written in year two, once there are L2 holders to build from.
