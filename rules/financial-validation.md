# Financial Validation Rules

Mandatory whenever a number about money, margin, cost, ROAS, CPA, CAC or lifetime value is calculated or interpreted. Use only supplied inputs and transparent arithmetic; never imply automated validation unless an available tool actually performed it.

## 1. Metric dictionary (never interchangeable)

| Metric | Definition | Denominator or basis that must be stated |
|---|---|---|
| Revenue (gross) | Value charged to customers before discounts, refunds, returns | Orders counted: placed or fulfilled |
| Net revenue | Gross minus discounts, refunds, returns, and revenue of cancelled orders | Per order, per period or total |
| Gross profit | Net revenue minus COGS | Same unit as net revenue |
| Gross margin | Gross profit divided by net revenue | Net revenue |
| Contribution before marketing | Net revenue minus COGS and all other relevant variable costs, excluding advertising and other marketing costs | Per order or period; state the basis |
| Contribution margin before marketing | Contribution before marketing divided by net revenue | Use the same order set and revenue basis in numerator and denominator |
| Contribution after advertising | Contribution before marketing minus advertising cost allocated to the same order set or period | State attribution, allocation, and time scope |
| Contribution after marketing | Contribution before marketing minus all marketing costs in a stated scope, including advertising where applicable | State which marketing costs are included; do not use as a synonym for contribution after advertising |
| Paid media spend per total order | Paid spend divided by ALL business orders | PROXY only. Includes organic, direct, repeat orders. Never call it CPA |
| CPA | Cost in a stated scope divided by a defined conversion event count | Define event, denominator, platform, attribution window, and measurement period |
| CAC | Acquisition cost in a stated scope divided by newly acquired customers in a defined cohort or period | Define cost scope, new-customer rule, cohort, and period |
| LTV | Observed contribution per customer over a stated observation window | Window length, customer maturity. Not a forecast |
| Break-even CPA | Contribution before advertising per qualifying acquired order | First-order basis unless stated; comparable to observed CPA only when conversion event, denominator, cost scope, attribution window, and period align |
| Break-even ROAS | Platform-reported revenue divided by contribution available for advertising, for the same qualifying order set | Include all non-ad variable costs first; match platform revenue definition, attribution scope, and period |
| Platform-reported ROAS | Platform attributed revenue divided by platform spend | Attributed, not incremental |
| Blended ROAS | Deduplicated business revenue divided by total marketing spend | Revenue basis (gross or net) |

## 2. Hard rules

1. Never calculate paid-channel CPA with total business orders. If only total orders exist, report "paid media spend per total order" and label it PROXY.
2. Never state a true CAC without its cost scope and new-customer definition. CPA and CAC are not inherently mathematically incomparable: assess whether their conversion event, denominator, attribution window, cost scope, and measurement period align before comparing them.
3. Keep gross profit/margin, contribution before marketing, contribution after advertising, and contribution after total marketing distinct. Calculate contribution before marketing only when all relevant non-marketing variable costs are supplied or explicitly marked not applicable. A missing cost is not zero.
4. Keep refunds, cancellations, returns, discounts, payment fees, marketplace fees, shipping subsidy and fulfillment separate. Never merge them into one "costs" or "leakage" figure.
5. A percentage is meaningless without its denominator. A "5 percent refund rate" can mean 5 percent of orders, of gross value, or of discounted value. Ask or label the assumption. Do not apply it until the denominator is known.
6. Cancellations (order never fulfilled, usually no COGS) and refunds (money returned after fulfillment, COGS usually spent) have different economics. Do not treat them as the same cost.
7. Never invent a missing financial input, including COGS, fees, margins, conversion rates, or exchange rates.
8. One currency per calculation. Convert only with a supplied rate and date; never use a remembered exchange rate.
9. Break-even figures are first order unless the user supplies repeat purchase data that supports an LTV based figure, labelled as such.
10. A positive ROAS or a low CPA is not profit. Compare to break-even derived from the business's own unit economics.
10. A positive ROAS or a low CPA is not profit. Compare to break-even derived from the business's own unit economics, using matching revenue, conversion, attribution, and period definitions.

## 3. Required inputs for a full unit economics calculation

Gross order value, COGS per fulfilled order, discounts, refunds, returns, cancellation rate and cost per cancelled order, payment and marketplace fees, shipping subsidy, fulfillment, packaging, other variable costs, advertising cost, and currency. State whether each value is per order, per customer, or aggregate, and its period. Keep advertising cost separate from other variable costs. Identify every missing input; a missing cost is not zero.

## 4. When inputs are missing

Report what is computable, name the missing inputs, and ask only for the ones that change the decision. Example: net revenue is known but contribution is unavailable because shipping subsidy and fulfillment cost are missing.

## 5. Transparent calculation formulas

Use a per-placed-order basis unless another basis is explicitly stated. Define the inputs before calculating:

- `c` = cancelled-order rate among placed orders; `f = 1 - c` = fulfilled-order rate.
- `G` = gross order value per fulfilled order before discounts and revenue reversals.
- `D` = discounts per fulfilled order; `R` = refunds; `T` = return-related revenue reversals not already included in refunds.
- `C` = COGS per fulfilled order.
- `V` = sum of other non-marketing variable costs per fulfilled order, such as payment fees, marketplace fees, fulfillment, packaging, and shipping subsidy. Exclude COGS and all advertising/marketing costs.
- `K` = cost incurred per cancelled order.
- `A` = advertising cost allocated to the same order set; `M` = all marketing costs included in the stated scope.
- `P` = platform-reported revenue per qualifying attributed order, using the platform's stated revenue definition.

Assume all inputs use the same currency and compatible period/order basis. Cancellation costs apply only to cancelled orders; `C` and `V` apply only to fulfilled orders. Do not double-count returns already recorded as refunds.

1. `Net revenue per placed order = f x (G - D - R - T)`.
2. `Gross profit per placed order = net revenue - f x C`.
3. `Gross margin = gross profit / net revenue`, when net revenue is non-zero.
4. `Contribution before marketing = gross profit - f x V - c x K`.
5. `Contribution margin before marketing = contribution before marketing / net revenue`, when net revenue is non-zero.
6. `Contribution after advertising = contribution before marketing - A`, where `A` is allocated to that same order set or period.
7. `Contribution after marketing = contribution before marketing - M`, where `M` includes the explicitly stated marketing cost scope. Do not subtract advertising twice.
8. First-order break-even acquisition cost is the contribution before advertising for the same qualifying acquired order. Compare it with CPA or CAC only when their event/customer denominator, cost scope, attribution window, and period align.
9. `Break-even ROAS = P / contribution before advertising per matching attributed order`, or the equivalent aggregate ratio for the same matched order set. Include all relevant variable costs before advertising. The simplified `1 / contribution-margin ratio` is valid only when that ratio uses the same revenue basis as platform-reported ROAS and all relevant variable costs are included. Never substitute gross margin automatically.

Show the arithmetic, define variables, and state assumptions. Keep the mathematical result separate from external benchmarks and strategic recommendations. Describe a value as calculated only when inputs and arithmetic are available; do not claim a tool or script ran unless it did.
