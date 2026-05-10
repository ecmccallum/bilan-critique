# bilan-critique

**A reporting quality assessment of greenhouse gas reporting across five French professional services firms working in environmental engineering, certification, inspection, and ecological transition, using publicly available BEGES data from the ADEME platform.**

**Author:** Emma McCallum
**GitHub:** github.com/ecmccallum
**Started:** May 2026
**Status:** Complete
**Last updated:** May 2026

This project asks whether firms whose work is connected to environmental performance, certification, inspection, engineering, and ecological transition produce transparent and decision useful greenhouse gas reporting themselves.

---

## Scorecard

![Radar chart](figures/scorecard_radar.png)

![Summary table](figures/scorecard_table.png)

The scorecard synthesises findings from six analytical notebooks into a five-axis
reporting quality profile per firm. The average score is an unweighted indicative
synthesis metric, not a formal rating.

| Firm | Avg score / 100 |
|------|----------------|
| Artelia | 74.0 |
| Ecocert SA | 65.5 |
| Eco CO2 | 63.0 |
| Bureau Veritas | 47.0 |
| Antea France | 45.8 |

Scores reflect disclosure quality, not emissions performance.
---

## Key findings

**No firm scored consistently high across all five dimensions.** Reporting breadth,
methodology transparency, inventory balance, ESRS E1 readiness, and transition
plan disclosure do not necessarily move together. That is the central finding of
this project.

**Artelia had the strongest overall disclosure profile.** It performs consistently
across methodology transparency, inventory balance, and transition plan disclosure.
It is the only firm in this sample committed to SBTi. Its main weakness is coverage breadth at 45.5 percent.

**Eco CO2 had the strongest transition plan disclosure but the weakest inventory
balance.** It leads on coverage breadth, ESRS E1 readiness, and target setting,
but 91.6% of its reported emissions sit in only two categories. Broad coverage
does not guarantee a balanced inventory.

**Ecocert SA provided the most detailed methodology disclosure** Among the five
firms, Ecocert SA names specific database versions and gives structured uncertainty
estimates by scope. However, no 2030 or long-term reduction target appears in
its extracted fields.

**Bureau Veritas is the diagnostic case.** It has the highest reported emissions
at 23,298 tCO2e, the narrowest category coverage at 7 of 22 BEGES categories,
and a significant tension between its methodology statement and its numerical
reporting pattern. The full text disclosure reveals strategic intent and a quantified 2030 target, but the structured inventory data does not yet reflect the depth of the narrative planning disclosure.

**Business travel is zero for every firm.** P3.2 is the single most analytically significant zero in the dataset. For professional services and inspection firms whose staff often work at client sites, this absence requires methodological explanation.

**No firm addresses Scope 2 calculation basis.** ESRS E1 expects both
location-based and market-based Scope 2 figures. None of the five firms discloses
this in the structured ADEME export.

## Key analytical findings

### NB01: Emissions extraction

![Emissions by scope](figures/01_emissions_by_scope.png)

All five firms report Scope 3 equivalent emissions as more than 80% of their
total reported footprint. Bureau Veritas reports zero Scope 2 despite being
the highest total emitter at 23,298 tCO2e. This was later explained by
renewable electricity certificates using a market-based calculation, but the
structured export does not state this explicitly.

| Firm | Reporting year | Total tCO2e | Scope 3 share |
|------|---------------|-------------|---------------|
| Bureau Veritas | 2023 | 23,298 | 99.0% |
| Artelia | 2022 | 22,231 | 80.5% |
| Antea France | 2023 | 14,820 | 86.7% |
| Ecocert SA | 2024 | 3,764 | 84.6% |
| Eco CO2 | 2023 | 1,536 | 98.2% |

### NB02: Coverage matrix

![Coverage heatmap](figures/coverage_heatmap.png)

Across all 110 firm and category combinations, 57 return zero and only 53
return a positive value. More than half the available BEGES categories carry
no reported emissions across the dataset.

P3.2 business travel is zero for every firm. For professional services and
inspection firms whose staff work primarily at client sites, this is the most
analytically significant absence in the dataset.

| Firm | Categories reported | of 22 |
|------|--------------------|----|
| Eco CO2 | 14 | 63.6% |
| Antea France | 11 | 50.0% |
| Ecocert SA | 11 | 50.0% |
| Artelia | 10 | 45.5% |
| Bureau Veritas | 7 | 31.8% |

