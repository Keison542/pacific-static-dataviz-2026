# Pacific Sea Level Rise Analysis

[![R](https://img.shields.io/badge/R-4.5-blue.svg)](https://www.r-project.org/)
[![Quarto](https://img.shields.io/badge/Quarto-1.4.554-blue.svg)](https://quarto.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📋 Overview

This project analyzes sea level rise trends across 21 Pacific Island nations, with a specific focus on Papua New Guinea (PNG) as the country with the fastest recorded rate of sea level rise in the Pacific region. The analysis spans 30 years of data (1993–2023) and examines:

- Sea level anomaly trends per country and subregion
- The influence of El Niño–Southern Oscillation (ENSO) on sea levels
- Surface and sea surface temperature trends
- Disaster economic losses and affected populations

**Key finding**: PNG's sea levels are rising at **7.8 mm per year** (95% CI: 7.0–8.5 mm/yr) — the fastest among all 21 Pacific Island nations.

## 🗂️ Repository Structure

```
├── docs/
│   └── PNG_Coast_Lost_to_the_Sea.pdf    # Rendered output (static report)
├── data/
│   ├── sea_level_anomalies.csv          # Sea level data
│   ├── surface_temp_anomalies.csv       # Surface temperature data
│   ├── sea_surface_temperature_anomalies.csv # SST data
│   ├── direct_disaster_economic_loss.csv     # Economic loss data
│   └── number_of_persons_directly_affected_by_disaster.csv # Affected persons
├── README.md                            # This file
└── index.qmd                            # Quarto source file
```

## 📊 Data Sources

| Dataset | Source | Description |
|---------|--------|-------------|
| Sea Level Anomalies | [SPC Pacific Data Hub](https://stats.pacificdata.org/vis?lc=en&df[ds]=SPC2&df[id]=DF_CLIMATE_CHANGE&df[ag]=SPC&df[vs]=1.0&av=true&dq=A.SEA_LVL.&pd=,&to[TIME_PERIOD]=false) | Annual sea level measurements (1993–2023) |
| Surface Temperature Anomalies | [SPC Pacific Data Hub](https://stats.pacificdata.org/vis?lc=en&df[ds]=SPC2&df[id]=DF_CLIMATE_CHANGE&df[ag]=SPC&df[vs]=1.0&av=true&dq=A.ST_ANOM.&pd=,&to[TIME_PERIOD]=false) | ST_ANOM indicator |
| Sea Surface Temperature Anomalies | [SPC Pacific Data Hub](https://stats.pacificdata.org/vis?lc=en&df[ds]=SPC2&df[id]=DF_CLIMATE_CHANGE&df[ag]=SPC&df[vs]=1.0&av=true&dq=A.SST_ANOM.&pd=,&to[TIME_PERIOD]=false) | SST_ANOM indicator |
| Disaster Economic Loss | [SPC Pacific Data Hub – SDG 11.5.2](https://stats.pacificdata.org/vis?lc=en&df[ds]=ds%3ASPC2&df[id]=DF_SDG_11&df[ag]=SPC&df[vs]=3.0&dq=A.VC_DSR_AALT...._T.....&pd=,&to[TIME_PERIOD]=false) | Direct economic losses from disasters |
| Persons Affected by Disasters | [SPC Pacific Data Hub – SDG 11.5.2](https://stats.pacificdata.org/vis?lc=en&df[ds]=ds%3ASPC2&df[id]=DF_SDG_11&df[ag]=SPC&df[vs]=3.0&dq=A.VC_DSR_AFFCT.........&pd=,&to[TIME_PERIOD]=false&lb=bt) | Number of people directly affected |
| Oceanic Niño Index (ONI) | [NOAA Climate Prediction Center](https://www.cpc.ncep.noaa.gov/data/indices/oni.ascii.txt) | Annual ENSO indicator |

## 🛠️ Technologies Used

- **R 4.5** — Data processing and statistical analysis
- **Quarto** — Reproducible reporting
- **Tidyverse** — Data manipulation and visualization
- **broom** — Statistical model tidying
- **gt** — Table generation
- **maps** — Geographic visualization
- **scales** — Plot scaling and formatting

## 📈 Key Visualizations

1. **Ranked trends per country** — Sea level rise rates with 95% confidence intervals
2. **Spaghetti plot** — All 21 nations' trajectories with PNG highlighted
3. **Pacific map** — Geographic distribution of rise rates by subregion
4. **Dual-axis ENSO plot** — Sea level vs. ONI index (1993–2023)
5. **ENSO sensitivity chart** — Model improvement when adding ONI predictor
6. **Temperature trends** — Surface and sea surface temperature anomalies
7. **Disaster impact visualizations** — Economic losses and affected persons

## 🔬 Statistical Methods

- Ordinary least squares (OLS) linear regression for trend estimation
- 95% confidence intervals for all trend estimates
- Wilcoxon rank-sum test for ENSO comparisons (p-value reported)
- LOESS smoothing for trajectory visualization
- Subregional aggregation and comparison (Melanesia, Micronesia, Polynesia)

## 🚀 How to Reproduce

1. **Clone the repository**
   ```bash
   git clone https://github.com/Keison542/pacific-static-dataviz-2026.git
   cd pacific-static-dataviz-2026
   ```

2. **Install R packages**
   ```r
   install.packages(c("tidyverse", "broom", "gt", "maps", "scales"))
   ```

3. **Update file paths** — Modify the CSV import paths in `index.qmd` to point to your local `data/` folder:
   ```r
   raw <- read.csv("data/sea_level_anomalies.csv")
   # ... update all other read.csv() calls similarly
   ```

4. **Render the report**
   ```bash
   quarto render index.qmd
   ```

## 📄 Output

The rendered report includes:
- A styled HTML document with professional typography
- Interactive visualizations (when viewed in browser)
- Complete statistical output and interpretations
- Source citations and methodology notes

**View the full report**: [PNG_Coast_Lost_to_the_Sea.pdf](docs/PNG_Coast_Lost_to_the_Sea.pdf)

## 🎨 Design Notes

- **Hero section**: Custom CSS gradient banner with typography from Google Fonts (Playfair Display, Inter)
- **Color palette**: Ocean-themed (#1a5276, #1abc9c, #e74c3c)
- **Subregion colors**: Melanesia (#1a5276), Micronesia (#1abc9c), Polynesia (#f39c12)
- **Statistical highlights**: Pull quotes, stat boxes, and finding cards for key insights

## 📝 Key Findings

| Metric | Value |
|--------|-------|
| Nations analyzed | 21 Pacific Island nations |
| Time period | 1993–2023 (30 years) |
| PNG's rise rate | 7.8 mm/yr (fastest in dataset) |
| Confidence interval | 7.0–8.5 mm/yr |
| Total economic loss | $1.1B USD |
| Persons affected | 2.98M |
| ENSO p-value | <0.001 (significant suppression effect) |

## 🤝 Contributing

This is a static project for the Pacific Dataviz Challenge 2026. Feedback and suggestions are welcome via GitHub issues.

## 📧 Contact

**Keison Tipiou**  
[LinkedIn](https://www.linkedin.com/in/keison-tipiou-7a817a6a/)

## 📚 Citation

If you use this work, please cite:

> Tipiou, K. (2026). *Papua New Guinea's Coast Is Being Lost to the Sea: A Sea Level Rise Analysis Across 21 Pacific Island Nations*. Pacific Dataviz Challenge 2026. GitHub: https://github.com/Keison542/pacific-static-dataviz-2026

---

**Pacific Dataviz Challenge 2026** · Theme: Climate Change
