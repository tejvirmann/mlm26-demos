# MLM Website — Master Plan

> Status: Draft v0.1 · Owner: Tejvir Mann · Last updated: 2026-09-16

This is the top-level plan for a network-marketing (MLM) company's public
website and distributor back-office. It ties together the supporting
documents in this folder and gives a reader the "why" before they drop into
detail.

## 1. What we're building

A two-sided web platform:

1. **Public marketing site** — company story, product catalog, opportunity
   pitch, compliant income disclosure, distributor lookup, lead capture.
2. **Distributor back-office (portal)** — signup/enrollment, replicated
   personal storefronts, genealogy/downline view, commission statements,
   rank progress, training library, compliant marketing asset library.

## 2. Supporting documents

| File | Purpose |
|---|---|
| `business-model.md` | Revenue model, target market, product category, positioning |
| `compensation-plan.md` | How distributors earn — ranks, bonuses, payout rules |
| `compliance-legal.md` | Pyramid-scheme risk controls, disclosures, regulatory posture |
| `site-map.md` | Page-by-page structure for both public site and portal |
| `tech-stack.md` | Architecture, stack choices, third-party integrations |
| `marketing-strategy.md` | Launch plan, content, channels, compliant claims |
| `timeline.md` | Phased delivery plan with milestones |
| `budget.md` | Cost estimate by phase and category |
| `risks.md` | Key risks and mitigations, ranked by severity |

## 3. Goals (v1 launch)

- Legally compliant income and product claims reviewed against FTC's
  Business Opportunity Rule and the FTC's 2024 MLM guidance before anything
  goes live.
- A compensation plan that pays out primarily on **verified retail sales to
  non-participants**, not recruitment — this is the single most important
  design constraint for the whole project (see `compliance-legal.md`).
- A distributor portal that a non-technical rank-and-file distributor can
  use without support tickets for the top 5 daily tasks (share storefront
  link, check commissions, see downline, reorder product, pull a compliant
  social post).

## 4. Non-goals (v1)

- No cryptocurrency or "investment" framing anywhere in the product — this
  is a product-sales business, not an investment vehicle.
- No autoship dark patterns (hidden pre-checked boxes, buried cancellation
  flow). Autoship must be as easy to cancel as to start.
- No income claims on the public site beyond the linked, dated Income
  Disclosure Statement.

## 5. Success metrics

- Distributor activation rate (completes first sale within 30 days)
- Retail-to-recruitment revenue ratio (target: retail sales > 50% of
  total revenue — a common regulatory health signal)
- Support ticket volume per active distributor
- 90-day distributor retention rate

## 6. How to read the rest of this folder

Start with `business-model.md` for context, then `compliance-legal.md`
before looking at `compensation-plan.md` — the comp plan is designed
*around* the compliance constraints, not the other way around.