A high Scope 3 share does not imply broad category coverage. Bureau Veritas
reports 99% Scope 3 equivalent but covers only 7 of 22 categories.

### NB03: Methodology audit

![Transparency scores](figures/transparency_scores.png)

Firms are not equally transparent even when they use the same consolidation
method. Ecocert names Base Empreinte v23.2 and the Orki platform. Artelia is
the only firm to explain its zero categories with explicit justifications.
Bureau Veritas states all posts were reviewed with no materiality threshold,
yet reports positive values in only 7 of 22 categories.

| Firm | Transparency score / 12 |
|------|------------------------|
| Artelia | 10 |
| Ecocert SA | 9 |
| Bureau Veritas | 8 |
| Eco CO2 | 6 |
| Antea France | 5 |

The boundary field for most firms contains organisational marketing text rather
than an accounting boundary definition. That is a systematic transparency gap
across the dataset.

### NB04: ESRS E1 readiness

![ESRS E1 checklist](figures/esrs_checklist.png)

No firm addresses Scope 2 calculation basis in the structured export. Only
Eco CO2 discloses a long-term climate target. Only three firms disclose a
2030 reduction target. All five have an action plan and a base year, but
strategic target architecture is incomplete for most.

The most consequential systemic gap is the absence of long-term targets and
Scope 2 methodology disclosure. These indicate whether a firm's inventory is
connected to a structured climate strategy rather than functioning only as a
regulatory emissions declaration.

### NB05: Transition plan review

![Reduction levers](figures/bv_levers.png)

Bureau Veritas was selected because it combines the highest reported emissions,
the narrowest category coverage, and the clearest tension between narrative
planning and structured numerical reporting.

The full text disclosure reveals a firm more strategically engaged than the
structured export suggested. It has a quantified 2030 target of minus 40%
on Scopes 1 and 2 and minus 25% on Scope 3, a structured action plan, and
a governance structure including a dedicated Mobility Committee.

The illustrative reduction scenario achieves 4,856 tCO2e savings (20.8% of
reported baseline) using only categories with positive structured baselines.
P4.5 upstream leased assets and P4.1 upstream energy together account for
88% of the modelled reduction potential. Fleet electrification, refrigerant
management, and capital goods procurement are operationally relevant but
quantitatively secondary.

Reaching the disclosed 25% Scope 3 target would require stronger action on
P4.5 and P4.1, and measuring currently zero categories to establish a
complete baseline. The 23,298 tCO2e reported figure should be treated as a
floor, not a ceiling.

A domain-specific laboratory emissions analysis covers HVAC and ventilation
optimisation, cold storage and instrumentation loads, and green analytical
chemistry as a Scope 3 lever for solvent and reagent reduction linked to
P4.2 and P4.4.

---

## What this project measures

Five axes, each scored 0 to 100:

| Axis | Source | What it captures |
|------|--------|-----------------|
| Coverage breadth | NB02 | Percentage of 22 BEGES categories with a positive value |
| Methodology transparency | NB03 | Six-criterion rubric inspired by ISO 14064-1 and GHG Protocol |
| ESRS E1 readiness | NB04 | Eight-criterion readiness checklist |
| Inventory balance | NB02 and NB05 | Percentage of emissions outside the top two categories |
| Transition plan disclosure | NB05 | Five-criterion rubric on target and action plan quality |

All scores are based on publicly available ADEME structured data and free-text
fields. They measure what firms chose to disclose, not what they are actually
doing.

---

## Why this project matters

Published BEGES reports are often used as emissions data sources, but they can also be analysed as reporting documents. A reported emissions total is only useful if the boundary, category coverage, emission factors, data sources, uncertainty, exclusions, and targets are transparent enough to interpret.

This project applies BEGES category analysis, ISO 14064-1 inspired transparency criteria, GHG Protocol Corporate and Scope 3 logic, and ESRS E1 readiness indicators to compare reporting quality across firms operating in a similar professional services space.

The project demonstrates carbon accounting literacy, Python data analysis, regulatory interpretation, and consulting style synthesis across a complete analytical workflow from raw data to scored deliverable.

One section applies analytical chemistry domain knowledge to the Bureau Veritas transition plan review. The laboratory emissions analysis identifies major energy and consumables levers in analytical testing environments, including ventilation, fume hoods, instrumentation, cold storage, solvent use, reagents, and hazardous waste. This connects the carbon reporting critique to the operational reality of testing and inspection laboratories.

