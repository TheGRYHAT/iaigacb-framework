# Registry & Serialization — Numbers, Database, Point-of-Sale API, Incident Notification

IAiGACB · v0.1 · 2026-09-18

The Registry is the Board's operational core. Everything else — licenses, tiers, the sale rule, incident response — is a read or a write against it.

---

## 1. Identifier formats

All IAiGACB identifiers share a prefix, a type code, and a checksum so they can be validated offline.

| Identifier | Format | Example | Issued to |
|---|---|---|---|
| **Vendor Registration** | `IAI-V-<seq5>-<chk>` | `IAI-V-00042-K` | An AI company on registration |
| **Model Tier Designation** | `IAI-M-T<tier>-<yyyy>-<seq4>-<chk>` | `IAI-M-T3-2026-0007-R` | A specific model release, on assessment |
| **Operator Certification** | `IAI-C-L<level>-<cc>-<seq8>-<chk>` | `IAI-C-L2-US-00012345-Q` | An individual (or organization, with `O` suffix on level: `L2O`) |
| **L4 Domain Endorsement** | `IAI-C-L4-<cc>-<seq8>-<dom>-<chk>` | `IAI-C-L4-US-00000117-BIO-M` | A named individual, per domain |
| **Use Registration** | `IAI-U-<yyyy>-<seq6>-<chk>` | `IAI-U-2027-000031-D` | A T4 provisioning |
| **AI Serial** | `IAI-S-T<tier>-<vendor5>-<seq10>-<chk>` | `IAI-S-T2-00042-0000123456-X` | Every provisioned/upgraded instance |

Domain codes: `CBR` CBRN · `BIO` bioengineering · `OFC` offensive cyber · `AWS` autonomous weapons · `CIC` critical-infrastructure control.
Checksum: mod-23 alphabetic (same family as a VIN check digit). `cc` = ISO 3166-1 alpha-2.

**Serials are permanent.** An upgrade retires a serial and issues a new one with a `supersedes` link. A serial is never reused.

---

## 2. Data model

```
vendors
  vendor_id (IAI-V)        legal_name        jurisdiction      revenue_band
  safety_officer           agreement_signed  status            registered_at

models
  model_id (IAI-M)         vendor_id          product_name      version
  base_tier                restricted_flags[] assessed_at       reassess_due
  guardrail_attestation    kill_switch_verified

operators
  cert_id (IAI-C)          type (indiv|org)   level             country
  legal_name               contact            status            issued_at   expires_at
  rlo_cert_id  (org only → the Responsible Licensed Operator)
  l4_endorsements[]        (domain, issued_at, expires_at, background_check_ref)

use_registrations
  use_id (IAI-U)           org_cert_id        licensee_cert_ids[] domains[]
  purpose                  location           oversight_plan     accountable_exec
  valid_from               valid_to           status

serials
  serial_id (IAI-S)        model_id           cert_id            use_id (nullable)
  issued_at                retired_at         supersedes_serial  provisioning_ref (vendor-side order id)
  deployment_locale        status (active|retired|suspended)

incidents
  incident_id              serial_id          reported_by (vendor|operator|third-party)
  severity (S1–S4)         domain_flags[]     summary             reported_at
  jurisdiction             authority_notified authority_ref       status
```

**Access.** Vendors read/write their own serials only. Operators read their own. The Registry & Incident Committee reads all. Law enforcement receives a scoped disclosure per incident, never a standing feed.

---

## 3. Point-of-Sale API

The vendor integrates one endpoint into checkout / provisioning. Sandbox during the voluntary year, production from Phase 2.

```
POST /v1/provision
Authorization: Bearer <vendor API key>

{
  "model_id":     "IAI-M-T2-2026-0003-J",
  "cert_id":      "IAI-C-L2O-US-00000881-F",
  "use_id":       null,                        // required when model has restricted_flags
  "order_ref":    "vendor-order-88213",
  "locale":       "US-CA"
}

200 OK
{ "serial_id": "IAI-S-T2-00042-0000123456-X", "issued_at": "...", "expires_with_cert": "2028-03-31" }

403 LEVEL_INSUFFICIENT     { "required": "L2", "held": "L1" }
403 USE_REGISTRATION_REQ   { "domains": ["BIO"] }
404 CERT_NOT_FOUND
410 CERT_EXPIRED
```

