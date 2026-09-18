# Charter — International AI Governance and Certification Board

**Short name:** IAiGACB · **Domains:** iaigacb.com · internationalaigovernanceandcertificationboard.com
**Status:** Founding draft v0.1 · 2026-09-18 · Founding Chair: Andy V · Founding sponsor: GRYHAT Cybersecurity

---

## 1. The one-paragraph version

AI is sold like software and deployed like a power tool. Nobody checks whether the buyer knows how to hold it. IAiGACB is the licensing body that closes that gap: **AI systems are tiered by capability, operators are licensed by skill, and a vendor may only sell a system to an operator licensed at or above its tier.** Every deployed AI is serialized to the license that bought it, so when something goes wrong there is a name, a level, and a phone number — not a mystery. The people who write the standard are the people who have watched it fail in production: working CISOs and the professors who train the next ones.

## 2. Mission

To establish and maintain an international, practitioner-led standard for the safe acquisition, deployment and operation of artificial intelligence, enforced through operator licensing, system serialization and vendor registration.

## 3. What the Board does

| Function | In one line |
|---|---|
| **Tier AI systems** | Assign every commercially released model a capability tier (T1–T4) after assessment |
| **License operators** | Examine and license individuals and organizations at levels L1–L4 |
| **Enforce the sale rule** | A registered vendor may only sell/provision a Tier-n system to an operator holding Level ≥ n |
| **Serialize deployments** | Bind every purchased or upgraded AI instance to the buyer's certification number |
| **Keep the Registry** | One database: who holds what license, which AI serials are bound to them, at what tier |
| **Notify on incident** | When an incident is reported, resolve the serial to the operator and notify the competent authority for that jurisdiction |
| **Register and assess vendors** | Every AI company registers; the Board's regulators research their systems and set the tier |
| **Write the curriculum** | CISOs author the exams from real-world deployments, refreshed as the technology moves |

## 4. What the Board is — and where its authority comes from

IAiGACB is a **private, practitioner-governed standards and certification body**, in the lineage of PCI SSC (payments), (ISC)² (security professionals) and the Cyber AB (CMMC). Its authority is **contractual and reputational**, and it is designed to compound:

1. **Vendor Agreement.** A registered AI company signs the IAiGACB Vendor Agreement: it will provision Tier-n systems only to operators at Level ≥ n, will call the Registry at point of sale to serialize, and will report incidents. The sale rule lives in that contract.
2. **Buyer demand.** Insurers, procurement offices and regulated industries ask for the license the same way they ask for SOC 2 or CMMC. Operators get licensed because the deals require it.
3. **Regulator recognition.** Once the Registry and tiering are running, the Board seeks recognition as a conformity-assessment body under national and regional AI regimes (EU AI Act notified body, NIST AI RMF profile, state-level AI statutes). Recognition converts a private standard into a compliance path.

Year one is voluntary on purpose — see [07-roadmap.md](07-roadmap.md). A standard nobody has adopted yet has no business charging for it.

## 5. Founding principles

1. **Practitioners write the standard.** Board seats go to sitting CISOs and cybersecurity faculty. No vendor holds a voting seat — vendors are the regulated party.
2. **Tier the capability, not the brand.** Tiers are defined by what a system can do, then a public register maps current products to tiers. When the technology changes, the mapping changes; the tiers don't.
3. **License the operator, not the enthusiasm.** Buying a Tier-3 system is a professional act. It requires a professional's license.
4. **Serial numbers, not press releases.** Every deployed instance traces to a license. Incident response starts from the Registry, not from a search.
5. **The regulated pay for the regulator.** Vendors fund the Board in proportion to their scale. Operators pay for their own certification. The Board stays independent of any single payer.
6. **Restricted domains are restricted.** CBRN, bioengineering, offensive cyber at scale, autonomous weapons and critical-infrastructure control sit behind Tier 4 / Level 4 with named individuals, registered purpose and audit.
7. **The agent gets a badge, not a key.** Every deployed system is an identified actor with its own credential, its own audit trail and its own accountable human. This is the same doctrine GRYHAT runs internally and it maps directly to NIST SP 800-171 IA.L2-3.5.1 and AU.L2-3.3.2.

## 6. Scope

**In scope:** commercially distributed AI systems (hosted APIs, on-prem weights, embedded agents) and the individuals and organizations that acquire and operate them.
**Out of scope for v1:** open-weight research releases with no commercial provisioning path (tracked in the Model Tier Register as "unprovisioned"; the operator side still applies when someone deploys them commercially), and consumer chat apps below Tier 1 thresholds.

## 7. Structure at a glance

```
                      ┌──────────────────────────────┐
                      │        BOARD OF DIRECTORS      │
                      │  9 CISOs · 5 faculty · 1 ED   │
                      └──────────────┬───────────────┘
        ┌──────────────┬─────────────┼─────────────┬──────────────┐
        ▼              ▼             ▼             ▼              ▼
  Curriculum &    Model Assessment  Registry &   Ethics, Appeals   Finance &
  Examination     (the regulators)  Incidents    & Enforcement     Membership
```

Detail in [05-governance-and-board.md](05-governance-and-board.md).

## 8. The documents in this framework

| # | Document | Answers |
|---|---|---|
| 00 | This charter | What the Board is and why |
| 01 | [Certification framework](01-certification-framework.md) | The tiers, the levels, the sale rule, the guardrails |
| 02 | [Registry & serialization](02-registry-and-serialization.md) | Numbers, database, point-of-sale API, incident notification |
| 03 | [Curriculum & examination](03-curriculum-and-examination.md) | What each level must know and how it's tested |
| 04 | [Fees & funding](04-fee-schedule-and-funding.md) | Who pays what |
| 05 | [Governance & board](05-governance-and-board.md) | Seats, committees, terms, conflicts |
| 06 | [Model assessment program](06-model-assessment-program.md) | How a system gets its tier |
| 07 | [Roadmap](07-roadmap.md) | Founding → voluntary year → funded operation |
| 08 | [Brand & domains](08-brand-and-domains.md) | Name, marks, the two .coms |

## 9. Ratification

This charter takes effect on adoption by a two-thirds vote of the founding board at its first convened meeting. Until then it is the founding chair's working draft.
