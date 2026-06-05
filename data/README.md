Here is a polished, industry-grade `README.md` for your `data/` folder — ready to paste directly:

---

```markdown
# 📊 Data Documentation

This directory contains all source and processed datasets for the **AustralianPopulationDashboard** project.

---

## 📁 Directory Layout

```
data/
├── raw/                    # Original, unmodified ABS extracts
│   ├── abs_census_1996.csv
│   ├── abs_census_2001.csv
│   ├── abs_census_2006.csv
│   ├── abs_census_2011.csv
│   └── abs_census_2016.csv
├── clean/                  # Production-ready, modelled dataset
│   └── AUS_COB_ABS.csv     # Star-schema fact table used by the Power BI report
└── docs/
    └── Report-48312932BusinessAnalyticsProject.pdf
```

---

## 🏛️ Data Source

**Australian Bureau of Statistics (ABS)**  
- Dataset: Census of Population and Housing  
- Geography: Australia (National + State/Territory level)  
- Time Span: 1996 – 2016 (5-year intervals)  
- Coverage: Population counts by **Gender**, **Age Group**, **State/Territory**, and **Country of Birth**

> All raw files are reproduced under the ABS *Creative Commons Attribution 4.0* licence.

---

## 🧹 Data Cleaning & Transformation

| Step | Description |
|------|-------------|
| **Ingest** | Power Query (M) reads each raw CSV and normalises headers |
| **Standardise** | Harmonised field names, codes, and category labels across all 5 census years |
| **Derive** | Calculated columns: `Year`, `Region`, `AgeGroup`, `Gender`, `CountryOfBirth` |
| **Validate** | Null checks, outlier bounds, and totals reconciled against ABS official summaries |
| **Export** | Single denormalised fact table written to `clean/AUS_COB_ABS.csv` |

---

## 📐 Schema: `AUS_COB_ABS.csv`

| Column | Type | Description | Example |
|--------|------|-------------|---------|
| `Year` | Integer | Census year | `2006` |
| `Region` | String | Australian state or territory | `New South Wales` |
| `AgeGroup` | String | 5-year age bracket | `25-29` |
| `Gender` | String | `Male` / `Female` | `Female` |
| `CountryOfBirth` | String | Country or region of birth | `China` |
| `Population` | Integer | Count of persons | `12,345` |

**Row count:** ~8,000 rows (5 years × 8 regions × 10 key countries of birth × age groups × genders)

---

## 🔄 Refresh Instructions

1. Download updated ABS census extracts (e.g., 2021, 2026) from [abs.gov.au](https://abs.gov.au)
2. Place new raw files in `data/raw/` using the naming convention `abs_census_YYYY.csv`
3. Open `dashboard/AustralianPopulationDashboard.pbix` in **Power BI Desktop**
4. In Power Query Editor, update the *Folder* or *CSV* source path to include the new files
5. Click **Refresh** → verify totals against ABS official release notes
6. Save and commit the updated `.pbix` and the new `clean/AUS_COB_ABS.csv`

---

## 📄 Additional Resources

| File | Purpose |
|------|---------|
| `docs/Report-48312932BusinessAnalyticsProject.pdf` | Academic project report with methodology, DAX measure definitions, and executive summary |

---

## ⚖️ Licence

Raw ABS data is licensed under [Creative Commons Attribution 4.0](https://creativecommons.org/licenses/by/4.0/).  
Processed datasets in `clean/` are released under the same licence.
```

---

