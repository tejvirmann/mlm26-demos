# Risks & Mitigations

Ranked roughly by severity × likelihood.

## 1. Regulatory: pyramid-scheme characterization (High severity)
**Risk**: comp plan or marketing drifts toward recruitment-driven pay,
triggering FTC/state action.
**Mitigation**: structural rules in `compensation-plan.md` (70% retail
rule, no pay-to-recruit), ongoing audits per `compliance-legal.md`,
counsel review before every comp-plan change.

## 2. Distributor income-claim liability (High)
**Risk**: distributors post unapproved income claims on social media,
creating FTC exposure for the company.
**Mitigation**: approved marketing-asset library only, spot-check
process, clear policies & procedures with enforcement teeth (see
`marketing-strategy.md`, `compliance-legal.md`).

## 3. Commission engine errors (High — financial + trust)
**Risk**: miscalculated payouts erode distributor trust or create
clawback disputes.
**Mitigation**: auditable/reversible engine design (`tech-stack.md`),
staging tests against synthetic data before every release.

## 4. Inventory loading by distributors (Medium)
**Risk**: distributors over-purchase to hit rank thresholds, then
struggle to resell — a classic pyramid-scheme signal and a churn driver.
**Mitigation**: buyback guarantee, retail-verification requirement for
rank bonuses (`compensation-plan.md`, `business-model.md`).

## 5. Data privacy / payout KYC (Medium)
**Risk**: mishandling distributor PII or payment data, or failing
KYC/AML obligations on international payouts.
**Mitigation**: use established payout processor (Tipalti/Hyperwallet)
rather than building KYC in-house; standard data-privacy review pre-launch.

## 6. Slow founding-cohort feedback loop delays public launch (Low-Medium)
**Risk**: Phase 2 founding cohort surfaces comp-plan or product issues
late, pushing the Phase 4 public launch date.
**Mitigation**: timeline already treats this as a gate, not a fixed date
(`timeline.md` Phase 2 milestone is a real go/no-go, not a formality).
