# Checklist — Israel-Nexus Technology Response (Malaysia)

A working checklist for Malaysian organisations responding to the **20 October 2026** government
directive that barred civil servants from using **Waze**, and more broadly assessing technology with
an Israeli nexus in their stack — without a costly rip-and-replace.

> **TLP:GREEN — Malaysian community only.** Distilled from Rectifyq **RQ-2026-0159**,
> *[Beyond Waze: Israel-Nexus Technology in Malaysia's Public Sector](https://rectifyq.com/my-only/2026-10-waze-ban-israel-nexus-technology)*
> ([Bahasa Malaysia](https://rectifyq.com/my-only/2026-10-larangan-waze-teknologi-berkait-israel)), 21 Oct 2026.
> The source article is geo-restricted (Malaysia-only): **share the link, don't repost the article** —
> and keep this derived checklist within the community too (consider keeping this repo private).

## Context (as of 21 Oct 2026)

- **20 Oct 2026** — National Cyber Security Committee (**JKSN**) Meeting 3/2026, chaired by PM Anwar Ibrahim.
  The Chief Secretary to the Government circular barred **all civil servants from Waze**, effective immediately;
  secretaries-general and department heads to cascade. Coordinated by NACSA (MKN, JPM).
- **Rationale:** Waze is *"subject to Israeli government laws"*, putting users' data and movements at risk.
  *"The government cannot compromise on the security of Malaysians' data and identities."*
- **Public advice:** switch to **TuJu**, the local navigation app (Lembaga Lebuhraya Malaysia with Prosignal Consortium).
- **The test the government applied:** is Malaysian data **within reach of Israeli law**? Applied consistently,
  higher-access security tools (firewalls, PAM, SASE, EDR, OT sensors) meet that test long before a navigation app.
- **Approach recommended here:** **Aware → Policy → Verify → Migrate at renewal**. Don't rip anything out mid-contract.

## Files

| File | What it is |
| --- | --- |
| [`CHECKLIST.md`](CHECKLIST.md) | The checklist — 4 phases (Aware / Policy / Verify / Migrate), the access-ranking and nexus-tier tables, a quarterly watch list, and known unknowns |
| [`vendor-inventory-template.csv`](vendor-inventory-template.csv) | Inventory template for Phase 1 — one row per security/SaaS product, ranked by access |

**How to use:** start at the top of `CHECKLIST.md`. As you complete Phase 1 item 1, fill
`vendor-inventory-template.csv`; every later phase refers back to those rows (guarantee → verify →
keep & monitor, or migrate at renewal).

## Caveats

- An Israeli link is **not** evidence that a product is malicious or backdoored — this maps
  **structural exposure** (data jurisdiction and access), not wrongdoing.
- Judge **where data goes** (checkable), not who founded the vendor (not actionable).
- "No mention" in a privacy notice does not mean no data goes to Israel — check sub-processor lists
  and support locations.
- "Local" ≠ "reviewed" — put TuJu and other local alternatives through the same security review.
- The Waze circular's exact text and device scope (official vs personal) were **not published** as of 21 Oct 2026.

## Provenance

- Source assessment: Rectifyq RQ-2026-0159 (TLP:GREEN, confidence: Moderate) — link above. Full vendor
  matrix with evidence grading, competing-hypotheses analysis and references live in the source article's appendices.
- Background news: [FMT, 20 Oct 2026](https://www.freemalaysiatoday.com/category/nation/2026/10/20/anwar-advises-against-using-waze-over-israel-linked-security-concerns) ·
  [FMT, 21 Oct 2026](https://www.freemalaysiatoday.com/category/nation/2026/10/21/civil-servants-banned-from-using-waze) ·
  [The Edge Malaysia, 21 Oct 2026](https://theedgemalaysia.com/node/822663) ·
  [SoyaCincau, 21 Oct 2026](https://soyacincau.com/2026/10/21/malaysian-goverment-bans-waze-civil-servants/)