---

## Notebook workflow

| Notebook | Purpose | Status |
|----------|---------|--------|
| 00_firm_selection | SQL filtering of 11,138 organisations to five candidates | Complete |
| 01_emissions_extraction | BEGES P-category extraction, scope mapping, stacked bar chart | Complete |
| 02_coverage_matrix | Coverage classification, seaborn heatmap, coverage summary | Complete |
| 03_methodology_audit | Free-text extraction, six-criterion transparency scoring | Complete |
| 04_esrs_e1_checklist | Eight-criterion ESRS E1 readiness assessment | Complete |
| 05_transition_plan_review | Bureau Veritas transition plan, lever analysis, laboratory section | Complete |
| SC_scorecard | Five-axis radar chart and summary table synthesis | Complete |

---

## Data source

The primary data source is the ADEME BEGES open-data export, downloaded from
bilans-ges.ademe.fr in May 2026. The raw dataset contains published GHG
inventories from over 11,000 French organisations.

data/raw/export-opendata-inventories-03-05-2026.csv

---

## Methods and scoring logic

**Coverage breadth** uses the percentage of 22 BEGES categories with a positive
tCO2e value, directly from `coverage_summary.csv`.

**Methodology transparency** applies a six criterion manual review rubric scored 0 to 2 per criterion, inspired by ISO 14064 1 and GHG Protocol transparency principles. Criteria: organisational boundary disclosed, consolidation method stated, emission factors named, data sources described, uncertainty discussed, exclusions explained. Maximum 12 points, normalised to 100

**ESRS E1 readiness** aapplies an eight criterion binary checklist. Criteria: Scope 1 disclosed, Scope 2 disclosed, Scope 3 disclosed, base year disclosed, near term target disclosed, long term target disclosed, transition plan present, Scope 2 basis addressed. Maximum 8 points, normalised to 100. This is framed as a readiness indicator, not a legal compliance assessment. A full ESRS E1 assessment would require the company’s sustainability statement, double materiality assessment, climate risk disclosures, policies, transition plan details, and assurance context.

**Inventory balance** alculates the percentage of total reported emissions sitting outside the top two categories, then max normalises to 100. Higher scores indicate that the reported inventory is less dependent on one or two dominant categories.

**Transition plan disclosure** applies a five criterion binary rubric based on extracted ADEME target and action plan fields. Criteria: 2030 target disclosed, long term target disclosed, action plan present, actions linked to emissions categories, actions quantified with measurable indicators. Maximum 5 points, normalised to 100. This scores disclosure quality, not plan effectiveness.

---

## Limitations and interpretation caveats

In the processed ADEME export used here, blank or non disclosed category values are not distinguishable from zeros in the structured emissions columns. It is therefore not possible from the structured data alone to distinguish a genuine zero from a non disclosed or unreported category. All zero values are treated as prompts for methodology review rather than as automatic evidence of poor reporting.

Scores are based on ADEME structured data and free text fields only. Firms may have stronger internal documentation, more complete data, or more detailed methodology not captured in the public export.

The transition plan lever analysis for Bureau Veritas uses estimated savings based on the reported emissions profile and the firm’s public ADEME action plan text. These are illustrative scenarios, not verified forecasts.

The scorecard average is an unweighted synthesis metric. The individual dimension scores are more analytically meaningful than the ranking itself.

---

## Technical stack

| Tool | Purpose |
|------|---------|
| Python 3.13 | Primary language |
| DuckDB | SQL queries on CSV files |
| pandas | Data loading, transformation, inspection |
| matplotlib | Visualisation including radar chart and lever analysis |
| seaborn | Coverage heatmap |
| Jupyter | Analysis and documentation |

---

## Repository structure

