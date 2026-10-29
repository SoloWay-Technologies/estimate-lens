# EstimateLens by SoloWay Tech

EstimateLens is a SoloWay Tech skill for reviewing project estimates before a client or Client Partner commits to a proposal.

## Why we built it

Different companies can review the same brief and produce very different estimates. The difference is not always a mistake or bad faith. One estimate may include testing, integrations, deployment, and failure handling, while another may price only the main happy path. A lower initial price can therefore reflect a smaller or less clearly defined scope. Work that was not discussed up front may later appear as a change request.

EstimateLens makes those differences visible. It compares what each proposal confirms against the requirements that were used to prepare it, shows where the scope is unclear, and produces concrete questions for the evaluator. It helps a client or Client Partner choose a proposal with a clearer understanding of what is included, what is missing, and what still needs confirmation.

## What it does

EstimateLens can review one estimate or compare several estimates from one to many evaluators. It accepts requirements and estimates supplied as chat text or accessible PDF, Word, and Excel files.

It:

- groups requirements into functional blocks and explains the grouping;
- proposes requirement priorities from the brief: Critical (3 points), Important (2 points), or Additional (1 point);
- maps every estimate to the same blocks and distinguishes Included, Partially included, Possibly included, Not mentioned, Excluded, and Cannot determine;
- checks whether proposals cover a comparable scope and identifies unclear boundaries that may need clarification;
- checks hours, totals, and hour-times-rate arithmetic when the source data is sufficient;
- calculates a price from supplied hours and rates only when the mapping is unambiguous;
- uses the upper bound when a price is given as a range;
- converts non-USD prices using a verifiable current exchange rate and records the original amount, rate, date, and source;
- builds a provisional leaderboard by weighted confirmed coverage per USD 1,000;
- keeps proposals with an unconfirmed critical block or incomparable price visible in a separate, unranked section;
- prepares prioritized questions for each evaluator.

The main leaderboard includes only proposals that confirm every Critical block and have a comparable price. A proposal with an unconfirmed mandatory feature is not silently ranked last or treated as covered. With one estimate, EstimateLens provides a review and questions without a comparative leaderboard.

**Value score** = confirmed weighted coverage (%) / (comparable price in USD / 1,000). A block contributes its full weight only when all of its requirements are confirmed. The leaderboard is provisional: users can correct the grouping or priorities and recalculate it.

## What it does not do

EstimateLens does not create its own hours or price estimate in v1. It does not decide whether a company acted dishonestly, guarantee that change requests will not occur, or assess commercial terms outside scope, hours, and cost. A score is an auditable comparison under the stated evidence and weighting; it is not a guarantee that the highest-ranked proposal is the best business decision.

## Typical result

The chat report starts with a decision-oriented summary:

1. whether the proposals can be compared;
2. the provisional leaderboard, when there are multiple eligible estimates;
3. proposals that cannot yet be ranked and the reasons;
4. the most important scope, hours, and price differences;
5. questions that should be answered before choosing.

The detailed section includes the proposed functional blocks and priorities, source references, the coverage matrix, cost calculations, currency conversions, exclusions, assumptions, and questions grouped by evaluator. The user can change the grouping or priority and ask EstimateLens to recalculate the leaderboard.

The report follows the user's explicitly requested language. Without an explicit choice, it follows the language of the user's request, then the principal language of the supplied materials, and uses English only when the language remains unresolved.

## Package layout

The portable plugin is in `plugins/estimate-lens/`:

```text
plugins/estimate-lens/
├── plugin.json
├── .claude-plugin/plugin.json
└── skills/estimate-lens/SKILL.md
```

The repository also contains marketplace catalogs for the two local clients:

- Claude Code: `.claude-plugin/marketplace.json`
- Codex: `.agents/plugins/marketplace.json`

`soloway-tech` is the local catalog identifier used by these files. It identifies this SoloWay Tech marketplace catalog; it is not a claim that a company-wide marketplace is already registered under that name. After the repository is hosted in SoloWay's corporate Git service, use the actual repository URL when registering the marketplace.

## Local installation

From a checkout of this repository, Claude Code can register and install the plugin with:

```text
claude plugin marketplace add <local checkout path or corporate repository URL>
claude plugin install estimate-lens@soloway-tech
```

Codex can register the same repository marketplace with:

```text
codex plugin marketplace add <local checkout path or corporate repository URL>
```

Then install `EstimateLens` from the `soloway-tech` source in the Codex Plugins Directory. The exact UI and availability depend on the Codex client and organization policy. Restart or reload plugins after changing a local checkout.

These instructions describe local and private repository distribution. Public marketplace publication, workspace administration, access control, and the final corporate repository URL are deployment decisions for SoloWay Tech.

## Evidence and privacy

The skill reports source locations when the host can identify them, such as a PDF page, document section, or Excel sheet and row. If an attachment cannot be read, EstimateLens says so and does not infer its contents. File access, document extraction, exchange-rate lookup, and network access depend on the host agent's tools and permissions. Follow SoloWay's data-handling policy before providing confidential client material to any external service.
