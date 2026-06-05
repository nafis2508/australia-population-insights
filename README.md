```markdown
# Australian Population Dashboard (1996–2016)

> Interactive Power BI analytics on two decades of Australian Bureau of Statistics (ABS) census data — exploring population growth, gender balance, age structure, and migration patterns across all 8 states and territories.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measures-blue)
![Data](https://img.shields.io/badge/Source-ABS%20Census-orange)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

---

## Table of Contents

- [Overview](#overview)
- [Live Preview](#live-preview)
- [Repository Structure](#repository-structure)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Dashboards](#dashboards)
- [Key Insights](#key-insights)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Applications](#applications)
- [Roadmap](#roadmap)
- [Author](#author)
- [License](#license)

---

## Overview

This project transforms raw ABS census data (1996–2016) into a three-page interactive Power BI report that surfaces how migration, age, and gender have reshaped Australia's demographics over twenty years. It is designed for policymakers, urban planners, and researchers who need fast, drillable answers to regional and cultural population questions.

**Highlights**
- 5 census years × 8 states/territories × 10 countries of birth
- 3 dashboards, 12+ interactive visuals, custom DAX measures
- Clean star-schema model for performant slicing and drill-through

## Live Preview

| | |
|---|---|
| Report file | [`dashboard/Visualisations.pbix`](./dashboard/Visualisations.pbix) |
| Full report (PDF) | [`docs/Report-48312932BusinessAnalyticsProject.pdf`](./docs/Report-48312932BusinessAnalyticsProject.pdf) |
| Screenshots | [`docs/screenshots/`](./docs/screenshots) |

## Repository Structure

```
.
├── dashboard/
│   └── Visualisations.pbix              # Power BI report
├── data/
│   ├── raw/                             # Original ABS exports
│   └── clean/AUS_COB_ABS.csv            # Modelled dataset
├── docs/
│   ├── screenshots/                     # Dashboard previews
│   ├── data-dictionary.md               # Field definitions
│   └── Report-48312932BusinessAnalyticsProject.pdf
├── LICENSE
└── README.md
```

## Dataset

| Attribute | Detail |
|---|---|
| **Source** | [Australian Bureau of Statistics](https://www.abs.gov.au/) — Census of Population and Housing |
| **Years** | 1996, 2001, 2006, 2011, 2016 |
| **Geography** | NSW, VIC, QLD, SA, WA, TAS, NT, ACT |
| **Dimensions** | Year · State · Gender · Age Group (0–24, 25–64, 65+) · Country of Birth |
| **Countries of Birth** | Australia, China, Thailand, Singapore, Germany, Ireland, Egypt, Fiji, New Zealand, United States |
| **Primary file** | `data/clean/AUS_COB_ABS.csv` |

See [`docs/data-dictionary.md`](./docs/data-dictionary.md) for field-level definitions.

## Methodology

1. **Ingest** — load ABS CSV exports via Power Query
2. **Clean** — normalize state codes, harmonize country labels, unpivot year columns
3. **Model** — star schema: `FactPopulation` joined to `DimYear`, `DimRegion`, `DimAgeGroup`, `DimCountry`
4. **Measure** — DAX for Growth %, Gender Ratio, AUS vs Overseas split, YoY change
5. **Visualize** — three themed pages with cross-filtering and drill-through

## Dashboards

### 1. Total Population Overview by Region
Line chart of population growth per state · gender split donut · age-group stacked bars · regional totals.

### 2. Country of Birth Analysis
Top-10 countries trended over time · share of population donut · age distribution by origin · gender ratio by country.

### 3. Australian vs Overseas-Born
AUS vs overseas growth trends · regional migrant breakdown · 100% stacked diversity index by state.

## Key Insights

- **Steady growth** — total population rose ~8.28% between 1996 and 2016.
- **Regional dominance** — NSW, VIC, and QLD lead in both size and growth.
- **Age divergence** — SA and TAS skew older; NSW and VIC carry younger workforces.
- **Migration shift** — Chinese-born population surged from 2001 onward; Thai migrants skew female, Egyptian migrants skew male.
- **Diversity hotspots** — NSW and VIC are the most culturally diverse; NT and TAS the least.

## Tech Stack

| Layer | Tool |
|---|---|
| Modelling & visuals | Power BI Desktop |
| Transformation | Power Query (M) |
| Calculations | DAX |
| Source data | Excel / CSV (ABS) |

## Getting Started

**Prerequisites:** [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (latest version)

```bash
git clone https://github.com/<your-username>/AustralianPopulationDashboard.git
cd AustralianPopulationDashboard
```

1. Open `dashboard/Visualisations.pbix` in Power BI Desktop
2. If prompted, point the data source to `data/clean/AUS_COB_ABS.csv`
3. Click **Refresh** to load the model
4. Interact via slicers (Year, State, Gender, Country) or drill through to detail pages

## Applications

- **Urban planning** — anticipate infrastructure demand by region
- **Health & education** — align services to shifting age structures
- **Migration policy** — identify under-served regions for balanced settlement

## Roadmap

- [ ] Extend to 2021 and 2026 ABS census releases
- [ ] Automate refresh via Power BI Service + ABS API
- [ ] Add forecasting (exponential smoothing / ARIMA) for scenario planning
- [ ] Embed choropleth maps for spatial migration flows
- [ ] Publish to Power BI Service with public embed link

## Author

**Muntasir Md Nafis**
Master of Business Analytics — Macquarie University, NSW
📧 [md.nafis08@gmail.com](mailto:md.nafis08@gmail.com) · 🔗 [LinkedIn](https://www.linkedin.com/in/muntasir-md-nafis/)

## License

Distributed under the MIT License. See [`LICENSE`](./LICENSE) for details.
Census data © Commonwealth of Australia (Australian Bureau of Statistics), used under [Creative Commons Attribution 4.0](https://creativecommons.org/licenses/by/4.0/).

---

> If you find this project useful, consider giving it a ⭐ on GitHub.
```

