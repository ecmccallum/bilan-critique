# bilan-critique

**Author:** Emma McCallum
**GitHub:** github.com/ecmccallum
**Started:** May 2026
**Status:** Active
**Last updated:** May 2026

---

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
| Eco CO2 | 2023 | 26.4 | 1.4 | 1,535.6 | 98.2% |

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

## What this project covers that the Lacq model does not

| Skill area | Lacq model | bilan-critique |
|---|---|---|
| Scope 1 and 2 accounting | Yes | Yes |
| ADEME Base Empreinte | Yes | Yes |
| EU climate targets | Yes | Yes |
| Scope 3 in depth | No | Yes |
| ISO 14064-1 applied | No | Yes |
| GHG Protocol Scope 3 Standard | No | Yes |
| CSRD and ESRS E1 | No | Yes |
| Double materiality | No | Yes |
| Market vs location-based Scope 2 | No | Yes |
| Data quality assessment | No | Yes |
| Cross-firm benchmarking | No | Yes |
| Transition plan structure | No | Yes |
| SQL data extraction | No | Yes |

---

## CV relevance

This project is directly relevant to roles in carbon accounting, GHG reporting, CSRD compliance, environmental consulting, and sustainability advisory. It demonstrates applied knowledge of ISO 14064-1, GHG Protocol, ESRS E1, BEGES methodology, and French regulatory context, combined with a reproducible Python and SQL technical workflow.