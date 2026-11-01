# Data Integrity Rules

> **Superseded and extended by `rules/data-availability-and-integrity.md`.**
> Read that file first for the complete Global Data Availability and Integrity Policy.
> This file retains only the operational detail not covered there.

---

## Applies to every task

Complements `references/context-retrieval-protocol.md` with how to classify and trust what you find. The classification in `rules/data-availability-and-integrity.md` governs in any conflict.

## Five information classes (quick reference)

| Class | Meaning | How to present |
|---|---|---|
| FACT | Supported by an accessible document, data file, or verified source | State plainly |
| CALCULATION | Derived transparently from supplied facts | State formula and inputs |
| ASSUMPTION | Inference used to proceed | Label; name what changes if wrong |
| HYPOTHESIS | A proposition requiring testing | Label; name how to test it |
| DATA UNAVAILABLE | Needed but not present in accessible sources | State the gap and its effect |

A user's belief about their own business is a supplied fact about what they believe, not a verified fact about the market.

## Detect before analysing

When the supplied information can be inspected, check for missing values, inconsistencies across documents, outdated figures (note document dates), duplicated records, mixed currencies, mixed periods, and unclear metric definitions. Do not claim automated validation unless it actually occurred.

For customer-count metrics, confirm the population definition, measurement dates, and period before calculating rates. **Net additions** for a period equal new customers minus churned customers (plus separately identified reactivations or other adjustments, if applicable), using consistent definitions and the same period. This is a count, not a growth rate. **Growth rate** equals `(ending active customers - beginning active customers) / beginning active customers`; do not calculate it without a valid beginning-period count and a comparable ending count. If the beginning count is zero, the percentage rate is undefined. Do not substitute a current or ending count as the denominator.

Do not derive an actual beginning-period count from an ending count unless the new-customer, churn, reactivation, reinstatement, migration, and other adjustment flows form a complete, same-period bridge for the same population. If showing a conditional bridge, label it CALCULATION with every assumption; it is not a verified beginning count until those inputs are confirmed.

For **customer/logo churn rate**, define the churn event and population first. The numerator is customers from the eligible beginning-of-period active base who churn during the stated period; the denominator is that same eligible active base at the beginning of the period. State whether the metric is logo/customer churn or revenue churn, the period, and any exclusions. Do not use a current or ending active-customer count as the denominator unless the stated metric definition specifically requires it. A churn rate reported in Business Context is a reported claim, not an independently verified calculation. If numerator, denominator definition, period, or comparable base cannot be established, mark the independently verified churn rate `DATA UNAVAILABLE` and identify the missing inputs.

An unverified reported churn rate may be mentioned only as **reported** information. Do not use it as a verified baseline, derive lifetime/LTV from it, or use it to create churn targets, guardrails, or budget decisions. Keep the reported value distinct from the independently verified rate, which remains `DATA UNAVAILABLE` until validated.

Acquisition first replaces customers lost to churn only up to the churn count, when both counts use the same population and period. If new customers exceed churned customers, the remainder is positive net additions. Do not describe acquisition as merely replacing churn when comparable counts show positive net additions; do not infer a percentage growth rate from net additions alone.

For funnel conversion, stage counts must refer to the same observation period and the same starting cohort/population, with consistent event definitions and deduplicated units (for example, users versus sessions). Aggregate stage snapshots without linked users/events or a documented common cohort do not establish user-level progression. If linkage, cohort, period, event, or unit comparability is unconfirmed, label counts as unaligned snapshots; do not report a valid conversion rate, claim drop-offs, or project incremental customers. An exploratory arithmetic ratio may be shown only when useful, labeled provisional and explicitly not a conversion rate, with comparability assumptions and validation needs stated.

## Conflicts

Handled by `rules/data-availability-and-integrity.md` section 9. Short version: never silently pick one value; label DATA CONFLICTING, state both sources, explain the strategic consequence.

## Asking questions

The Business Context document is mandatory for business-specific work. Once available, ask at most one essential task-specific question when a critical missing detail prevents reasonable analysis. Never start a general intake interview or ask for something already in context.

## Never fabricate

See `rules/data-availability-and-integrity.md` section 1 for the complete prohibition list. No invented statistics, benchmarks, competitor facts, customer quotes, testimonials, financial figures, or document contents. If a referenced file cannot be opened, say so.

## Privacy and safety

Never request passwords, API keys, or payment credentials. Encourage hashed or pseudonymous customer identifiers in uploaded files and removal of unnecessary personal data. Do not repeat personal customer data back in outputs.

## Source preservation

Never modify the user's source files. If a separate cleaned or transformed copy is explicitly requested and available tools can produce it, preserve the original.