'''
bilan-critique/
├── data/
│   ├── raw/
│   │   └── export-opendata-inventories-03-05-2026.csv
│   └── processed/
│       ├── selected_firms.csv
│       ├── five_firms_full.csv
│       ├── emissions_long.csv
│       ├── firm_summary.csv
│       ├── coverage_matrix.csv
│       ├── coverage_summary.csv
│       ├── transparency_scores.csv
│       └── esrs_scores.csv
├── notebooks/
│   ├── 00_firm_selection.ipynb
│   ├── 01_emissions_extraction.ipynb
│   ├── 02_coverage_matrix.ipynb
│   ├── 03_methodology_audit.ipynb
│   ├── 04_esrs_e1_checklist.ipynb
│   ├── 05_transition_plan_review.ipynb
│   └── SC_scorecard.ipynb
├── figures/
│   ├── 01_emissions_by_scope.png
│   ├── coverage_heatmap.png
│   ├── transparency_scores.png
│   ├── esrs_checklist.png
│   ├── bv_levers.png
│   ├── scorecard_radar.png
│   └── scorecard_table.png
├── references/
│   ├── ghg-protocol-revised.pdf
│   ├── Corporate-Value-Chain-Accounting-Reporing-Standard-EReader_041613_0.pdf
│   └── Methode_pour_la_realisation_des_BEGES_Art_L22925_Version_4.pdf
├── README.md
└── requirements.txt
'''

---

## How to reproduce

```bash
git clone https://github.com/ecmccallum/bilan-critique
cd bilan-critique
pip install -r requirements.txt
jupyter notebook
```

Run the notebooks in order from 00_firm_selection to 05_transition_plan_review, then run SC_scorecard last. The scorecard depends on processed CSV outputs generated by the earlier notebooks.

The raw ADEME export is not committed to the repository because of file size. Download it from the ADEME BEGES platform and place it here:
 `data/raw/export-opendata-inventories-03-05-2026.csv`.

---

## Skills demonstrated

Carbon accounting and GHG inventory assessment across Scope 1, 2, and 3.
ISO 14064-1 transparency criteria applied to real published reports.
GHG Protocol Corporate and Scope 3 Standards interpreted and applied.
ESRS E1 and CSRD readiness assessment framed as analytical indicators.
BEGES regulatory framework, P-category structure, and ADEME export logic.
French climate regulatory context including BEGES V4 and V5.
SQL data extraction and filtering with DuckDB across 11,000 organisation records.
Python data analysis with pandas including wide to long transformation,
pivot tables, groupby aggregation, and classification logic.
Visualisation including seaborn heatmaps, matplotlib radar charts, horizontal
bar charts, and styled table figures.
Multi-criteria scoring framework design and normalisation.
Consulting-style synthesis from raw data to scored deliverable.
Laboratory emissions analysis drawing on analytical chemistry expertise,
including HVAC and ventilation optimisation, cold storage energy loads,
instrumentation scheduling, and green analytical chemistry for solvent
and reagent reduction.



## What this project is

bilan-critique is a comparative greenhouse gas reporting analysis of French environmental, engineering, certification, and ecological transition organisations.

The project uses publicly available BEGES reports from the ADEME platform to evaluate not only what these organisations emit, but how clearly, completely, and transparently they disclose their emissions and reporting methodology.

The central question is this: do organisations whose work is directly connected to environmental performance, sustainability certification, compliance, and ecological transition produce high-quality greenhouse gas reporting themselves?

This is a meta-analysis. The subject is not emissions. The subject is reporting quality.


---

## Project context

This project is part of a GitHub portfolio.

It builds directly on previous Python-based emissions modelling work, including a Scope 1 and Scope 2 baseline and decarbonisation trajectory model for the Lacq industrial basin. That project covered emission factor sourcing, scenario modelling, and trajectory building. This project extends that foundation into Scope 3 depth, cross-firm benchmarking, regulatory framework application, and reporting quality assessment.

---

## Data source

The primary data source is the ADEME BEGES open-data export, downloaded from bilans-ges.ademe.fr in May 2026.

The raw dataset contains published greenhouse gas inventories from over 11,000 French organisations reporting through the BEGES platform. The file is stored locally as: data/raw/export-opendata-inventories-03-05-2026.csv
A supplementary reference is the Agence Déclic voluntary bilan carbone 2024/2025, used as a methodological benchmark and transparency reference. Total emissions of 69 tCO2eq across 26 employees, with six years of trend data and a detailed indirect emissions breakdown.

---

## Methodological frameworks applied

**ISO 14064-1:2018**
Organisational GHG quantification and reporting. Used to assess organisational boundary setting, emission source identification, base year selection, emission factor documentation, uncertainty assessment, and verification readiness.

**GHG Protocol Corporate Standard and Scope 3 Standard**
Scope 1, 2, and 3 accounting framework. All 15 Scope 3 categories assessed for relevance and coverage across selected firms. Market-based and location-based Scope 2 methods compared where data allows.

