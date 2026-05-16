# Does Weather Affect the Stock Market? A BIST 100 Analysis

## Project Overview
This project investigates whether daily weather conditions in Istanbul have a measurable
relationship with the performance of the BIST 100 index. Since Borsa Istanbul is located
in Istanbul, the city's local weather is a natural variable to examine. The project is
motivated by behavioral finance research which suggests that weather can influence investor
mood and trading decisions.

**Course:** DSA 210 – Introduction to Data Science, Sabancı University (Spring 2025–2026)

## Data Sources
- **BIST 100 (XU100.IS):** Daily open, close, and volume data fetched via `yfinance` (2023–2024)
- **Istanbul Weather:** Daily mean temperature, precipitation, and max windspeed fetched from
  the [Open-Meteo Archive API](https://open-meteo.com/) for coordinates 41.0082°N, 28.9784°E

## Project Structure
```
DSA210-project/
├── Eda.ipynb                  # Phase 1: Data collection, cleaning, and EDA
├── hypothesis_testing.ipynb   # Phase 2: Statistical hypothesis tests
├── machine_learning.ipynb     # Phase 3: ML models and evaluation
├── requirements.txt           # Python dependencies with pinned versions
└── README.md
data/                          # Auto-generated when notebooks are run
├── bist100.csv
├── istanbul_weather.csv
└── merged.csv
```

## How to Reproduce

### 1. Install dependencies
```bash
pip install -r requirements.txt
```

### 2. Run notebooks in order
Run the notebooks sequentially — each phase builds on the previous one's output:

```
1. Eda.ipynb                 → generates data/merged.csv
2. hypothesis_testing.ipynb  → reads data/merged.csv
3. machine_learning.ipynb    → reads data/merged.csv
```

Open with Jupyter:
```bash
jupyter notebook
```
Or with VS Code's Jupyter extension.

> **Note:** `Eda.ipynb` makes live API calls to Yahoo Finance and Open-Meteo.
> An internet connection is required for the first run. Subsequent runs can use the
> cached CSV files in `data/`.

## Key Findings
- No statistically significant relationship was found between weather variables
  (temperature, precipitation, windspeed) and BIST 100 daily returns (all p-values > 0.05).
- Machine learning models (Linear Regression, Ridge, Random Forest) achieved near-zero R²
  scores, confirming that weather has negligible predictive power over stock returns.
- Results are consistent with the Efficient Market Hypothesis: publicly available information
  such as weather is already reflected in asset prices.

## AI Usage Disclosure
This project used Anthropic Claude (Sonnet 4.x) as an assistant for:
- Writing explanatory comments in notebook cells
- Drafting README and final report structure
- Debugging Python and sklearn errors
- Conceptual verification of statistical tests

All code, analysis, and interpretations were reviewed and finalized by me.