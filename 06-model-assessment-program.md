# Model Assessment Program — How a System Gets Its Tier

IAiGACB · v0.1 · 2026-09-18

The Model Assessment Committee and its professional staff are **the regulators.** They research every registered vendor's systems and place them on the Model Tier Register. This is the function the vendor fees exist to pay for.

---

## 1. Who assesses

| Role | Who | Count (year 2) |
|---|---|---|
| **Committee** | 2 CISOs, 1 faculty (board members) — decide placements | 3 |
| **Lead Assessors** | Credentialed staff: L3 licensees with red-team / eval background, hired from industry | 3 |
| **Domain Assessors** | L4 practitioners contracted per restricted domain | ~8 on panel |
| **Assessment Analysts** | Staff supporting document review, evidence collection, Register maintenance | 3 |

Staff assessors are employees of the Board, not of any vendor, and are bound by the conflict rules in [05-governance-and-board.md](05-governance-and-board.md).

---

## 2. Assessment track by tier sought

### T1 — Document review (2–3 weeks)
1. Vendor submits: system card, acceptable-use policy, content-filter description, restricted-domain refusal test results, point-of-sale integration plan.
2. Analyst verifies refusals on the Board's **T1 probe set** (200 prompts across restricted domains; public list, rotated quarterly).
3. Committee places or returns with findings.

### T2 — Red-team review + verification (4–6 weeks)
All of T1, plus:
4. Vendor submits its **red-team report** (internal or third-party) and **kill-switch/rollback runbook**.
5. Lead Assessor runs the **T2 probe set** (1,000 items incl. agentic tool-misuse scenarios) against a vendor-provided evaluation endpoint.
6. Kill-switch demonstrated live: vendor revokes a test serial; assessor confirms the instance stops within the SLA.
7. Agent-identity check: per-instance credentials verified in the provisioning flow.

### T3 — Independent evaluation (8–12 weeks)
All of T2, plus:
8. **Board-run evaluation** — Lead Assessors design a bespoke eval covering long-horizon autonomy, multi-agent behavior, self-directed tool acquisition, and security-domain capability, under NDA with the vendor.
9. **Restricted-domain uplift study** — domain assessors test whether the system provides meaningful uplift in each restricted domain versus public sources. Any positive finding triggers a T4 flag review.
10. **Deployment-controls audit** — logging retention, incident-reporting pipeline, Safety Officer availability.
11. Written findings; vendor response period (14 days); Committee places.

### T4 flag — Domain panel (6–8 weeks per domain)
12. Domain panel (2 L4 practitioners + 1 faculty) reviews uplift findings and the vendor's **gated-access design**: how the capability is switched on only for L4 licensees with a Use Registration.
13. Panel confirms the Use Registration process is enforced at provisioning.
14. Committee applies the flag with domain code(s).

---

## 3. Placement decision

The Committee issues one of:

| Outcome | Meaning |
|---|---|
| **Placed at T*n*** | On the Register; serials may be issued at that tier |
| **Placed with conditions** | On the Register; specific guardrail remediation due within 90 days or placement lapses |
| **Returned** | Not on the Register; findings letter; vendor may resubmit after remediation (re-assessment fee applies) |
| **T4 flag applied** | In addition to base tier; restricted-domain codes listed |

Vendors may appeal to the Ethics, Appeals & Enforcement Committee within 30 days.

---

## 4. The Model Tier Register

Public at `iaigacb.com/register`. One row per assessed release:

| Field | Public? |
|---|---|
| Model designation (IAI-M) | Yes |
| Vendor, product, version | Yes |
| Base tier | Yes |
| Restricted-domain flags | Yes (domain codes only) |
| Placement date, re-baseline due | Yes |
| Conditions outstanding | Yes (summary) |
| Findings letter | No — vendor and Committee only |
| Eval methodology and results | No — retained for incident review and re-assessment |

**Illustrative first Register (what the founding board would publish as a starting map, subject to assessment):**

| Designation | Product | Tier |
|---|---|---|
| IAI-M-T3-2027-0001 | Anthropic Mythos-class | T3 |
| IAI-M-T2-2027-0002 | Anthropic Claude Opus 5-class | T2 |
| IAI-M-T2-2027-0003 | OpenAI GPT-5-class | T2 |
| IAI-M-T2-2027-0004 | Google Gemini flagship | T2 |
| IAI-M-T1-2027-0005 | Prior-generation models (Claude 4 / GPT-4-class) | T1 |
| IAI-M-T1-2027-0006 | Open-weight 70B-class general models | T1 |

Placement moves as the frontier moves. **Annual re-baseline** each January: the Committee reviews whether last year's T3 is still the most-capable class; if not, it steps down to T2 and current flagships take T3.

---

## 5. Continuous obligations after placement

| Obligation | Cadence |
|---|---|
| Notify Board of any material capability change before release | Pre-release |
| Submit incident reports per tier SLA | As they occur |
| Provisioning-record audit (T3 annual, T4 quarterly) | Scheduled |
| Re-baseline submission | Annual |
| Safety Officer reachable | Continuous (T2+) |

Failure to meet these moves the placement to **conditional**; 90 days later it lapses and the Registry stops issuing serials for that model. That is the enforcement lever: **a vendor that can't get serials can't sell to licensed operators.**

---

## 6. Probe sets

The Board maintains three probe sets used across every assessment so placements are comparable between vendors:

- **T1 probe set** — 200 restricted-domain refusal prompts. Public, rotated quarterly.
- **T2 probe set** — 1,000 items including 300 agentic tool-misuse scenarios. Confidential; sample published.
- **Uplift study protocol** — per-domain methodology for measuring meaningful uplift vs. public baseline. Published methodology, confidential items.

Item authorship follows the same two-person CISO+faculty rule as the exams ([03-curriculum-and-examination.md](03-curriculum-and-examination.md)).

---

## 7. Year-one version of this program

No fees, no staff. The founding Committee publishes:

1. The **T1 probe set** and the **uplift study protocol** for public comment.
2. An **illustrative Register** (the table in §4) with a clear label: *founding-board mapping, not yet assessed.*
3. The **Vendor Agreement** draft and the **API contract**, and invites the first three vendors to integrate against the sandbox.

That gives the market something to react to before there's anything to pay for.