**ESRS E1 (CSRD)**
EU climate reporting disclosure requirements. Double materiality logic applied. Selected disclosure requirements checked against published BEGES data for each firm.

---

## Selected firms

Five firms were selected to allow cross-firm comparison across different organisation types within the environmental and sustainability advisory space.

**ARTELIA**
A large multidisciplinary engineering and consulting organisation working across mobility, water, energy, buildings, and industry. Selected for its scale and breadth of environmental engineering activity.

**ANTEA FRANCE**
An environmental and technical engineering consultancy. Its overlap with Artelia is intentional. Comparing two firms with similar profiles reveals how methodological choices rather than activity type drive reporting differences.

**BUREAU VERITAS EXPLOITATION**
A major inspection, certification, compliance, and risk management organisation. Its inclusion is important because the company works directly in standards, verification, and regulatory trust, making its own reporting quality especially relevant to assess.

**ECOCERT SA**
A sustainability certification, consulting, and training organisation focused on durable practices, environmental standards, climate, biodiversity, and responsible economic models. 778 employees, 2024 report, meaningful indirect emissions.

**Eco CO2**
An ecological transition and ESG advisory organisation with activity in mobility, transport, climate practices, and environmental behaviour change. Represents the smaller, mission-driven consultancy profile within the set.

### Reported emissions for selected firms

| Organisation | Year | Scope 1 (tCO2e) | Scope 2 (tCO2e) | Scope 3 (tCO2e) | Scope 3 % |
|---|---|---|---|---|---|
| ANTEA FRANCE | 2023 | 1,924.8 | 44.4 | 12,840.8 | 86.7% |
| ARTELIA | 2022 | 3,365.0 | 981.0 | 17,944.0 | 80.5% |
| BUREAU VERITAS EXPLOITATION | 2023 | 230.0 | 0.0 | 23,068.0 | 99.0% |
| ECOCERT SA | 2024 | 565.3 | 12.1 | 3,183.6 | 84.6% |
| Eco CO2 | 2023 | 26.4 | 1.4 | 1,513.92 | 96.8% |

Scope 1 and Scope 2 values map directly to BEGES Categories 1 and 2. Scope 3-equivalent values are primarily aggregated from BEGES indirect emissions categories P3, P4, and P5. BEGES P6 is treated separately because it refers to avoided emissions and does not correspond directly to GHG Protocol Scope 3 emissions.

---

## Key analytical findings to date

**Bureau Veritas Exploitation reports zero Scope 2.**
For a firm of this size with 23,068 tCO2e of Scope 3, a zero Scope 2 is unusual. This may reflect a market-based electricity accounting choice, incomplete disclosure, or a data entry/reporting issue. The methodology fields will be checked in Notebook 03.

**Antea France has the highest Scope 1 relative to peers.**
At 1,924.8 tCO2e, this is consistent with a field engineering firm running a large company vehicle fleet. P1.2 (mobile combustion) accounts for the majority of that figure.

**Headcount data was only available for Ecocert SA.**
778 employees, giving 4.1 tCO2e Scope 3 per employee. The other four firms had no headcount in the ADEME export. Emissions intensity cannot be calculated without sourcing this externally.

**Antea France and Bureau Veritas each have two reporting years available.**
2019 and 2023 reports exist for both firms. The older reports are preserved in five_firms_full.csv for potential within-firm evolution analysis.

**Eco CO2 is the only firm with a non-zero P6 value.**
P6 in BEGES refers to avoided emissions, not indirect emissions, and must be
excluded from Scope 3-equivalent totals. Eco CO2 reports 21.64 tCO2e in P6.1.
Their corrected Scope 3-equivalent total is 1,513.92 tCO2e (96.8% of total),
not 1,535.56 tCO2e as initially calculated. This will be investigated in
notebook 03 to determine whether the P6 value represents genuine avoided
emissions or a misclassification.
---

## Technical stack

| Tool | Purpose |
|---|---|
| Python 3.13 | Primary language |
| DuckDB | SQL queries on CSV files |
| pandas | Data loading, transformation, inspection |
| matplotlib / seaborn | Visualisation |
| Jupyter notebooks | Analysis and documentation |

---

## Repository structure

