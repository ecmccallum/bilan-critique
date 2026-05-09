# BEGES Emissions Category Structure and GHG Protocol Mapping

**Sources**
- ADEME: *Méthode pour la réalisation des bilans d'émissions de GES*, Version 4, Octobre 2016 (official methodology)
- ADEME: https://bilans-ges.ademe.fr/ressources/points-cles-methodologiques
- GHG Protocol Corporate Standard (revised edition, 2004) — Chapter 4
- GHG Protocol Corporate Value Chain (Scope 3) Standard (2011) — Chapter 5, Table 5.3
- ISO TR 14069: *Guide d'application de la norme ISO 14064-1*

---

## Overview

The French BEGES framework (Bilan d'Émissions de Gaz à Effet de Serre) is grounded in
article L. 229-25 of the Code de l'environnement and draws on ISO 14064-1 and the GHG
Protocol. It organises emissions into **three categories** (called *scopes* in international
frameworks) and **23 sub-posts**. Categories 1 and 2, covering posts 1–7, are **mandatory**.
Category 3, covering posts 8–23, is **recommended but not obligatory** under the regulation.

The ADEME open-data export uses a **P1–P6 grouping** that rearranges those 23 posts into
six publication buckets. Both structures are documented below, with explicit cross-references.

> **Important:** BEGES and GHG Protocol are parallel frameworks, not identical ones.
> Mappings are approximate. Notebook 02 will build the explicit column-level mapping
> between BEGES P-category export columns and the 15 GHG Protocol Scope 3 categories.

---

## Part 1 — Official BEGES Structure: 3 Categories, 23 Posts

### Category 1 — Émissions directes de GES (≈ Scope 1) | MANDATORY | Posts 1–5

Direct GHG emissions from fixed and mobile sources owned or controlled by the organisation.
Governed by operational or financial control consolidation approach (chosen by the organisation).

| Post | Name | Key sources | GHG Protocol Scope 3 cat. |
|------|------|-------------|--------------------------|
| 1 | Émissions directes des sources fixes de combustion | Boilers, furnaces, turbines, flares, generators burning fossil or biomass fuels | — (Scope 1) |
| 2 | Émissions directes des sources mobiles à moteur thermique | Company vehicles, aircraft, ships, trains under organisational control | — (Scope 1) |
| 3 | Émissions directes des procédés hors énergie | Industrial chemical or biological processes: cement decarbonation, aluminium electrolysis, N₂O from soils, NF₃ from electronics manufacture | — (Scope 1) |
| 4 | Émissions directes fugitives | Refrigerant leaks, landfill methane, methane from livestock, nitrification/denitrification, coal seam gas | — (Scope 1) |
| 5 | Émissions issues de la biomasse (sols et forêts) | Land use and land use change (LULUCF): CO₂, CH₄, N₂O from biomass growth, decay, soil carbon changes, deforestation | — (Scope 1) |

**Notes for posts 1–5**
- Biomass CO₂ must be quantified **separately** from fossil CO₂ across all posts.
- The consolidation approach (financial control vs. operational control) directly determines
  which sources fall in Category 1 vs. Category 3 (leasing posts 14 and 21).
- For installations covered by EU ETS (directive 2003/87/CE), the verified measurement
  method approved by the inspection authority should be used where available.

---

### Category 2 — Émissions indirectes associées à l'énergie (≈ Scope 2) | MANDATORY | Posts 6–7

Emissions from the production of purchased electricity, heat, steam, or cooling consumed
by the organisation. Scope covers the **production phase only** — upstream fuel chain
emissions (extraction, transport, refining) fall in Post 8 (Category 3).

| Post | Name | Key sources | GHG Protocol Scope 3 cat. |
|------|------|-------------|--------------------------|
| 6 | Émissions indirectes liées à la consommation d'électricité | Electricity production: grid average or usage-based factor (heating, lighting, base load, intermittent) from Base Carbone® | — (Scope 2) |
| 7 | Émissions indirectes liées à la consommation de vapeur, chaleur ou froid | District heat/cold production: use supplier emission factor based on their energy mix, or French average if unavailable | — (Scope 2) |

**Notes for posts 6–7**
- **Electricity factor rule:** only Base Carbone® factors are permitted. No supplier discrimination.
  Use either the usage-based approach (heating / lighting / base / intermittent) or the average
  production factor, never both in the same inventory.
- The methodology does **not** require a market-based vs. location-based dual disclosure,
  unlike the GHG Protocol Scope 2 Guidance (2015). This is a key gap for ESRS E1 readiness.
- Renewable self-generation: autoconsumption offsets the consumption in post 6.
  Electricity sold back to the grid generates *avoided emissions*, reported separately, never
  netted against the inventory total.

---

### Category 3 — Autres émissions indirectes de GES (≈ Scope 3) | RECOMMENDED | Posts 8–23

All other indirect emissions caused by the organisation's activities but arising from sources
controlled by third parties. Not part of the regulatory obligation but recommended and
increasingly expected under CSRD / ESRS E1.

| Post | Name | Description | Bilan Carbone® tab | GHG Protocol Scope 3 cat. |
|------|------|-------------|-------------------|--------------------------|
| 8 | Émissions liées à l'énergie non incluses dans catégories 1 et 2 | Upstream fuel chain: extraction, transport, refining, distribution of all energy carriers used in posts 1–7. For electricity: T&D losses. "Well to tank" in transport terms. | ÉNERGIE | Cat 3 — Fuel and energy related |
| 9 | Achats de produits ou services | Purchased goods and services, cradle to the last supplier gate. Includes embedded transport between suppliers. Does **not** include last-mile freight to the organisation (→ post 12). | INTRANTS | Cat 1 — Purchased goods and services |
| 10 | Immobilisations de biens | Capital goods: same as post 9 but for fixed assets. Emissions amortised over accounting depreciation period (recommended), physical lifetime, or expensed in year of acquisition. | IMMOBILISATION | Cat 2 — Capital goods |
| 11 | Déchets | Transport and treatment of waste generated by the organisation. Mode-specific emission factors: incineration (CO₂f, CO₂b), landfill (CH₄, CO₂b), biological treatment (CH₄, N₂O, CO₂b), recycling (CO₂f). | DÉCHETS DIRECTS | Cat 5 — Waste generated in operations |
| 12 | Transport de marchandises amont | Upstream freight whose cost is borne by the organisation (not already in categories 1–2). Covers all modes. Can use the regulatory "information GES des prestations de transport" (mandatory for carriers since Oct 2013), adjusted by +3 % to convert CO₂ to all-GES. | TRANSPORT | Cat 4 — Upstream transportation and distribution |
| 13 | Déplacements professionnels | Business travel by transport not owned or controlled by the organisation. Includes accommodation when material. Same +3 % adjustment applies. | DÉPLACEMENTS | Cat 6 — Business travel |
| 14 | Actifs en leasing amont | Assets leased **by** the organisation from third parties. Treatment depends on consolidation approach and contract type (finance lease vs. operating lease — see Table 4 of methodology). Under operational control, operating leases fall here; under financial control, only non-owned assets. | Depends on asset type | Cat 8 — Upstream leased assets |
| 15 | Investissements | For financial sector: GHG emissions financed by loans, bonds, equity. For other sectors: proportional share of Scope 1+2 emissions of third-party entities the organisation holds a stake in but does not control. | Not in Bilan Carbone® | Cat 15 — Investments |
| 16 | Transport des visiteurs et des clients | Visitor and client travel to the organisation's premises, not in categories 1–2. Allocation required if journey has mixed purposes. | DÉPLACEMENTS | No direct equivalent (≈ Cat 4 downstream) |
| 17 | Transport de marchandises aval | Downstream freight whose cost is **not** borne by the organisation. Methodologically identical to post 12. | TRANSPORT | Cat 9 — Downstream transportation and distribution |
| 18 | Utilisation des produits vendus | Emissions from use of sold products and services after they leave the organisation. Calculated over full product lifetime for all units sold during the reporting year. Covers both direct-emitting products (vehicles) and energy-consuming products (appliances). | UTILISATION | Cat 11 — Use of sold products |
| 19 | Fin de vie des produits vendus | End-of-life treatment of products sold during the reporting year. Requires end-of-life scenario modelling. Methodology mirrors post 11. | FIN DE VIE | Cat 12 — End of life treatment of sold products |
| 20 | Franchise aval | Emissions from franchisee operations, reported by the **franchisor**. Compiled by applying this same methodology to franchisee data, typically via sampling. | Not in Bilan Carbone® | Cat 14 — Franchises |
| 21 | Leasing aval | Emissions from assets **owned by** the organisation and leased to third parties. Covers full asset lifecycle. Risk of double-count with posts 9 and 10. | Depends on asset type | Cat 13 — Downstream leased assets |
| 22 | Déplacements domicile-travail | Employee home-to-work commuting by transport not owned or controlled by the organisation. Primary data rarely available; secondary data from HR records or employee surveys. Telework emissions (heating, electricity, IT equipment) are included. | DÉPLACEMENTS | Cat 7 — Employee commuting |
| 23 | Autres émissions indirectes | Catch-all for indirect emissions not classifiable in posts 8–22. | Not in Bilan Carbone® | No direct equivalent |

---

## Part 2 — ADEME Open-Data Export: P1–P6 Publication Categories

The ADEME public platform groups the 23 posts into six P-categories for display and export.
These do **not** add up to new totals — they are a reorganisation of the same posts.

| P category | Scope equiv. | Posts included | Regulatory status |
|------------|-------------|----------------|-------------------|
| P1 — Émissions directes | Scope 1 | Posts 1–5 | Mandatory |
| P2 — Émissions indirectes associées à l'énergie | Scope 2 | Posts 6–7 | Mandatory |
| P3 — Émissions indirectes associées au transport | Scope 3 | Posts 12, 13, 16, 17, 22 | Recommended |
| P4 — Émissions indirectes associées aux produits achetés | Scope 3 | Posts 8, 9, 10, 11, 14 | Recommended |
| P5 — Émissions indirectes associées aux produits vendus | Scope 3 | Posts 18, 19, 20, 21 | Recommended |
| P6 — Autres émissions indirectes | Scope 3 | Posts 15, 23 | Recommended |

**What this means for NB01 and NB02**

The CSV export columns will reflect the P1–P6 grouping, likely with sub-columns per post
or per GHG type. Many organisations only fill P1 and P2. A firm that reports P3–P5 at all
is already above average. The coverage matrix in NB02 should classify each post as:
`reported` (non-null, non-zero value), `zero` (value of 0.0, which may mean not applicable),
or `missing` (null — the firm did not assess this post).

---

## Part 3 — GHG Protocol Scope 3: 15 Categories

Official structure from *Corporate Value Chain (Scope 3) Standard*, Table 5.3.

**Upstream categories (1–8)**

| Cat | Name |
|-----|------|
| 1 | Purchased goods and services |
| 2 | Capital goods |
| 3 | Fuel and energy related activities |
| 4 | Upstream transportation and distribution |
| 5 | Waste generated in operations |
| 6 | Business travel |
| 7 | Employee commuting |
| 8 | Upstream leased assets |

**Downstream categories (9–15)**

| Cat | Name |
|-----|------|
| 9 | Downstream transportation and distribution |
| 10 | Processing of sold products |
| 11 | Use of sold products |
| 12 | End of life treatment of sold products |
| 13 | Downstream leased assets |
| 14 | Franchises |
| 15 | Investments |

**Note:** GHG Protocol Category 10 (Processing of sold products) has no direct BEGES
equivalent. It covers intermediate manufacturers whose products are further processed
before end use. It will appear as a gap in the mapping table.

---

## Part 4 — Key Methodological Differences to Flag in NB03

These are the issues most likely to surface during the methodology audit of the five firms.

**1. Consolidation approach**
BEGES requires the organisation to declare whether it uses financial control or operational
control consolidation. This choice directly determines which leased assets appear in Category 1
vs. posts 14 and 21. Firms must disclose their choice. Comparing two firms without knowing
their consolidation approach is methodologically invalid.

**2. Electricity emission factors**
BEGES only permits Base Carbone® factors. The GHG Protocol Scope 2 Guidance (2015)
requires dual reporting: location-based and market-based. BEGES does not. A firm reporting
near-zero Scope 2 due to a renewable energy contract would comply with BEGES while
potentially obscuring physical grid emissions. Flag for NB03 and NB04 (ESRS E1 readiness).

**3. Biomass CO₂**
Must be reported separately from fossil CO₂ in every post. Many firms collapse them.
The ADEME export likely has separate columns for CO₂b (biogenic) and CO₂f (fossil).

**4. Avoided emissions**
Cannot be netted against the inventory total under any circumstances. Reported separately in
a dedicated table on the ADEME platform. A firm that nets avoided emissions against its total
is non-compliant. Check for this in the free-text methodology fields in NB03.

**5. Carbon offsets and compensation**
Reduction estimates from voluntary compensation projects cannot be deducted from the BEGES
total. They may appear in the action plan section only. Any firm reporting a net figure that
includes offset deductions is misrepresenting its gross emissions.

**6. Category 3 exclusion threshold**
A firm may exclude a mandatory post (Category 1 or 2) only if all excluded posts together
represent less than 5 % of estimated total emissions, pre-assessed. Any exclusion must be
justified in the report. Category 3 posts can be excluded without justification since they are
recommended, not mandatory.

**7. Reporting year**
The reporting year is the calendar year preceding the year in which the BEGES is filed,
or the penultimate year if the preceding year's data is unavailable. The reference year
(baseline for tracking progress) must post-date 1999 and must be recalculated if the
organisational perimeter or calculation methodology changes significantly.

---

## Part 5 — Consolidated Cross-Reference Table

| BEGES Post | BEGES P cat. | Regulatory status | Bilan Carbone® tab | GHG Protocol Scope | GHG Protocol cat. |
|-----------|-------------|------------------|-------------------|-------------------|--------------------|
| 1 — Fixed combustion | P1 | Mandatory | ÉNERGIE | Scope 1 | — |
| 2 — Mobile combustion | P1 | Mandatory | TRANSPORT / DÉPLACEMENTS | Scope 1 | — |
| 3 — Process emissions | P1 | Mandatory | HORS ÉNERGIE | Scope 1 | — |
| 4 — Fugitive emissions | P1 | Mandatory | HORS ÉNERGIE | Scope 1 | — |
| 5 — Biomass / LULUCF | P1 | Mandatory | Not in Bilan Carbone® | Scope 1 | — |
| 6 — Purchased electricity | P2 | Mandatory | ÉNERGIE | Scope 2 | — |
| 7 — Heat / steam / cold | P2 | Mandatory | ÉNERGIE | Scope 2 | — |
| 8 — Upstream energy chain | P4 | Recommended | ÉNERGIE | Scope 3 | Cat 3 |
| 9 — Purchased goods & services | P4 | Recommended | INTRANTS | Scope 3 | Cat 1 |
| 10 — Capital goods | P4 | Recommended | IMMOBILISATION | Scope 3 | Cat 2 |
| 11 — Waste | P4 | Recommended | DÉCHETS DIRECTS | Scope 3 | Cat 5 |
| 12 — Upstream freight | P3 | Recommended | TRANSPORT | Scope 3 | Cat 4 |
| 13 — Business travel | P3 | Recommended | DÉPLACEMENTS | Scope 3 | Cat 6 |
| 14 — Upstream leased assets | P4 | Recommended | Depends on asset | Scope 3 | Cat 8 |
| 15 — Investments | P6 | Recommended | Not in Bilan Carbone® | Scope 3 | Cat 15 |
| 16 — Visitor / client travel | P3 | Recommended | DÉPLACEMENTS | Scope 3 | ≈ Cat 4 downstream |
| 17 — Downstream freight | P3 | Recommended | TRANSPORT | Scope 3 | Cat 9 |
| 18 — Use of sold products | P5 | Recommended | UTILISATION | Scope 3 | Cat 11 |
| 19 — End of life | P5 | Recommended | FIN DE VIE | Scope 3 | Cat 12 |
| 20 — Franchises | P5 | Recommended | Not in Bilan Carbone® | Scope 3 | Cat 14 |
| 21 — Downstream leased assets | P5 | Recommended | Depends on asset | Scope 3 | Cat 13 |
| 22 — Commuting | P3 | Recommended | DÉPLACEMENTS | Scope 3 | Cat 7 |
| 23 — Other indirect | P6 | Recommended | Not in Bilan Carbone® | Scope 3 | — |
| — | — | — | — | Scope 3 | Cat 10 — Processing of sold products — **no BEGES equivalent** |

---

*Last updated: May 2026. Built for the bilan-critique portfolio project.*
*Emma McCallum | github.com/ecmccallum | M1 EACM, UPPA Pau*
