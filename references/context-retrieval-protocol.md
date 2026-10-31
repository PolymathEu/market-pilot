# Context Retrieval Protocol

## Mandatory Business Context gate

For every business-specific diagnosis, analysis, recommendation, strategy, or plan, first confirm that an accessible, non-empty Business Context document is available. It is the primary source for business facts. Project instructions define standing preferences and constraints; supporting documents provide task-specific evidence. Conversation details are supplemental and never replace the required document.

If the Business Context document is missing, inaccessible, or empty, stop and return exactly the response in `SKILL.md` under Business Context First. Do not start an interview, ask intake questions, infer the business, or provide a hypothetical diagnosis.

General educational questions do not require Business Context. Answer them directly.

When Business Context is available, read it first and use it without asking the user to repeat documented information. Ask at most one essential, task-specific clarification question only if a critical missing detail prevents reasonable analysis. If a supporting document is missing, name that exact document and limit only the conclusions that depend on it.

## Check accessibility

Check only information actually accessible in the current session. Relevant supporting documents may include customer research, analytics, competitor notes, financial or sales reports, brand guidelines, and prior marketing assets. If a referenced document cannot be opened, say so plainly. Do not infer its contents from the filename.

## Classify evidence

Classify every material finding as one of the following. Label assumptions and hypotheses in the output when they affect a conclusion.

- **FACT**: Directly supported by an accessible document, data file, or verified source. A user's statement is a fact about what the user said, not independent verification of the claim.
- **CALCULATION**: Mathematically derived from supplied facts. State the formula, inputs, units, and currency when material.
- **ASSUMPTION**: An inference used to proceed. Label it and state what changes if it is wrong.
- **HYPOTHESIS**: A proposition requiring validation. Label it and name a suitable test.
- **DATA UNAVAILABLE**: Information required for a conclusion but absent from accessible sources.

Never silently convert a claim, assumption, or hypothesis into a fact.

## Handle conflicts

When sources disagree, identify the conflicting values and sources. Explain which value is used and why, such as recency or explicit user confirmation. If the conflict could change the recommendation, state that and ask at most one essential clarification question.

## Assess task sufficiency

- **Sufficient**: Business Context is available and includes enough task-relevant information. Proceed without unnecessary questions.
- **Partially sufficient**: Business Context is available but a supporting detail is missing. Proceed only with supported conclusions, label material assumptions or hypotheses, and state what cannot be determined.
- **Insufficient for this task**: A critical task-specific fact is missing and analysis cannot reasonably proceed. State the limitation and ask at most one essential clarification question.

For narrow business-specific requests, still require Business Context but use only the relevant portions. General educational questions are exempt from the gate.