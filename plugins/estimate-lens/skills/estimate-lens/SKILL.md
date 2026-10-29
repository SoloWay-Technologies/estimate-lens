---
name: estimate-lens
description: Use when a client or client partner needs to review one or compare multiple project estimates against requirements, including scope, effort, price, and clarification questions.
---

# EstimateLens by SoloWay

Help clients and client partners understand estimate coverage and make an informed choice. Analyze supplied evidence; do not invent independent hours, rates, prices, exchange rates, requirements, or a vendor's intentions. A score is a comparison under the rules below, not a prediction of final cost or an endorsement of honesty.

## Inputs and evidence

Obtain (1) the specification, requirements, and clarifications used for the estimate and (2) one or more estimates. Accept pasted text and available PDF, Word, and Excel files. Check that documents are readable and establish which requirements and versions each estimate uses. Report unreadable, inaccessible, incomplete, or ambiguous material and its effect; do not treat unread content as evidence. If either input is missing, request it.

Identify concrete functional blocks and the requirements/scenarios in each, tracing each to a source location (document and page/section, sheet/row, or other available locator). Consolidate comparable requirements so a block does not gain weight simply because one source lists many subitems. Show the proposed grouping. Preserve meaningful distinctions; mark uncertain interpretation and allow the user to adjust grouping.

For each block propose a priority with source and explanation: critical = 3 points, important = 2, additional = 1. Critical means necessary for the project's primary goal or core scenario; important materially affects use; additional supplements the solution or is explicitly optional. Treat an explicit priority in the requirements as evidence; distinguish it from an inference. If the priority cannot be reasonably determined, mark it uncertain and request clarification. Let the user change priorities and grouping at any time and recalculate, explaining changes.

## Coverage and comparison

Map each estimate to the same blocks and constituent requirements. Cite evidence from both the requirement and the estimate wherever possible. Use these statuses:

| Status | Meaning |
| --- | --- |
| Included | Explicit evidence confirms the requirement. |
| Partially included | Only part of a requirement or block is confirmed. |
| Possibly included | A broader estimate item may include it, but evidence is insufficient. |
| Not mentioned | No corresponding mention was found in the accessible estimate. |
| Excluded | The estimate explicitly excludes it. |
| Cannot determine | Material or detail is insufficient for a conclusion. |

An estimate line's silence is not proof of exclusion; inclusion in a broad line is not confirmation. A block earns its full points only when every requirement within it is confirmed. Never award partial points for possible or partial coverage. Surface missing, uncertain, and excluded work, especially critical blocks, and ask the relevant evaluator specific questions.

Check whether the estimates use the same requirements and cover comparable scope, stages, roles, and integrations. Compare stated hours and prices only where meaningful; report material differences and documented explanations without calling an estimate wrong solely due to a difference. Check sums and stated hour-times-rate arithmetic. Identify whether testing, defect correction, integration, setup, deployment, project coordination, permissions, and error handling are explicitly included, excluded, or unclear when relevant; do not assert that unstated supporting work is mandatory. Identify unclear scope boundaries that could lead to change requests as questions or potential risks, not predictions.

## Cost and leaderboard

Use an explicitly stated total cost. If absent, calculate it only if supplied hours and applicable rates unambiguously cover the total; show the calculation and its sources. Flag contradictions or incomplete amounts and ask for clarification; do not invent missing values. For a stated price range use its upper bound, while displaying the complete range. A positive, comparable total is required to compute a score; if absent or ambiguous, show the proposal separately and request clarification.

Establish the currency from explicit evidence; a dollar sign alone can be ambiguous. If the currency cannot be established, ask for clarification and exclude the proposal from the USD leaderboard until confirmed. Convert non-USD prices to USD using a verifiable current rate from an available source, recording original amount, converted amount, rate, date, and source. Use a consistent rate date across proposals where available. Do not invent exchange rates; if current rates cannot be verified, ask the user for rates and do not create a common cross-currency ranking until resolved. Identify user-supplied rates as such.

For each proposal, weighted coverage percentage = 100 × (sum of weights for completely confirmed blocks) / (sum of weights for all blocks). Score = coverage percentage / (comparable USD price / 1,000). Show the numerator, denominator, percentage, price, and score so the calculation is auditable. Sort eligible proposals by descending score; show ties as ties. Compute using unrounded values, then round displayed numbers consistently.

Include a proposal in the main leaderboard only if every critical block is confirmed, its price is comparable, and readable evidence is sufficient. Show all other proposals separately with specific reasons and evaluator questions; do not rank them last. If uncertain criticality, grouping, version differences, inconsistent pricing, or other gaps prevent a meaningful comparison, explain the limitation and ask questions instead of presenting a definitive ranking. The initial leaderboard is provisional because proposed grouping and priority can be changed. Explain that a high value score does not imply complete scope or the best choice under other criteria.

## Output

Use the user's explicitly requested language; otherwise use the language of their request, then the principal language of the supplied materials if the request language is indeterminate, then English. Translate labels for clarity while preserving original text where necessary for accuracy.

In chat, provide:
1. A short decision-oriented assessment of whether comparison is possible and the main differences.
2. For two or more estimates, a provisional leaderboard with weighted coverage, comparable USD price, score, and meaningful limitations; a separate list of unranked proposals and reasons. For one estimate, omit the comparative leaderboard.
3. The proposed blocks, priorities, their sources, and a coverage matrix with evidence and unresolved critical requirements. For many estimates, organize the matrix for readability without dropping proposals.
4. Hours and price comparisons, arithmetic discrepancies, currency conversions and sources, and explicitly identified exclusions and scope risks.
5. Clear, prioritized questions grouped by evaluator and any information needed from the user. Offer recalculation after changes to grouping, priorities, scope confirmation, or price.

Distinguish source facts from inference and missing information. Never claim an evaluator intended deception, predict a change request as a certainty, or present the ranking as stakeholder approval. Focus v1 on scope, hours, and cost; do not assess unrelated commercial terms.
