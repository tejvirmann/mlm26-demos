# Site Map

## A. Public marketing site

```
/                       Home — brand story, hero product, CTA (Shop / Join)
/shop
  /shop/[category]
  /shop/[product-slug]  Product detail, ingredients, reviews
/opportunity            The pitch — framed as side income from product use
  /opportunity/income-disclosure   Required IDS, linked prominently
  /opportunity/compensation-plan   Plain-language comp plan summary
/find-a-distributor     Directory / locator, search by name or zip
/[distributor-slug]     Replicated personal storefront (templated, brand-safe)
/about
/blog                   Compliant content marketing, no income claims
/legal
  /legal/policies-and-procedures
  /legal/terms
  /legal/privacy
  /legal/refund-buyback-policy
/support
```

## B. Distributor portal (auth required)

```
/portal/dashboard        Rank, this-period volume, quick actions
/portal/storefront        Manage replicated site content (brand-locked)
/portal/customers         Personal customer list + order history
/portal/downline          Genealogy tree, activity status, compression view
/portal/commissions
  /portal/commissions/statements    Period-by-period, exportable
  /portal/commissions/payout-settings
/portal/orders
  /portal/orders/place-order
  /portal/orders/autoship        One-click cancel, no dark patterns
/portal/training          Product + compliant-marketing training library
/portal/marketing-assets  Pre-approved, on-brand shareable assets only
/portal/rank-progress     Requirements + current standing, re-verified quarterly
/portal/account
  /portal/account/profile
  /portal/account/tax-documents   1099s etc.
```

## C. Admin / back-office (internal, not public)

```
/admin/distributors       Search, status, compliance flags
/admin/compliance         Flagged social posts, income-claim review queue
/admin/commissions-engine Run/approve payout cycles
/admin/reporting          Retail-vs-recruitment ratio, cohort retention, etc.
/admin/content            IDS updates, comp plan doc versioning
```

## Navigation notes

- Public nav never leads with "opportunity" — product/shop is first,
  consistent with `business-model.md` positioning ("buy it because you'd
  buy it anyway").
- Every page under `/opportunity` links the Income Disclosure Statement
  in the same visual weight as any earnings example, per
  `compliance-legal.md`.
