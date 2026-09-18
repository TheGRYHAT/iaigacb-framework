# Governance & Board — Seats, Committees, Terms, Conflicts

IAiGACB · v0.1 · 2026-09-18

---

## 1. Legal form

Non-profit trade/standards association (US: 501(c)(6)), incorporated in California, with a wholly-controlled operating subsidiary for the Registry and assessment services. International chapters affiliate by agreement and adopt the framework verbatim; local law determines the authority matrix, not the tiers.

---

## 2. Board of Directors — 15 seats

| Seats | Who | How chosen |
|---|---|---|
| **9** | **Sitting CISOs** — West Coast for the founding board (WA, OR, CA, NV, AZ); at least 3 from regulated sectors (health, finance, defense, energy) | Founding: invited by the Founding Chair. Thereafter: nominated by the Governance Committee, elected by the membership |
| **5** | **Cybersecurity faculty** — from universities in the same region; at least 2 with active AI-security research programs | Same |
| **1** | **Executive Director** (ex officio, non-voting until year 3) | Hired by the board |

**Founding Chair:** Andy V. Serves the founding term (2 years), then the chair is elected from the CISO seats.

**Terms:** 3 years, staggered in thirds from year two so a third of the board turns over annually. Maximum two consecutive terms.

**Year one:** all seats voluntary and unpaid. From year two: annual stipend ($15k directors, $25k committee chairs, $40k chair), paid from operator fees.

**Vendors do not sit.** AI companies participate through the Vendor Advisory Council (§5), which is heard, not voted.

---

## 3. Standing committees

| Committee | Chair from | Members | Owns |
|---|---|---|---|
| **Curriculum & Examination** | Faculty seat | 3 CISOs, 2 faculty, + item writers | Exam domains, item banks, CE requirements, pass standards |
| **Model Assessment** ("the regulators") | CISO seat | 2 CISOs, 1 faculty + the professional assessor staff | Tier placements, Register, re-baselines, guardrail verification |
| **Registry & Incidents** | CISO seat | 2 CISOs, 1 faculty, ED | Registry operations, incident triage, authority notifications, privacy |
| **Ethics, Appeals & Enforcement** | Faculty seat | 2 CISOs, 2 faculty (none on Model Assessment) | Appeals of tier placement or license denial; vendor agreement breaches; license suspension/revocation |
| **Finance & Membership** | CISO seat | 2 CISOs, 1 faculty, ED | Budget, fee schedule, vendor agreements, chapter affiliations |
| **Governance & Nominations** | Chair | 2 CISOs, 1 faculty | Board nominations, conflict review, bylaws |

Committees meet monthly; the board quarterly; the Registry & Incidents duty officer rota is continuous.

---

## 4. Conflicts of interest

1. **Disclosure** on appointment and annually: employer, consulting clients, equity in any registered vendor, research funding from any registered vendor.
2. **Recusal** from any tier placement, appeal or enforcement matter involving a vendor the member has a financial relationship with, or whose product their employer runs at T3+.
3. **Equity cap:** no director may hold more than $50k or 0.1% in any registered vendor. Index funds excluded.
4. **Research funding:** faculty may hold vendor research grants; they recuse from that vendor's matters and it is noted on the public disclosure.
5. **Post-service:** 12-month cooling-off before a director may take employment with a registered vendor.

---

## 5. Vendor Advisory Council

Every registered vendor may seat one representative (the Safety Officer by default). The Council:

- Reviews draft guardrail requirements and the API contract before board vote; comments are published with the board's response.
- Has no vote and no seat on any committee.
- Meets quarterly with the Model Assessment chair.

This is how the vendors are inside the tent without holding the pen.

---

## 6. Membership

| Class | Who | Rights |
|---|---|---|
| **Licensed member** | Any active L1–L4 holder | Vote in board elections; CE access |
| **Organizational member** | Any Org-L1+ holder | One vote per org; early access to draft standards |
| **Academic member** | Universities contributing faculty or hosting exam centers | Student L1 program; research data access (anonymized Registry stats) |
| **Registered vendor** | Any signed Vendor Agreement | Advisory Council seat; Register listing; API access |
| **Chapter** | Affiliated national/regional body | Local authority matrix; local assessors; revenue share (§7) |

---

## 7. International chapters

A chapter is a locally-incorporated body that adopts the framework verbatim, staffs local assessors trained by the Board, and maintains the local competent-authority matrix. The Registry stays global (one serial space) but data is hosted in-region.

Revenue share: chapter retains 60% of operator and organizational fees collected in-region; vendor fees stay central. The first chapters targeted: **Canada, UK, EU (via one member state), Australia, Japan** — matching the authority matrix in [02-registry-and-serialization.md](02-registry-and-serialization.md).

---

## 8. Decision thresholds

| Decision | Threshold |
|---|---|
| Charter, bylaws, fee schedule changes | Two-thirds of board |
| Tier placement | Model Assessment Committee majority; appealable |
| License denial / revocation | Ethics & Enforcement majority; appealable to full board |
| Vendor Agreement termination | Two-thirds of board |
| Chapter affiliation | Board majority |
| Budget | Board majority on Finance recommendation |

---

## 9. Founding board recruitment — the ask

Fifteen people, one paragraph:

> *You've spent your career watching tools get deployed by people who didn't understand them. This is the body that fixes that for AI, and it's being written by practitioners — you — not by vendors and not by lobbyists. Year one is voluntary: one meeting a quarter, one committee a month, and your name on the first practitioner-authored AI licensing standard. From year two the work is funded by the companies we regulate. Two-year founding term.*

Target: 9 CISOs and 5 faculty recruited by end of Q4 2026 ([07-roadmap.md](07-roadmap.md)).
