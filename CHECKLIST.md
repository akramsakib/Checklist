# Israel-Nexus Technology Response Checklist

> **TLP:GREEN — Malaysian community only.** Derived working aid from Rectifyq **RQ-2026-0159**,
> *[Beyond Waze: Israel-Nexus Technology in Malaysia's Public Sector](https://rectifyq.com/my-only/2026-10-waze-ban-israel-nexus-technology)*
> ([BM version](https://rectifyq.com/my-only/2026-10-larangan-waze-teknologi-berkait-israel)), 21 Oct 2026.
> The source article is geo-restricted — **share the link, don't repost the article**. Keep this derived
> checklist within the community as well.

**For:** Malaysian public-sector, CNII and private organisations assessing technology with an Israeli nexus
**after the 20 Oct 2026 directive** (JKSN Meeting 3/2026: civil servants barred from Waze; PM advises TuJu).
**Approach:** act gradually, not abruptly — **Aware → Policy → Verify → Migrate at renewal**. Do not rip out
security tools mid-contract; that leaves gaps and can cause the incident you are trying to avoid.

> [!warning] **Fair-use caveat**
> An Israeli link is **not** evidence that a product is malicious or backdoored. This checklist maps
> **structural exposure** (data jurisdiction and access) so organisations can respond to a stated
> government policy. Nothing here alleges wrongdoing by any vendor or person.

---

## The test

> Is Malaysian data **within reach of Israeli law**?

Apply it consistently. Judge **where data goes** (checkable) — not who founded the vendor (not actionable).
**Risk ≈ nexus tier × access level × where the data goes.** Founder nationality is a dead end: many
Israel-founded security firms are now US-owned, and Microsoft, Google and AWS all have Israeli R&D or
Israeli government contracts.

---

## Phase 1 — Aware (0–3 months)

- [ ] List every security and SaaS product in **`vendor-inventory-template.csv`**, with its **current owner**,
      **where it is developed and supported**, **where its telemetry goes** and **when the contract ends**.
- [ ] Rank each product by **access level** (table below), highest access first.
- [ ] Block **Waze on official devices** through MDM, and apply location-history controls to **all**
      navigation apps. *(Official vs personal device scope is not stated in the circular — clarify with NACSA.)*
- [ ] Brief management with one line per product: category, access level, data destination, contract end date.

## Phase 2 — Policy (3–6 months)

- [ ] Add a **data-jurisdiction clause** to procurement and renewal templates: no storage, processing or
      access of Malaysian data in a restricted jurisdiction.
- [ ] Align with **Act 854** (NCII obligations), **NACSA** guidance and **PDPA** cross-border transfer rules.
- [ ] Make the clause mandatory for sub-processors, with **advance change notice**.

## Phase 3 — Verify (6–12 months)

- [ ] Get a **written guarantee** from each vendor covering, at minimum:
  - [ ] data and telemetry region
  - [ ] **no access from Israel** (R&D, support, SOC analysts, sub-processors)
  - [ ] sub-processor list with change notice
  - [ ] audit reports
  - [ ] exit assistance
- [ ] **Check it yourself:** monitor where agents and appliances actually send traffic (egress/dns logs,
      packet captures at the perimeter), and switch off optional "cloud sharing" features.
- [ ] Compare the guarantee against the vendor's **privacy notice and sub-processor list** — "no mention"
      in a privacy notice does **not** mean no data goes to Israel (support locations and sub-processors
      are where the gap shows).
- [ ] Give **less weight** to guarantees from Israel-headquartered vendors: a contract cannot override
      their home country's laws.

**Decision point — does the guarantee hold?**

- [ ] **Yes → Keep & monitor.** Record the guarantee and evidence; **re-attest yearly** (repeat Phase 3).
- [ ] **No → Phase 4, Migrate.**

## Phase 4 — Migrate (at contract renewal or end-of-life)

- [ ] Replace **only** where the guarantee fails. Time the switch to the **renewal date** to avoid sunk cost.
- [ ] Run old and new in parallel during cutover.
- [ ] **Rotate every credential** the old tool held (admin accounts, API keys, service accounts, certificates).
- [ ] Remove vendor remote access and revoke their accounts/sub-processor access.
- [ ] Put local alternatives — including **TuJu** — through the **same** security review. "Local" ≠ "reviewed".

---

## Access ranking — rank your inventory against this

Highest access inside your network first (condensed from the source assessment):

| # | Category | Why it matters | Examples with an Israeli nexus |
| --- | --- | --- | --- |
| 1 | SASE / secure web gateway | *All* traffic passes through the vendor's cloud | Cato Networks (Israel HQ); Zscaler, Palo Alto (Israeli R&D) |
| 2 | Privileged access (PAM) | Holds the passwords to admin accounts | CyberArk (now Idira, Palo Alto Networks) |
| 3 | Firewall / perimeter | Inline on every connection; vendor-pushed updates | Check Point (Israel HQ); Palo Alto Networks |
| 4 | EDR / XDR | Kernel-level agent on every laptop and server | SentinelOne, Cynet, Cybereason; CrowdStrike (Israel R&D) |
| 5 | OT / IoT monitoring | Sees inside CNII control systems | Claroty, Armis; Tenable OT (built on Indegy) |
| 6 | Cloud security | Reads cloud configs and snapshots | Wiz (now Google), Orca |
| … | Navigation app | Location and movement data | **Waze** (the banned app) |

## Nexus tiers — for the inventory's "tier" column

| Tier | Definition | Examples |
| --- | --- | --- |
| 1 | Israel-headquartered or Israel-controlled | Check Point, Cato, Radware, Cellebrite |
| 2 | Israel-founded, HQ abroad, core R&D in Israel | SentinelOne, Snyk, Claroty, Varonis |
| 3 | Non-Israeli firm with Israeli acquisitions or R&D | Palo Alto, Google, CrowdStrike, Zscaler |
| 4 | Contracts with the Israeli government or military | Google & AWS (Nimbus), Microsoft (IMOD) |
| — | No material nexus identified | e.g. Fortinet, Trend Micro (per source assessment, 21 Oct 2026) |

Hard cases (tier 3–4): **Microsoft, Google and AWS** are government cloud providers — expect long,
guarantee-based management rather than migration. Full vendor matrix with evidence grading is in
**Appendix B** of the source article.

## Watch & reassess (quarterly)

- [ ] Circular text published, or a second circular naming other products → wider review may be under way.
- [ ] NACSA / Act 854 guidance on data jurisdiction or vendor origin → data-flow rule taking shape.
- [ ] Procurement circular on suppliers' data location → wider review.
- [ ] Technical statement on Waze data flows → security-led motive becomes more plausible.
- [ ] Google Maps or other apps also restricted → broader jurisdiction test.
- [ ] Vendors publish Malaysia data-residency commitments → market adapting; re-check guarantees.
- [ ] Nothing beyond Waze in 6–12 months → treat as policy signal only; keep the inventory current anyway.

## Still unknown (as of 21 Oct 2026)

- The circular's exact text and device scope (official vs personal) — **not published**.
- How Iraq-style blocking would be enforced, if ever extended here.
- Actual government deployments of the vendors listed above (market presence ≠ confirmed government use).
- Whether follow-on guidance beyond Waze will appear (the source rates this a roughly even chance, low confidence).

---

*Source of the checklist steps and tables: Rectifyq RQ-2026-0159 (TLP:GREEN, 21 Oct 2026), linked above.
This file is an operational aid, not a reproduction of the assessment. Corrections to the source are
welcomed by Rectifyq via Tanya Rectifyq.*