```
bilan-critique/
├── data/
│   ├── raw/
│   │   └── export-opendata-inventories-03-05-2026.csv
│   └── processed/
│       ├── selected_firms.csv
│       ├── selected_firms_indirect_emissions_check.csv
│       ├── five_firms_full.csv
│       ├── emissions_long.csv
│       └── firm_summary.csv
│       ├── p6_avoided_emissions.csv

├── notebooks/
│   ├── 00_firm_selection.ipynb              (complete)
│   ├── 01_emissions_extraction.ipynb        (complete)
│   ├── 02_indirect_emissions_coverage.ipynb (next)
│   ├── 03_methodology_audit.ipynb           (planned)
│   ├── 04_esrs_checklist.ipynb              (planned)
│   └── 05_transition_plan_review.ipynb      (planned)
├── references/
│   ├── ghg-protocol-revised.pdf
│   ├── Corporate-Value-Chain-Accounting-Reporing-Standard-EReader_041613_0.pdf
│   └── Methode_pour_la_realisation_des_BEGES_-_Art-L229-25-_Version_4.pdf
└── README.md
```

---

## Project specification

### Notebook 00: firm selection (complete)

Loads the ADEME BEGES open-data export. Inspects columns and data structure. Uses SQL via DuckDB to filter and rank candidate organisations. Applies a reporting quality screening score. Inspects organisation description fields. Selects five firms for comparative analysis. Exports selected firms to processed CSV checkpoints.

Key learning: SQL SELECT, WHERE, GROUP BY, ORDER BY, LIKE, CAST, IS NOT NULL, computed columns, query iteration logic, the difference between NAF codes and free-text description fields as selection signals.

### Notebook 01: emissions extraction (complete)

Extracts all BEGES emissions categories (P1.1 through P6.1) for the five selected firms. Documents the official BEGES category structure using the ADEME methodology document V4 (2016) and GHG Protocol Scope 3 Standard (2011) as primary references. Maps BEGES P-categories to GHG Protocol Scope 1, 2, and 3 equivalents. Transforms data from wide to long format. Calculates Scope 3 as a percentage of total reported emissions per firm. Flags headcount data gaps.

Key learning: pandas melt, wide versus long data formats, BEGES post structure and P-category groupings, BEGES to GHG Protocol mapping, emissions intensity calculation.

### Notebook 02: indirect emissions coverage (next)

For each firm, classifies each BEGES indirect emissions category as reported with a non-zero value, reported as zero, or missing. Builds a cross-firm coverage heatmap. Identifies which P3, P4, P5, and P6 categories are systematically absent. Maps BEGES categories to GHG Protocol Scope 3 categories to identify structural gaps. Uses the ADEME methodology document V4 as the primary reference for category definitions.

Key learning: seaborn heatmaps, categorical classification logic, coverage gap analysis, BEGES post-level interpretation, GHG Protocol Scope 3 category mapping.

### Notebook 03: methodology audit (planned)

Audits the free-text methodology fields for each firm. Checks for disclosure of organisational boundary, consolidation approach, emission factor sources, uncertainty, base year, and recalculation policy. Flags the Bureau Veritas zero Scope 2 question. Assesses market-based versus location-based Scope 2 disclosure. Uses ISO 14064-1 transparency requirements as the reference framework.

Key learning: pandas string methods and free-text extraction, ISO 14064-1 transparency criteria, qualitative scoring in Python.

### Notebook 04: ESRS E1 checklist (planned)

Applies selected ESRS E1 disclosure expectations to each firm's published BEGES data. Scores each firm against the checklist. Identifies gaps between current BEGES practice and CSRD-aligned reporting. Framed as readiness signals, not legal compliance. Introduces double materiality as a concept and assesses whether any firm addresses it.

Key learning: ESRS E1 structure, double materiality logic, disclosure requirement interpretation, scoring framework design in Python.

### Notebook 05: transition plan review (planned)

For the highest-emitting firm, extracts current reduction actions and targets from BEGES free-text fields. Proposes a stronger action plan with specific levers, estimated savings, and prioritisation by impact and feasibility. Aligns with Paris Agreement 1.5 degree trajectory using SNBC carbon budget reference. Framed as a consulting-style recommendation with honest caveats about data limitations.

Key learning: lever analysis, trajectory alignment, transition plan structure, SNBC reference values, waterfall chart visualisation.

---

## CV relevance

This project is directly relevant to roles in carbon accounting, GHG reporting, CSRD compliance, environmental consulting, and sustainability advisory. It demonstrates applied knowledge of ISO 14064-1, GHG Protocol, ESRS E1, BEGES methodology, and French regulatory context, combined with a reproducible Python and SQL technical workflow.