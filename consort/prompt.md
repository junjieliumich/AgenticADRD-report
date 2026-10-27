Act as an independent reviewer of experimental reporting. Evaluate whether a competent applied researcher can reconstruct each experiment and its statistical analysis using only the published main article.

Do not evaluate novelty, substantive importance, journal prestige, or whether you agree with the conclusions. Do not seek a predetermined winner. Apply exactly the same evidentiary standard to every paper.

## Source restriction

Use only the published main article, including its main-text tables, figures, table notes, figure notes, and footnotes.

Do not consult online appendices, supplementary information, preregistrations, registries, replication files, code, or external methodological references. A reference to excluded material does not supply the omitted information.

Use the supplied official CONSORT 2025 checklist only to define the scoring items and their components; it is not evidence about the papers. All paper-specific evidence must come from the published main article as specified above.

## Unit of evaluation

First identify every distinct randomized experiment.

Classify each as:

1. Primary experiment
2. Supporting experiment with a formal statistical analysis
3. Brief diagnostic randomization or robustness check
4. Pilot with no reported outcome
5. Observational analysis

Score categories 1–3 separately. List categories 4–5 without scoring them as experiments. Do not combine all randomizations into a single article-level score. Report the primary experiment separately from supporting and diagnostic experiments.

A follow-up using the original randomized assignment belongs to the original experiment. A new randomized sample or manipulation is a separate experiment.

## Binary scoring

Use:

- **1 = fully meets the reporting standard**
- **0 = does not fully meet the reporting standard**
- **N/A = logically inapplicable**

Do not award partial credit. If a material component required by a criterion is missing, score the entire criterion 0.

Use N/A only when the concept cannot apply to the design. Failure to report information is 0, not N/A.

## Evidence rule

A regression equation is not required when a regression table and its notes jointly make the analysis completely unambiguous.

A regression table may earn full credit when it clearly identifies:

- The outcome
- Treatment or experimental contrast
- Treatment and control coding
- Omitted or reference category
- Analysis unit
- Estimator
- Covariates or fixed effects in each specification
- Standard-error procedure
- Clustering or other dependence adjustment
- Analysis sample size
- Effect estimate
- Uncertainty measure
- Correspondence between the table column and the result discussed in the text

Do not reduce a score merely because this information appears in a table rather than in prose.

Conversely, merely naming an estimator—such as OLS, AMCE, marginal means, conditional AMCE, or a bootstrap—does not earn credit when the reader cannot reconstruct how it was implemented.

## Design map

Before scoring, create the following map for every experiment:

- Target population
- Eligibility criteria
- Recruitment procedure
- Field dates and setting
- Number recruited and analyzed
- Experimental arms or randomized attributes
- Unit of randomization
- Allocation probabilities and restrictions
- Exact treatment and comparator
- Outcome definitions and timing
- Estimand
- Estimator or statistical model
- Analysis unit
- Variable coding and reference categories
- Covariates and fixed effects
- Standard-error and inference procedure
- Handling of clustering or repeated observations
- Missing-data and attrition rules
- Effect estimates and uncertainty

Cite the page, table, figure, or footnote supporting every entry. Write “NR” when an element is not reported. Do not infer standard practice.

## Core reporting criteria

Score each experiment on the following binary criteria.

### Experimental design

1. **Population and recruitment:** Target population, eligibility, recruitment, and major exclusions are fully reported.
2. **Experimental conditions:** Treatment and comparator, or all randomized attributes and levels, are reported precisely enough to reproduce.
3. **Randomization:** Unit, probabilities or ratio, sequence-generation process, and restrictions are fully reported.
4. **Outcome measurement:** Outcomes, coding, timing, and primary or secondary status are fully reported.
5. **Participant flow:** Numbers recruited, randomized, exposed, followed, and analyzed are reported as applicable.

### Statistical methods

6. **Estimand:** The causal or descriptive quantity being estimated is explicitly defined.
7. **Estimator/model:** The statistical operation used to estimate the estimand is reconstructable from the text, table, or table notes.
8. **Analysis unit:** The reader can determine whether observations are participants, profiles, choices, sessions, or another unit.
9. **Coding and reference categories:** Treatment coding, outcome coding, omitted categories, and reference levels are explicit.
10. **Specification:** Covariates, fixed effects, weights, transformations, and column-to-column specification changes are explicit.
11. **Dependence and inference:** Standard errors, clustering, repeated-observation dependence, bootstrap or permutation procedures, and confidence-interval construction are explicit.
12. **Missingness and attrition:** Inclusion rules, missing outcomes, exclusions, attrition, and corresponding adjustments are explicit.
13. **Multiplicity and analysis status:** Multiple-testing procedures and prespecified versus exploratory analyses are distinguished.

