# bilan-critique

**Author:** Emma McCallum
**GitHub:** github.com/ecmccallum
**Started:** May 2026
**Status:** Active

---

## What this project is

bilan-critique is a comparative greenhouse gas reporting analysis of French environmental, engineering, certification, and ecological transition organisations.

The project uses publicly available BEGES reports from the ADEME platform to evaluate not only what these organisations emit, but how clearly, completely, and honestly they report their emissions.

The central question is this: do organisations whose work is directly connected to environmental performance, sustainability certification, compliance, and ecological transition produce high-quality greenhouse gas reporting themselves?

This is a meta-analysis. The subject is not emissions. The subject is reporting quality.

---

## Why this project exists

Most practitioners use published BEGES reports as data sources. Very few analyse them critically as objects of study.

Applying ISO 14064-1, the GHG Protocol Corporate and Scope 3 Standards, and ESRS E1 climate disclosure logic simultaneously to a set of firms in the same thematic space produces a genuinely novel comparison: not of emissions levels, but of reporting quality and methodological transparency.

For a hiring manager at a carbon consultancy or environmental advisory firm, this project signals something specific. It shows that the author understands not just how to calculate a bilan carbone, but how to assess whether one has been done well.

---

## Project context

This project is part of a GitHub portfolio built during an M1 internship in Environmental Analytical Chemistry at UPPA Pau, under Prof. Robert Duran at IPREM CNRS.

It builds directly on previous Python-based emissions modelling work, including a Scope 1 and Scope 2 baseline and decarbonisation trajectory model for the Lacq industrial basin. That project covered emission factor sourcing, scenario modelling, and trajectory building. This project extends that foundation into Scope 3 depth, cross-firm benchmarking, regulatory framework application, and reporting quality assessment.

---

## Data source

The primary data source is the ADEME BEGES open-data export, downloaded from bilans-ges.ademe.fr in May 2026.

The raw dataset contains published greenhouse gas inventories from over 11,000 French organisations reporting through the BEGES platform. The file is stored locally as:

```
data/raw/export-opendata-inventories-03-05-2026.csv
```

A supplementary reference is the Agence Déclic voluntary bilan carbone 2024/2025, used as a methodological benchmark and transparency reference. Total emissions of 69 tCO2eq across 26 employees, with six years of trend data and a detailed indirect emissions breakdown.

---

## Methodological frameworks applied

**ISO 14064-1:2018**
Organisational GHG quantification and reporting. Used to assess organisational boundary setting, emission source identification, base year selection, emission factor documentation, uncertainty assessment, and verification readiness.

**GHG Protocol Corporate Standard and Scope 3 Standard**
Scope 1, 2, and 3 accounting framework. All 15 Scope 3 categories assessed for relevance and coverage across selected firms. Market-based and location-based Scope 2 methods compared where data allows.

**ESRS E1 (CSRD)**
EU climate reporting disclosure requirements. Double materiality logic applied. Selected disclosure requirements checked against published BEGES data for each firm.

**Bilan Carbone V9 (ABC, 2024)**
French methodology context. ADEME Base Empreinte emission factors mapped against GHG Protocol categories. BEGES category structure (P1 through P6) translated into Scope 1, 2, and 3 equivalents.

---

## Selected firms

Five firms were selected for comparative analysis. Five firms rather than three were chosen to allow more robust cross-firm comparison and to capture a wider range of organisation types within the environmental and sustainability advisory space.

**ARTELIA**
A large multidisciplinary engineering and consulting organisation working across mobility, water, energy, buildings, and industry. Selected for its scale and breadth of environmental engineering activity.

**ANTEA FRANCE**
An environmental and technical engineering consultancy. Its overlap with Artelia is intentional. Comparing two firms with similar profiles reveals how methodological choices rather than activity type drive reporting differences.

**BUREAU VERITAS EXPLOITATION**
A major inspection, certification, compliance, and risk management organisation. Its inclusion is important because the company works directly in standards, verification, and regulatory trust. A firm that verifies others should itself report to a high standard.

**ECOCERT SA**
A sustainability certification, consulting, and training organisation focused on durable practices, environmental standards, climate, biodiversity, and responsible economic models. 778 employees, 2024 report, meaningful indirect emissions.

