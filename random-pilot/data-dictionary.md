# Random-sample assessment data

## Sampling and units

120 papers were drawn by simple random sampling without replacement from 501
DOI-deduplicated papers with published-version PDFs, using seed 20261124.
The sampling frame covers APSR, AJPS and the eligible economics/multidisciplinary
journal collection. Interpret summaries with respect to this sampling frame.

`paper_id` uniquely identifies a paper in this sample. `experiment_id` is unique
within a paper; use both keys for joins. `doi` links to the publisher article.
`journal` and `title` identify the source. Experiment roles are Primary, Supporting,
Diagnostic, Pilot without outcome, and Observational. The first three are scored.

## Tables

- `papers.csv`: one row per paper, scored-experiment count and structural flags.
- `experiments.csv`: one row per identified study, role, design labels and scored flag.
- `criteria.csv`: one row per scored experiment and criterion (20 criteria).
- `components.csv`: one row per criterion component, with its rationale and evidence JSON.
- `design-labels.csv`: one row per study and label, supporting many-to-many joins.
- `criterion-summary.csv`: criterion counts and proportions, separately by study role.
- `assessments.json`: full records, including page-specific supporting evidence.
- `validation.json`: remaining evidence checks and documented metadata corrections.

## Scores and aggregation

`score` is 0, 1 or the string N/A. `applicable` is 1 for scores 0 or 1 and 0 for N/A.
`met` counts scores of 1; `share = met / applicable`. `na` counts N/A entries.
A criterion is 1 when all applicable components are 1, 0 when any is 0, and N/A
when every component is N/A. Components are not separate observations in totals.
Domains cover criteria 1–5, 6–13, 14–18 and 19–20.

Design labels may overlap. Splitting or joining labels duplicates corresponding
experiment rows; compute an overall denominator before that join. Preserve
Primary, Supporting and Diagnostic roles in comparisons. No paper-level score
averaging these roles is supplied. For uncertainty estimates, account for the
nesting of experiments within sampled papers.

`structural_flags` is the number of remaining automated evidence-field checks at
the paper level. It is repeated in experiment/criterion tables for filtering.
Quotation matching flags and classifications require substantive review against
source PDFs. Scores in the exports preserve the model's original judgments.
Current HTML and JSON are rendered from the same normalized records.

## Experiment inventory review

`inventory_flag` identifies historical experiments without individual identities:
146 synthetic entries in P082 and 36 unidentified prior experiments in P041.
`include_in_summary` is 1 for the 266 scored experiments used in descriptive
summaries and 0 for those 182 entries and unscored studies. All original model
scores are retained in the tables. P041's six named conjoint experiments are
included. Coauthors can review the inventory decision and reproduce alternative
summaries by changing this filter.
