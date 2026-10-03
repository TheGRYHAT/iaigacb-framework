# IAiGACB — International AI Governance and Certification Board

**Founding framework · v0.1 · 2026-09-18 · Founding Chair: Andy V**

AI systems are tiered by capability (T1–T4). Operators are licensed by skill (L1–L4). A vendor may only sell a Tier-n system to an operator at Level ≥ n. Every deployed AI is serialized to the license that bought it. CISOs and cybersecurity faculty write the standard; the AI companies pay for the regulator.

## Why this is free

This framework is community-built. We only started it.

It is given away under the [Creative Commons Attribution 4.0](LICENSE) license: use it, adapt it, teach it, build on it, with credit to the source. It began as one practitioner's answer to a problem he'd watched for 27 years, tools deployed by people who didn't understand them, and it is offered as a give-back to the field, not as a product. The people who should write the rest of it are the CISOs, engineers, and faculty who have watched AI fail in production.

If it earns adoption, it goes to an independent, board-run non-profit so that no single company, including the one that sponsored the first draft, controls it. Until then this repository is the canonical text. The site at iaigacb.online is an earlier placeholder preview and will be rebuilt from these documents.

**To contribute:** open an issue or a pull request against any document. Every dollar figure, seat count, exam weight, and SLA in these drafts is explicitly proposed, not decided. Argue with it.

## Read in this order

| # | Doc | One line |
|---|---|---|
| 00 | [Charter](00-charter.md) | What the Board is, where its authority comes from, founding principles |
| 01 | [Certification framework](01-certification-framework.md) | The two ladders, the sale rule, guardrails by tier, restricted domains |
| 02 | [Registry & serialization](02-registry-and-serialization.md) | ID formats, data model, point-of-sale API, incident → FBI/authority protocol |
| 03 | [Curriculum & examination](03-curriculum-and-examination.md) | L1–L4 domains, exams, labs, org certification |
| 04 | [Fees & funding](04-fee-schedule-and-funding.md) | 0.5% vendor fee with $10k floor / $1M cap, assessment fees, operator fees, year-2 budget |
| 05 | [Governance & board](05-governance-and-board.md) | 9 CISOs + 5 faculty + ED, committees, conflicts, chapters |
| 06 | [Model assessment program](06-model-assessment-program.md) | How the regulators place a system on the Register |
| 07 | [Roadmap](07-roadmap.md) | Q4 2026 founding → 2027 voluntary year → 2028 fees on |

Diagram: [`diagrams/iaigacb-framework.drawio`](diagrams/iaigacb-framework.drawio) · [Framework PNG](diagrams/iaigacb-framework.drawio.png) · [Governance PNG](diagrams/iaigacb-governance.drawio.png) · [PDF](diagrams/iaigacb-framework.pdf)

## The ladder on one screen

```
  SYSTEM TIER (assigned to the AI)        OPERATOR LEVEL (earned by the person/org)
  ─────────────────────────────────       ──────────────────────────────────────────
  T4  Restricted-domain flag              L4  Restricted-Domain Licensee (per domain)
      CBRN · bio · offensive cyber ·          L3 + domain credential + background check
      autonomous weapons · infra control       + Use Registration for every provisioning
  T3  Frontier Advanced  (Mythos-class)   L3  Licensed AI Systems Manager
  T2  Frontier Pro       (Opus 5-class)   L2  Licensed AI Professional
  T1  General Assistant  (below frontier) L1  Licensed AI Operator

  SALE RULE:  Tier n  →  requires Level ≥ n at point of sale  →  serial issued, bound to the cert
```

## What's decided vs. what's proposed

**Decided by the founder (this draft):** two ladders, the sale rule, serialization, practitioner-only board, voluntary year one, vendors fund the regulator, T4 for restricted domains, incident → law-enforcement notification via the Registry.

**Proposed for board ratification:** every dollar figure in 04, seat counts in 05, exam weights and pass marks in 03, the illustrative Register in 06, SLAs in 01/02.

## Next actions

1. Founding board recruitment — the ask is written in [05 §9](05-governance-and-board.md).
2. Counsel: 501(c)(6) formation + trademark filings.
3. Site + sandbox Registry on `iaigacb.com` (GRYHAT in-kind).
4. Long domain → 301 to `iaigacb.com`.
