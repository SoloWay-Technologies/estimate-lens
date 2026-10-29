# EstimateLens v1 behavioral validation scenarios

Use these scenarios as manual acceptance checks for the shared skill. Each check should be run with the listed inputs and compared with the expected behavior; wording may vary, but the decision and evidence rules must hold.

## 1. One estimate, no leaderboard

**Input:** Requirements plus one estimate with hours, price, inclusions, exclusions, and assumptions.

**Expected:** Produce a coverage review, hours/cost checks, uncertainties, and prioritized questions. Do not present a comparative leaderboard or invent an independent estimate.

## 2. Weighted coverage and ranking

**Input:** Three functional blocks weighted Critical=3, Important=2, Additional=1. Proposal A fully covers all blocks at $30,000. Proposal B fully covers Critical and Important only at $20,000; Additional is explicitly excluded.

**Expected:** A has 100% coverage; B has 5/6 (about 83%) coverage. If B has all critical blocks confirmed, both are eligible. Rank by `coverage percentage / price in USD per $1,000`; show the inputs and formula.

## 3. Critical-block gating

**Input:** Proposal C is cheaper and covers all Important and Additional blocks, but one Critical block is “not stated” or “possibly included.”

**Expected:** C is excluded from the main leaderboard, shown in a separate section with the exact blocking status and a question asking for confirmation. Do not treat “not stated” as “excluded” or as confirmed coverage.

## 4. Partial and ambiguous evidence

**Input:** The requirements contain password recovery. An estimate contains only “Authentication — 40h.”

**Expected:** Mark password recovery as “possibly included” (or “cannot determine” if the context is insufficient), cite the source locations when available, and ask whether it is included and separately estimated. Never silently award full block points.

## 5. Functional grouping and user override

**Input:** One document lists checkout as one item; another lists cart, payment, confirmation, and receipt. The skill proposes one Checkout block and assigns Critical priority based on the stated primary purchase flow.

**Expected:** Explain the grouping and priority evidence. Accept a user correction to split/merge the block or change its priority, then recompute coverage, eligibility, and leaderboard and explain what changed.

## 6. Hours, rates, and arithmetic

**Input:** An estimate gives 120 hours at $50/hour but no total price. A second gives line items whose sum differs from its stated total.

**Expected:** Compute the first price as $6,000 and show the formula and source values. Flag the second arithmetic discrepancy. Do not compute a price when role-to-rate mapping or hours are ambiguous.

## 7. Price range

**Input:** An eligible estimate states `$20,000–$30,000`.

**Expected:** Use the upper bound ($30,000) for ranking, retain and display the full range, and state that the upper bound was used.

## 8. Currency conversion

**Input:** Comparable estimates use EUR and USD.

**Expected:** Convert non-USD prices using a verifiable current rate, showing original amount, USD amount, rate, date, and source. If no rate can be verified, request a user-supplied rate and withhold a mixed-currency leaderboard until resolved.

## 9. Language selection

**Input:** The user asks in Ukrainian, provides English source documents, and explicitly requests the final report in Polish.

**Expected:** Write the report in Polish. If no explicit language is requested, use the user’s message language; fall back to the dominant source language, then English only when unresolved. Keep original wording where translation could alter evidence.

## 10. Source citations and unreadable material

**Input:** A requirement appears on page 4 of a PDF and an estimate value appears on an Excel sheet/row. Another attachment cannot be read.

**Expected:** Cite page/section or sheet/row references where available. State that the unreadable attachment was not analyzed and do not infer its contents or claim complete coverage.

## 11. Change-request signals

**Input:** Requirements mention “reports,” while an estimate has one broad “Reporting” line with no report count or export formats.

**Expected:** Flag an unclear scope boundary as a clarification risk, explain the evidence gap, and formulate a concrete question. Do not assert dishonest intent or guarantee that a change request will occur.

## 12. Boundary and output checks

**Expected for every scenario:** The report separates confirmed facts, evaluator statements, and EstimateLens inferences; includes hours and cost only where supported; does not create its own hours/cost estimate; and keeps non-scorable proposals visible with reasons rather than silently dropping them.
