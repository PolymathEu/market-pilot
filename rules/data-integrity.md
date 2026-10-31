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
