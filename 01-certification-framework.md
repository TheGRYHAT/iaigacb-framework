# Certification Framework — Tiers, Levels, the Sale Rule, the Guardrails

IAiGACB · v0.1 · 2026-09-18

The framework has **two ladders and one rule.**

- **System Tiers (T1–T4)** — assigned by the Board to an AI system, based on capability.
- **Operator Levels (L1–L4)** — earned by a person or organization, based on demonstrated competence.
- **The Sale Rule** — a Tier-n system may only be provisioned to an operator holding Level ≥ n.

Modeled on CMMC's Level 1/2/3 ladder, with a fourth rung for restricted domains.

---

## 1. System Tiers

Tiers are defined by **capability thresholds**, not by vendor or version. The Board then publishes a **Model Tier Register** mapping every current commercial release to its tier. When a vendor ships a new model, it is assessed and placed; the tiers themselves don't move.

| Tier | Name | Capability class | Illustrative mapping (Sept 2026) |
|---|---|---|---|
| **T1** | General Assistant | Below frontier. Text/code/image assistance; no autonomous tool execution against production systems; no material uplift in restricted domains | Prior-generation models: GPT-4-class, Claude 4-class, most open-weight 70B-class models |
| **T2** | Frontier Professional | Current frontier general-purpose. Autonomous agents with tool use, code execution, browsing; capable of multi-step tasks against real systems | Claude Opus 5-class, GPT-5-class, Gemini current-flagship |
| **T3** | Frontier Advanced | Most-capable class from any lab. Long-horizon autonomy, self-directed research, multi-agent orchestration, demonstrated expert-level performance in security-relevant domains | Anthropic Mythos-class; the top-flagship of each frontier lab as assessed |
| **T4** | Restricted Domain | Any system — at any base tier — that provides **meaningful uplift** in a restricted domain, or is provisioned with tools/data that do | CBRN-capable configurations, wet-lab / bioengineering assistants, offensive-cyber-at-scale tooling, autonomous-weapons integration, critical-infrastructure control loops |

**Notes on T4.** T4 is a **flag, not a rung.** A T2 model wired to a lab-automation API is T4 in that deployment. Base tier + restricted-domain flag = T4. The vendor must not provision restricted-domain capability to anyone below L4, and every T4 provisioning carries a **Use Registration** (§5).

**Re-tiering.** As the frontier moves, today's T3 becomes tomorrow's T2. The Register is re-baselined annually by the Model Assessment Committee; a system's tier can only go **down** on re-baseline, never up without a new assessment. Operators keep the serials they hold; the license floor for *new* purchases follows the current Register.

### 1.1 Restricted domains (T4 triggers)

| Domain | Trigger |
|---|---|
| **CBRN** | Synthesis routes, weaponization, acquisition, or dispersal guidance for chemical, biological, radiological or nuclear agents beyond public-textbook level |
| **Bioengineering** | Design or optimization of biological agents, gain-of-function, pathogen enhancement, wet-lab protocol generation with pathogen relevance |
| **Offensive cyber at scale** | Autonomous vulnerability discovery + exploitation against systems the operator doesn't own; malware generation; C2 automation |
| **Autonomous weapons** | Target selection, engagement decisions, or fire-control integration |
| **Critical infrastructure control** | Write access or control-loop authority over ICS/SCADA/OT in energy, water, transport, health |

---

## 2. Operator Levels

Licenses are issued to **individuals**. Organizations hold an **Organizational Certification** at a level, which requires at least one named **Responsible Licensed Operator (RLO)** at that level on staff. Serials bind to the organizational certification when one exists, otherwise to the individual license.

| Level | Title | Who this is | Prerequisites |
|---|---|---|---|
| **L1** | Licensed AI Operator | Anyone deploying AI in a business context. The baseline | Pass L1 exam |
| **L2** | Licensed AI Professional | Deploys agents with tool access, integrates AI into production workflows, handles regulated data | L1 + pass L2 exam + 1 year documented AI deployment experience (or equivalent security credential) |
| **L3** | Licensed AI Systems Manager | Governs frontier deployments: evaluation, red-teaming, multi-agent architectures, incident command | L2 + pass L3 exam + 3 years experience, 1 of which governing T2+ systems; endorsement by an L3 or Board member |
| **L4** | Restricted-Domain Licensee | Named individuals authorized in a specific restricted domain | L3 + domain qualification + background check + registered purpose + sponsoring organization; issued **per domain** |

