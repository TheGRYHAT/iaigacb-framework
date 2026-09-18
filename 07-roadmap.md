# Roadmap — Founding → Voluntary Year → Funded Operation

IAiGACB · v0.1 · 2026-09-18

---

## Phase 0 — Founding · Q4 2026

**Goal:** a legal entity, a board, a published v1.0 framework, two live domains.

| Workstream | Deliverable | Owner |
|---|---|---|
| Legal | 501(c)(6) formed in California; bylaws adopted from [05](05-governance-and-board.md); trademark filings for the name and marks | Founding Chair + counsel |
| Board | 9 CISOs + 5 faculty recruited and seated; first meeting; charter ratified | Founding Chair |
| Framework | Docs 00–08 revised by the founding board and published as **v1.0** | Board |
| Web | `iaigacb.com` live: framework, tier ladder, illustrative Register, board roster, "get notified" for exams. Long domain 301s to it | GRYHAT (in-kind) |
| Registry | Sandbox API stood up per [02](02-registry-and-serialization.md); synthetic vendors; `/verify` working with checksums | GRYHAT (in-kind) |

**Exit criteria:** entity exists, 15 seats filled, v1.0 published, sandbox answers `/v1/provision`.

---

## Phase 1 — Voluntary Year · 2027

**Goal:** adoption before revenue. Prove the exams, the Register and the API with real people and real vendors, all free.

| Quarter | Milestone |
|---|---|
| **Q1** | L1 item bank complete (Curriculum Committee). T1 probe set published for comment. Vendor Agreement + API contract published. First 3 vendors invited to sandbox |
| **Q2** | **L1 exam pilot** — 500 free seats via member universities and board members' organizations. First vendor integrates the sandbox `/provision` call |
| **Q3** | L2 item bank + lab complete. **L2 exam pilot** — 150 seats, targeting board members' own staff. Illustrative Register reviewed against real submissions; first *actual* T1/T2 placements (no fee) |
| **Q4** | Pilot results published. Pass standards set. Fee schedule ratified with 90-day notice. First Org-L1/L2 self-attestations accepted. Registry moved to production infrastructure |

**Year-one numbers to hit:** 500 L1 holders · 100 L2 holders · 3 vendors signed · 10 systems on the Register · 1 university chapter agreement · 0 fees collected.

**What the board is really doing in year one:** turning its own organizations into the first licensed operators. If a founding CISO's company won't get Org-L2, nobody else will.

---

## Phase 2 — Funded Operation · 2028

**Goal:** fees on, staff hired, the sale rule live with the first vendors.

| Quarter | Milestone |
|---|---|
| **Q1** | Fees live. Vendor registrations invoiced. First Lead Assessor and Registry engineer hired. **Sale rule enforced** by the first signed vendors at production `/provision` |
| **Q2** | First paid **T3 assessment** (8–12 weeks). L3 item bank + capstone complete; L3 exam opens. Board stipends begin |
| **Q3** | First **Org-L3 assessment** delivered. L4 domain panels formed for BIO and OFC. First T4 flag review |
| **Q4** | Annual re-baseline of the Register. First public incident statistics. Chapter agreements signed with 2 of: Canada, UK, EU member state, Australia, Japan |

**Year-two numbers:** 12 vendors · 40 assessments · 5,000 L1 · 800 L2 · 60 L3 · 10 L4 · 200 orgs · ~$7.7M revenue ([04](04-fee-schedule-and-funding.md)).

---

## Phase 3 — International & Recognition · 2029+

| Track | Target |
|---|---|
| **Chapters** | 5 chapters live; global Registry, in-region hosting; local assessor corps trained |
| **Regulator recognition** | Application as EU AI Act conformity-assessment body via an EU chapter; NIST AI RMF profile published; engagement with US state AI statutes (CA, CO, NY) for safe-harbor recognition of IAiGACB certification |
| **Insurance** | Two carriers offering premium credit for Org-L2+ |
| **Procurement** | IAiGACB level as a line item in public-sector AI procurement templates (starting with California state and county) |
| **Register** | Every commercially provisioned frontier system placed; T4 gating standard across the top labs |

---

## Critical path

```
Board seated ──► v1.0 published ──► L1 pilot ──► L2 pilot ──► Fees ratified ──► Staff hired ──► T3 assessment
      │                 │                                                             │
      └── Legal entity  └── Sandbox API ──► First vendor integrates ──► Sale rule live ┘
```

Two things gate everything: **fifteen names on the board** and **one vendor integrating the API.** Everything else is sequencing.

---

## Risks the roadmap is built around

| Risk | Where it's handled |
|---|---|
| Nobody adopts a standard with no adopters | Year one is free; the board's own orgs certify first |
| Vendors won't sign a sale restriction | Vendor Advisory Council shapes the API; first signatories get founding-vendor recognition and a fee holiday for year two |
| Tier mapping goes stale | Annual re-baseline; tiers by capability, not brand |
| Board capture by a large vendor | 25% revenue cap per vendor; no vendor seats; equity limits |
| Assessors can't be hired at volunteer rates | Fees fund credentialed staff from Phase 2; no T3 assessments promised before then |
| "International" is a name, not a fact | Chapters from Phase 2; authority matrix from day one |
