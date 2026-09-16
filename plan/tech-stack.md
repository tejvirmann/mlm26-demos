# Technical Architecture

## Stack (proposed)

| Layer | Choice | Why |
|---|---|---|
| Frontend | Next.js (React) | SSR for public/SEO pages, same framework for portal |
| Styling | Tailwind CSS | Fast, consistent design system across replicated storefronts |
| Backend API | Node.js (NestJS) or Django | Whichever the team knows best; needs strong auth + job scheduling |
| Database | PostgreSQL | Relational integrity for genealogy tree, commissions, orders |
| Genealogy/tree queries | Materialized path or closure table in Postgres | Efficient downline/upline queries at scale without a graph DB |
| Commission engine | Scheduled batch job (queue-based) | Commission runs are period-based, auditable, must be idempotent and reversible |
| Payments (customers) | Stripe / Adyen | PCI compliance offloaded to processor |
| Payouts (distributors) | Tipalti, Hyperwallet, or Stripe Connect | Handles 1099s, international payout compliance, KYC |
| Auth | Auth0 / Clerk, or homegrown with strong MFA for admin | Distributor portal handles financial data — treat like a fintech app |
| Hosting | Vercel (frontend) + managed Postgres (RDS/Supabase) | Standard, low-ops |
| Replicated storefronts | Single Next.js app, dynamic route by distributor slug, content pulled from CMS + brand-locked template | Avoids "one site per distributor" sprawl |

## Key architectural constraints from the business rules

1. **Commission engine must be auditable and reversible.** Every payout
   run needs a full trace back to the qualifying orders — regulators and
   distributor disputes both require this. Treat it like financial
   ledger software, not a simple cron job.
2. **Retail-vs-recruitment tracking is a first-class data model**, not an
   afterthought — every order needs a `customer_type` (retail /
   distributor-personal-use / distributor-resale) because the entire
   compliance posture in `compliance-legal.md` depends on being able to
   report this ratio at any time.
3. **Replicated storefronts must be brand-locked.** Distributors should
   not be able to freely edit HTML/claims — use a constrained CMS
   (approved copy blocks, approved images) to prevent unauthorized income
   or health claims, which is a top MLM legal risk.
4. **Genealogy tree at scale**: assume up to 6–7 levels deep and
   potentially tens of thousands of distributors — use a closure table or
   nested-set model in Postgres rather than N+1 recursive queries.

## Third-party integrations

- Tax: Avalara or TaxJar for multi-state retail sales tax
- Email/SMS: for distributor lifecycle + customer marketing (with
  opt-in/opt-out compliance, CAN-SPAM/TCPA)
- Analytics: standard web analytics + a compliance dashboard (see
  `compliance-legal.md` reporting requirements)

## Environments

- `dev` → `staging` → `production`, with the commission engine tested
  against a full synthetic dataset in staging before every release — a
  commission bug is a legal and financial incident, not just a bug.