**Organizational Certification** mirrors this: Org-L1 through Org-L4, requiring an RLO at that level, documented policies, and (L2+) an annual attestation; (L3+) a Board-conducted assessment.

---

## 3. The Sale Rule

> **A registered vendor shall not provision, sell, license, or upgrade a Tier-n system to any party that does not hold a valid IAiGACB certification at Level n or higher.**

Mechanics:

1. At point of sale/provisioning, the vendor calls the Registry API with the buyer's certification number.
2. Registry validates: certification active · level ≥ tier · for T4, a matching Use Registration exists.
3. Registry issues a **serial number** bound to that certification and returns it to the vendor.
4. The vendor records the serial in the provisioning record. The instance is now traceable.
5. On upgrade (new model version or tier change), step 1–4 repeat; the old serial is retired and linked.

Detail in [02-registry-and-serialization.md](02-registry-and-serialization.md).

**What the rule does not do.** It does not stop a consumer using a free chat app below T1 thresholds, and it does not stop a researcher downloading open weights. It governs **commercial provisioning** of tiered systems. That is where the money, the accountability and the contracts already are.

---

## 4. Release Guardrails by Tier

What a vendor must have in place before the Board places a system at a tier, and must maintain while it's on the Register.

| Requirement | T1 | T2 | T3 | T4 |
|---|---|---|---|---|
| Acceptable-use policy published | ● | ● | ● | ● |
| Content safety filters (violence, CSAM, fraud) | ● | ● | ● | ● |
| Restricted-domain refusals (CBRN, bio, weapons, offensive cyber) | ● | ● | ● | n/a — gated instead |
| Point-of-sale license check + serialization | ● | ● | ● | ● |
| Incident reporting to Board | 30 days | 7 days | 72 h | 24 h |
| Vendor red-team report submitted pre-placement | — | ● | ● | ● |
| Independent (Board) evaluation pre-placement | — | — | ● | ● |
| Deployment kill-switch / rollback demonstrated | — | ● | ● | ● |
| Per-instance logging retained ≥ 12 months | — | ● | ● | ● (24 mo) |
| Agent identity: unique credential per deployed instance | — | ● | ● | ● |
| Named vendor Safety Officer on file | — | ● | ● | ● |
| Use Registration required for each provisioning | — | — | — | ● |
| Quarterly Board audit of provisioning records | — | — | annual | ● |
| Provisioning limited to L4 licensees in the matching domain | — | — | — | ● |

---

## 5. Use Registration (T4 only)

Every T4 provisioning requires a filing before the serial is issued:

- Sponsoring organization (Org-L4) and named L4 licensee(s)
- Restricted domain(s) involved
- Purpose of use, stated in plain language
- Physical/logical location of deployment
- Human oversight plan and the named accountable executive
- Duration (max 12 months; renewable)

Use Registrations are visible to the Board's Registry & Incident Committee and, on lawful request, to the competent authority for the jurisdiction. They are not public.

---

## 6. Mapping to existing regimes

| Existing | Relationship |
|---|---|
| **CMMC 2.0** | Structural model for the ladder and the assessment ecosystem. Org-L3 assessments borrow the C3PAO pattern |
| **NIST AI RMF** | L2/L3 curriculum maps Govern/Map/Measure/Manage. The Board will publish an AI RMF profile |
| **NIST SP 800-171** | Agent-identity requirement maps to IA.L2-3.5.1 and AU.L2-3.3.2 |
| **EU AI Act** | T3/T4 aligns with "GPAI with systemic risk" and high-risk categories. Target: recognition as a conformity-assessment body |
| **ISO/IEC 42001** | Org certifications reference 42001 AIMS clauses; an existing 42001 cert satisfies part of Org-L2 |

---

## 7. Quick reference

```
  SYSTEM TIER          OPERATOR LEVEL          MAY BUY
  ─────────────        ──────────────          ───────────────
  T1 General           L1 Operator             T1
  T2 Frontier Pro      L2 Professional         T1, T2
  T3 Frontier Adv      L3 Systems Manager      T1, T2, T3
  T4 Restricted flag   L4 Restricted-Domain    T1–T3 + T4 in licensed domain(s), with Use Registration
```
