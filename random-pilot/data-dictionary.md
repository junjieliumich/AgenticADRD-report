# Experimental reporting assessment data

## Corpus and units

The corpus contains 501 DOI-deduplicated published articles from 2016–2025:
147 APSR, 155 AJPS, 45 AER, 9 QJE, 8 Econometrica, 14 REStud, 17 JPE,
88 PNAS, 16 Science and 2 Nature papers. All assessments use the same shared
prompt and GPT-5.6 Sol at medium reasoning effort in independent sessions.

`paper_id` uniquely identifies a paper in this corpus. `experiment_id` is unique
within a paper; use both keys for joins. `doi` links to the publisher article.
`journal` and `title` identify the source. Experiment roles are Primary, Supporting,
Diagnostic, Pilot without outcome, and Observational. The first three are scored.

## Tables

- `runs.csv`: one row per independent session, source/prompt hashes, model settings and token use.
- `papers.csv`: one row per paper, scored-experiment count and structural flags.
- `experiments.csv`: one row per identified study, role, design labels and scored flag.
- `criteria.csv`: one row per scored experiment and criterion (20 criteria).
- `components.csv`: one row per criterion component, with its rationale and evidence JSON.
- `design-labels.csv`: one row per study and label, supporting many-to-many joins.
- `criterion-summary.csv`: criterion counts and proportions, separately by study role.
- `assessments.json`: full records, including page-specific supporting evidence.
- `validation.json`: remaining evidence checks and documented metadata corrections.
- `review-issues.csv`: paper IDs and item-specific locations for evidence review.

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
nesting of experiments within papers.

`structural_flags` is the number of remaining automated evidence-field checks at
the paper level. It is repeated in experiment/criterion tables for filtering.
Quotation matching flags and classifications require substantive review against
source PDFs. Scores in the exports preserve the model's original judgments.
Current HTML and JSON are rendered from the same normalized records.

## Experiment inventory review

`inventory_flag` identifies repeated inventory entries whose individual identities
are absent: 146 historical entries in P082, 36 prior experiments in P041, and
35 matched-pair entries in EXP255. `include_in_summary` selects individually
identified scored experiments. All original model scores remain in the exports,
and the named experiments in P041 are included. The summary JSON gives the
current row counts. Filtering on `include_in_summary` reproduces the dashboard.

## Eight-measure comparisons

`comparisons/analysis-experiments.csv` contains all included experiments,
publication years, original design labels, a supplementary field classification,
and all 20 criterion scores. `journal-comparison.csv`, `annual-trends.csv` and
`experiment-types.csv` provide both all-scored and Primary-only summaries.
Each aggregate includes papers, experiments, points earned and denominator.
Mean total/results scores divide earned points by the number of experiments;
domain percentages divide pooled earned points by applicable points. C16 and
C19 percentages divide experiments earning 1 by applicable experiments.

Journal comparisons report APSR, AJPS, AER, QJE, Econometrica, REStud, JPE,
PNAS, Science and Nature separately. The eight-panel journal charts use the same values as the tables.
Annual trends use publication years for all ten journals. No observations are filled
in for empty years. SVG figures and the companion CSV files use identical values.

List, conjoint and survey labels reproduce the model output. Field is a separate
analyst classification using archived experiment descriptions and page-linked
article evidence. It covers real-world interventions, including online field
interventions and randomized operational procedures; artificial laboratory tasks,
hypothetical vignettes and elicitation-only tasks are excluded. A natural setting
alone does not establish this label. Classification records and publication-year
sources are in `classification-and-years.json`, generated from
`data/annotations/random-pilot-analysis.json`. Labels overlap. For APSR and AJPS, an empty field
classification indicates insufficient design information. Other journals are outside
this supplementary classification scope. `field_classification_status` distinguishes
these cases; both remain in the analysis dataset and are omitted from the Field subgroup.

Archive completed runs and rebuild all paper reports, data, and figures with:

```bash
PYTHONPATH=src python3 -m agenticadrd.reporting.random_pilot
```

The builder verifies all 501 run states and source/prompt hashes before assembling
the report. Retained and continuation runs are resolved using
`configs/review/full-corpus-remaining.json`. The `random-pilot` URL is retained
so existing dashboard and download links continue to work.

Rebuild comparisons from the assembled data with:

```bash
PYTHONPATH=src python3 -m agenticadrd.reporting.sample_comparisons
```

## Report navigation

`reports/current/random-pilot/index.html` is the single entry point for current
corpus results. Its five sections are journal comparisons (`#journals`), annual
trends (`#trends`), experiment types (`#types`), paper reports (`#papers`), and data
and methods (`#methods`). The experiment-scope control applies to all statistical
sections. Individual paper reports return to the searchable paper directory.

The former `comparisons/index.html` entry redirects to this dashboard; the
comparison data and figure files retain their download URLs. Query parameters
used to refresh browser caches do not identify different report versions.

The annual-trend view supports journal selection, a single-measure selector,
and both experiment scopes. Its CSV and SVG downloads follow the current
selection; annual sample-size downloads use the same selected journals and scope.
`journal-table-primary.csv` and `journal-table-all.csv` reproduce the displayed
eight-measure tables, including paper and experiment counts. Experiment-type
tables also have scope-specific CSV and SVG downloads beside the table.

Table images are available as editable SVGs and high-resolution PNGs. Rebuild
PNG files from the same SVG tables after regenerating comparisons:

```bash
pip install -e '.[figures]'
PYTHONPATH=src python3 -m agenticadrd.reporting.table_images
```

The table image renderer uses Georgia where installed, with DejaVu Serif as a
fallback. PNGs use twice the SVG pixel dimensions. Direct table download buttons
are available for each experiment scope.
