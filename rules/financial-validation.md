# Financial Validation Rules

Mandatory whenever a number about money, margin, cost, ROAS, CPA, CAC or lifetime value is calculated or interpreted. Use only supplied inputs and transparent arithmetic; never imply automated validation unless an available tool actually performed it.

## 1. Metric dictionary (never interchangeable)

| Metric | Definition | Denominator or basis that must be stated |
|---|---|---|
| Revenue (gross) | Value charged to customers before discounts, refunds, returns | Orders counted: placed or fulfilled |
| Net revenue | Gross minus discounts, refunds, returns, and revenue of cancelled orders | Per order, per period or total |
| Gross profit | Net revenue minus COGS | Same unit as net revenue |
| Gross margin | Gross profit divided by net revenue | Net revenue |
| Contribution before marketing (amount) | Net revenue minus COGS and all other relevant variable costs, excluding marketing costs | Per order or period; state the basis |
| Contribution margin before marketing (ratio) | Contribution before marketing divided by net revenue | Use the same order set and revenue basis in numerator and denominator |
| Contribution after advertising (amount) | Contribution before marketing minus the specified advertising cost, before other marketing costs | State allocation, attribution, and time scope |
| Contribution margin after advertising (ratio) | Contribution after advertising divided by the same net revenue basis | State that other marketing costs are excluded, if they are |
| Contribution after marketing (amount) | Contribution before marketing minus all marketing costs in a stated scope | State which marketing costs are included; do not use as a synonym for contribution after advertising |
| Contribution margin after marketing (ratio) | Contribution after marketing divided by the same net revenue basis | State the included marketing cost scope |
| Paid media spend per total order | Paid spend divided by ALL business orders | PROXY only. Includes organic, direct, repeat orders. Never call it CPA |
| CPA | Cost in a stated scope divided by a defined conversion event count | Define event, denominator, platform, attribution window, and measurement period |
| CAC | Acquisition cost in a stated scope divided by newly acquired customers in a defined cohort or period | Define cost scope, new-customer rule, cohort, and period |
| LTV | Contribution actually observed for a defined customer cohort over a stated observation window | State cohort, window length, customer maturity, and included contribution basis. Not a forecast |
| Break-even CPA | Contribution available to cover the tested acquisition cost per qualifying new customer or order | State other marketing costs included; comparable to observed CPA only when conversion event, denominator, cost scope, attribution window, and period align |
| Break-even ROAS | Platform-reported revenue divided by contribution available to cover the tested ad spend, for the same qualifying order set | Include all relevant variable costs and any other marketing costs in scope; match platform revenue definition, attribution scope, and period |
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
10. A positive ROAS or a low CPA is not profit. Compare to break-even derived from the business's own unit economics, using matching revenue, conversion, attribution, and period definitions.
11. Do not estimate fully loaded CAC by applying an assumed multiplier to marketing-only CPA/CAC. State which cost categories are missing and mark fully loaded CAC unavailable unless those costs and the new-customer denominator are supplied. No additional paid-media spend on a cross-sell does not imply zero CAC: distinguish marginal paid-media cost from acquisition cost including allocated campaign, content, email, sales, support, discounts, and other relevant costs. Claim zero marginal spend only when no incremental paid-media outlay is established; do not relabel it zero CAC.
12. Do not present `1 / churn rate` as observed customer lifetime, retention, or LTV. It is at most a theoretical constant-churn model estimate when the churn definition, opening-base denominator, period, and stable constant-hazard assumption are all supported and stated. Keep modeled LTV separate from observed cohort contribution LTV, and never describe the model as validated cohort retention.
13. A formula such as `average order value x purchase frequency x customer lifetime` produces a modeled revenue-LTV only when its inputs, cohort, window, and assumptions are defined. Do not present it as observed LTV or contribution LTV. Prefer observed cohort contribution LTV when suitable data exists; otherwise label the model and its inputs ASSUMPTION or CALCULATION as appropriate, and disclose that contribution costs or cohort evidence may be missing.

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
- `A` = tested advertising cost allocated to the same order set; `M` = total marketing costs in scope, including `A`; `O = M - A` = other marketing costs in scope, excluding the tested advertising cost.
- `P` = platform-reported revenue per qualifying attributed order, using the platform's stated revenue definition.

Assume all inputs use the same currency and compatible period/order basis. Cancellation costs apply only to cancelled orders; `C` and `V` apply only to fulfilled orders. Do not double-count returns already recorded as refunds.

1. `Net revenue per placed order = f x (G - D - R - T)`.
2. `Gross profit per placed order = net revenue - f x C`.
3. `Gross margin = gross profit / net revenue`, when net revenue is non-zero.
4. `Contribution before marketing = gross profit - f x V - c x K`.
5. `Contribution margin before marketing = contribution before marketing / net revenue`, when net revenue is non-zero.
6. `Contribution after advertising = contribution before marketing - A`; this excludes other marketing costs `O`.
7. `Contribution after marketing = contribution before marketing - M`, where `M` includes the explicitly stated marketing cost scope.
8. `Contribution margin after advertising = contribution after advertising / net revenue`; `contribution margin after marketing = contribution after marketing / net revenue`, using matching scopes and denominators.
9. `Contribution available for tested advertising = contribution before marketing - O`. First-order break-even CPA is this amount per matching acquired customer/order. Compare it with observed CPA or CAC only when their event/customer denominator, cost scope, attribution window, and period align.
10. `Break-even ROAS = P / contribution available for tested advertising per matching attributed order`, or the equivalent aggregate ratio for the same matched order set. Include all relevant variable costs and other marketing costs `O`. The simplified `1 / contribution-margin ratio` is valid only when that ratio is calculated after those costs and uses the same revenue basis, order set, and attribution period as platform-reported ROAS. Never substitute gross margin automatically.

Show the arithmetic, define variables, and state assumptions. Keep the mathematical result separate from external benchmarks and strategic recommendations. Describe a value as calculated only when inputs and arithmetic are available; do not claim a tool or script ran unless it did.

## 6. General financial education

Answer educational questions without requiring Business Context. Keep explanations concise and use hypothetical numbers only when labeled illustrative; do not invent a company, business stage, or personalized recommendation.

If explaining `ARPU / churn rate`, call the result a **modeled revenue-LTV**, not observed lifetime, cohort retention, or contribution LTV. State that the churn rate must be a defined, period-matched logo churn rate and that the model assumes a stable, constant churn hazard. It excludes costs unless contribution margin is explicitly applied with supported inputs. Do not describe the resulting LTV:CAC ratio as healthy, unhealthy, or proof to increase spend without relevant evidence and context.

For educational iROAS examples, estimate incremental revenue from comparable treatment/control groups over the same period and per the same eligible unit. With randomized groups, `incremental revenue estimate = (treatment revenue per eligible unit - control revenue per eligible unit) x eligible treatment units`; `iROAS = incremental revenue estimate / treatment ad spend`. State randomization/comparability assumptions. Unequal or non-random groups need an appropriate design/adjustment; raw total-revenue subtraction alone does not establish causal lift.