```
POST /v1/upgrade        { "serial_id", "new_model_id" }  → new serial, old retired with supersedes link
POST /v1/retire         { "serial_id", "reason" }
GET  /v1/verify/:cert   → { "level", "status", "expires_at" }   (public, rate-limited — lets anyone verify a license)
POST /v1/incident       { "serial_id", "severity", "summary", ... }
```

**Verification without the API.** The `/verify` endpoint and a public web lookup at `iaigacb.com/verify` let a buyer, insurer or auditor check any certification number. The checksum lets a form reject typos before it ever hits the network.

---

## 4. Incident notification protocol

| Step | Who | Deadline (by tier) |
|---|---|---|
| 1. Report to Registry (`POST /v1/incident`) | Vendor or operator — whoever knows first | T1 30d · T2 7d · T3 72h · T4 24h |
| 2. Serial → operator → jurisdiction resolved | Registry, automatic | immediate |
| 3. Severity triage | Registry & Incident Committee duty officer | 4h (S1/S2), 48h (S3/S4) |
| 4. Competent authority notified (S1/S2, or any T4) | Committee chair | 24h from triage |
| 5. Vendor + operator notified of authority referral | Committee | same day |
| 6. Post-incident review; Register/guardrail update if warranted | Model Assessment Committee | 30 days |

### Severity

| | Definition |
|---|---|
| **S1** | Loss of life, restricted-domain uplift realized, critical-infrastructure impact, or autonomous action causing material harm |
| **S2** | Data breach of regulated data via the AI; unauthorized autonomous action with financial impact; guardrail bypass in a restricted domain |
| **S3** | Guardrail bypass outside restricted domains; policy violation with contained impact |
| **S4** | Near-miss; misuse attempt blocked; operator error without harm |

### Competent authority matrix (initial)

| Jurisdiction | Primary | Secondary |
|---|---|---|
| **US** | FBI (field office / IC3) | CISA; sector regulator (FDA, FERC, etc.) |
| **Canada** | RCMP | Canadian Centre for Cyber Security |
| **UK** | National Crime Agency | NCSC; AI Safety Institute |
| **EU member states** | National CSIRT | EU AI Office; national DPA |
| **Australia** | AFP | ASD / ACSC |
| **Japan** | NPA | NISC |

The matrix expands as chapters form ([07-roadmap.md](07-roadmap.md)). Where no entry exists, the Committee notifies the operator's national CSIRT.

**What the authority receives:** serial, tier, operator identity and contact, RLO, Use Registration (if T4), vendor Safety Officer, incident summary. Not: the operator's full deployment inventory, other serials, or exam records.

---

## 5. Privacy and data handling

- Registry is hosted in-region for each chapter (US data in US, EU in EU).
- Individual license records: name, contact, level, status, expiry. No exam content, no scores retained beyond pass/fail.
- Public lookup exposes: certification number, level, status, expiry. **Not** the holder's name unless the holder opts in.
- Use Registrations are confidential; disclosed only per §4 or under lawful process.
- Retention: serials and incidents permanent; expired individual records 7 years.

---

## 6. Build notes (for whoever stands it up)

- Postgres, one schema, the tables above. Serial issuance is a single transaction with an advisory lock per vendor sequence.
- API keys per vendor, rotated annually, scoped to that vendor's `vendor_id`.
- Every write is append-only audited (who, what, when, from which key).
- Public `/verify` behind a CDN with per-IP rate limits; the checksum keeps garbage off the origin.
- Phase 1 (voluntary year) runs on a sandbox with synthetic vendors so the API contract is proven before any vendor integrates.