**Eco CO2**
An ecological transition and ESG advisory organisation with activity in mobility, transport, climate practices, and environmental behaviour change. Represents the smaller, mission-driven consultancy profile within the set.

### Verified indirect emissions for selected firms

| Organisation | Reporting year | Indirect emissions (tCO2e) |
|---|---|---|
| ANTEA FRANCE | 2023 | 12,840.80 |
| ARTELIA | 2022 | 17,944.00 |
| BUREAU VERITAS EXPLOITATION | 2023 | 23,068.00 |
| ECOCERT SA | 2024 | 3,183.60 |
| Eco CO2 | 2023 | 1,513.92 |

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
    data/
        raw/
            export-opendata-inventories-03-05-2026.csv
        processed/
            selected_firms.csv
            selected_firms_indirect_emissions_check.csv
    notebooks/
        00_firm_selection.ipynb
        01_emissions_extraction.ipynb        (next)
        02_scope3_coverage.ipynb             (planned)
        03_methodology_audit.ipynb           (planned)
        04_esrs_checklist.ipynb              (planned)
        05_reduction_action_plan.ipynb       (planned)
    README.md
```

---

## Project specification

### Notebook 00: firm selection (complete)

Loads the ADEME BEGES open-data export. Inspects columns and data structure. Uses SQL via DuckDB to filter and rank candidate organisations. Applies a reporting quality screening score. Inspects organisation description fields. Selects five firms for comparative analysis. Exports selected firms to a processed CSV checkpoint.

Key learning: SQL SELECT, WHERE, GROUP BY, ORDER BY, LIKE, CAST, IS NOT NULL, computed columns, query iteration logic, and the difference between NAF codes and free-text description fields as selection signals.

### Notebook 01: emissions extraction (next)

Extracts all BEGES emissions categories (P1.1 through P6.1) for the five selected firms. Translates BEGES category structure into GHG Protocol Scope 1, 2, and 3 equivalents. Transforms data from wide to long format for analysis. Calculates emissions intensity per employee where headcount data is available. Exports a clean emissions dataframe as the basis for all subsequent notebooks.

Key learning: pandas melt and pivot, long versus wide data formats, BEGES to GHG Protocol category mapping, emissions intensity calculation.

### Notebook 02: Scope 3 coverage audit

For each firm, assesses which BEGES indirect emissions categories are reported with primary data, reported with estimated data, explicitly excluded with justification, or absent without explanation. Builds a cross-firm coverage heatmap. Identifies systematic gaps and patterns across the five firms.

Key learning: seaborn heatmaps, categorical data visualisation, gap analysis logic, BEGES P3 through P5 category interpretation.

### Notebook 03: methodology audit

Documents where firms make different choices for the same reporting question. Scope 2 accounting method where data allows. Organisational boundary approach. Emission factor vintages and sources. Data quality documentation. Assesses whether choices are justified and disclosed, using ISO 14064-1 criteria as the reference.

Key learning: qualitative data extraction from free-text fields, comparative methodology assessment, ISO 14064-1 compliance criteria.

### Notebook 04: ESRS E1 checklist

Applies selected ESRS E1 disclosure expectations to each firm's published BEGES data. Scores each firm against the checklist. Identifies gaps between current BEGES practice and stronger CSRD-aligned reporting. Produces a scored comparison table. Discusses double materiality as a concept and assesses whether any firm addresses it.

Key learning: ESRS E1 structure, double materiality logic, disclosure requirement interpretation, scoring framework design in Python.

### Notebook 05: reduction action plan

For the highest-emitting firm, identifies the three to five highest-impact indirect emissions categories. Proposes specific and measurable reduction levers with estimated savings. Prioritises by impact, feasibility, and cost. Aligns with Paris Agreement 1.5 degree trajectory using SNBC carbon budget reference. Structures output as a transition plan meeting selected ESRS E1 requirements.

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
| Reduction action plan | No | Yes |
| Transition plan structure | No | Yes |
| SQL data extraction | No | Yes |

---

## CV relevance

This project is directly relevant to roles in carbon accounting, GHG reporting, CSRD compliance, environmental consulting, and sustainability advisory. It demonstrates applied knowledge of ISO 14064-1, GHG Protocol, ESRS E1, BEGES methodology, and French regulatory context, combined with a reproducible Python and SQL technical workflow.
