# Module 9: Execution and Budget Strategy

## What to develop

- Three to five prioritized initiatives when evidence supports that many. If the primary constraint is not established, prioritize the smallest useful validation action or actions instead of filling the list with speculative interventions.
- Execution roadmap with realistic sequencing
- Resource requirements matched to what the business actually has (from Module 1's constraints)
- Budget scenarios, only where there's real budget context to scale from
- Milestones and dependencies
- KPIs per initiative
- Experiment design: hypothesis, what's being tested, how it's measured, what decision each outcome leads to

## Prioritization method

Use a lightweight version of ICE or RICE (Impact, Confidence, Effort, and Reach where relevant) to rank candidate initiatives, but don't show the scoring mechanics to the user by default, just the resulting order and a one-line reason. If the user wants to see the scoring itself, show it.

Weigh:

- **Impact**: how much this could move the actual bottleneck identified in Module 1, not a generic "would be nice" metric
- **Confidence**: how much evidence supports this working, versus how speculative it is
- **Effort**: team time, budget, and complexity, matched against the real constraints in context
- **Time to learn**: how fast you'd know if it's working; favor initiatives with faster feedback loops when impact and confidence are roughly similar, since speed to learn compounds

Strategic relevance and risk matter too: an initiative that's high-impact but carries brand or legal risk, or that only makes sense if an unproven assumption holds, should be flagged as such rather than ranked purely on the ICE/RICE score.

## 80/20 discipline

The system exists to cut the list down, not pad it. If ten reasonable initiatives surface, pick the three to five with the best impact-to-effort ratio and say explicitly what's being deprioritized and why. Don't present a backlog disguised as a strategy.

## Experiment design requirements

Every proposed experiment must specify:

1. **Problem and evidence**: the observed issue and evidence supporting a test; absence from context is not proof an activity does not exist.
2. **Hypothesis**: a falsifiable statement about a defined audience or cohort and expected direction of change.
3. **Intervention**: what changes, what remains unchanged, and the control or comparison method where feasible.
4. **Primary metric**: event, numerator, denominator, unit, cohort, period, and why it measures the hypothesis.
5. **Guardrail metric**: metric definition and why it protects against a harmful trade-off.
6. **Baseline and target**: use a comparable observed baseline when available. A proposed numeric target must come from user requirements, supported business economics, a cited relevant benchmark, or an explicit decision criterion; labeling an arbitrary number ASSUMPTION or HYPOTHESIS is not sufficient. If no defensible basis exists, set no numeric threshold and run a baseline-measurement phase.
7. **Evaluation period and decision criteria**: state the observation window and evidence needed to decide. If a minimum sample or statistical threshold is used, derive it from a stated design and available inputs; do not invent a generic minimum. If the sample is too small, describe findings as directional/descriptive and do not claim statistical significance or causal impact.
8. **Interpretation limits**: sample-size limitations, confounders, seasonality, attribution limits, selection effects, data quality, and what the test cannot establish.
9. **Stop, continue, and change conditions**: specify the conditions for each outcome and the evidence that would change the recommendation. Do not extrapolate a small or short test into a forecast.

If the test cannot meet these requirements, present it as an exploratory measurement or validation action, not as a causal experiment or a forecast.

## Never fabricate forecasts

Don't produce precise revenue or growth forecasts without real baseline data to project from. It's fine to say "this initiative targets [specific bottleneck] and a reasonable early signal of success would be [specific, measurable, near-term indicator]." It's not fine to assert "this will increase revenue by 23%."

## Output for this module

Feeds "Recommended Strategy," "Action Plan," and "Success Metrics" directly in the comprehensive brief.