### Results

14. **Analysis sample:** The number of observations used in each focal analysis is reported.
15. **Group quantities:** Relevant control means, treatment means, marginal means, or other raw quantities are reported.
16. **Effect and uncertainty:** Effect estimates and standard errors or confidence intervals are reported.
17. **Model-to-result traceability:** A reader can connect each focal numerical result directly to a particular outcome, contrast, specification, sample, and inference procedure.
18. **Robustness analyses:** Alternative specifications and sensitivity analyses are explained sufficiently to understand what changed.

### Validity assessment

19. **Internal-validity threats:** Attrition, noncompliance, spillovers, demand effects, measurement problems, and other relevant threats are discussed.
20. **Inferential scope:** The paper distinguishes the randomized contrast from broader claims about mechanisms, populations, and settings.

## Design-specific standards

### Ordinary treatment-control experiments

Award 1 for statistical-model reporting when the main-text regression table and notes jointly identify the outcome, treatment indicator, omitted control condition, analysis unit, adjustments, inference method, sample size, estimate, and uncertainty. Do not require a redundant mathematical equation.

### List experiments

Require the control and treatment lists, sensitive item, randomization mechanism, difference-in-means estimator, analysis unit, variance or confidence-interval procedure, sample size, and numerical estimate.

### Conjoint experiments

Award 1 only when the main text reports:

- Number of tasks and profiles per respondent
- Attribute levels and assignment probabilities
- Restrictions on profile construction
- Outcome coding
- Exact estimand
- Estimating model or computational procedure
- Analysis unit
- Reference categories
- Treatment of paired profiles and repeated observations
- Respondent-level clustering or another justified dependence adjustment
- Analysis sample size
- Direct mapping from the model to every focal AMCE, marginal mean, or related figure

The statement “we estimate AMCEs,” a citation to a standard conjoint article, or a pointer to an appendix is insufficient.

### Brief diagnostic randomizations

Score these separately. Do not average them with primary or formally analyzed experiments. If only two percentages are reported without an explicit contrast, uncertainty calculation, or arm-specific sample sizes, score the missing statistical criteria 0.

## CONSORT reporting

After completing the reconstructability assessment, provide a separate CONSORT 2025 table.

For compound CONSORT items, divide the item into its required components. Give the item a score of 1 only if every applicable component is fully reported. Otherwise score it 0. Keep article-level items—title, funding, conflicts, registration, and data access—separate from experiment-level methods and results.

Do not use the overall CONSORT total as a measure of statistical-model clarity. Report these separately:

1. Overall CONSORT completeness
2. Experimental-design reporting
3. Statistical-method transparency
4. Results transparency
5. Internal-validity discussion

## Required output

Produce:

1. An inventory of the experiments and their classifications.
2. A design map for every scored experiment.
3. A binary criterion-by-experiment table.
4. Separate totals for experimental design, statistical methods, results, and validity.
5. A separate CONSORT table.
6. A concise explanation of every 0, identifying the exact missing information.
7. A direct comparison of the papers’ statistical transparency.
8. A consistency audit confirming that tables and table notes received the same evidentiary status as prose.

### HTML presentation and scoring evidence

Save the output as a polished, self-contained HTML file that opens offline, with embedded styling, clear navigation, readable tables, and layouts suitable for desktop, mobile, and printing. Include the paper titles, experiment classifications, source scope, and a visible note that the AI-generated judgments await human review.

For every core criterion and CONSORT item, show its identifier, wording, score (1, 0, or N/A), and concise rationale. Display the score and evidence for each required component of compound items, alongside the overall item score. Each scoring component must have the relevant verbatim excerpt(s), one-based PDF page number(s), and printed page, table, figure, or footnote locator where available. Make scores link to their evidence details. For missing information, state exactly what is absent and which main-article pages or displays were reviewed; do not invent a quotation to support an absence. Explain every N/A judgment.

Show numerators, applicable-item denominators, and N/A counts for each subtotal. Keep core scores, CONSORT scores, article-level items, and experiment-level items clearly separated. Exclude N/A from denominators and avoid double-counting component scores in item totals. Include the scored records as downloadable JSON within the HTML so that the tables, evidence, and totals can be checked against the same data.

Do not give credit for customary practice, inferred implementation, or information available only outside the main article. Do give full credit when the main-text regression table and notes together make the analysis completely reconstructable.
