# LY-STScope Ver.2

LY-STScope Ver.2 combines the original LY-STScope stock valuation platform with a new REIT-focused analysis module. The main app remains LY-STScope, while the REIT module is available as a separate Streamlit page.

## Purpose

This app is designed as an educational analytics tool, not an investment recommendation service. The goal is to study how finance theory can be applied to stocks, portfolios, and REITs using real market examples.

## App Structure

- `streamlit_app.py`: Main LY-STScope stock valuation and portfolio analytics app.
- `pages/01_REIT_Focused_Analysis.py`: REIT-focused Ver.2 module.
- `docs/`: REIT analysis blueprint and data dictionary.
- `ontology/`: Initial REIT ontology structure.

## Planned Analysis Areas

- Stock valuation and portfolio analytics from the original LY-STScope.
- REIT sector classification: Retail, Industrial, Residential, Office, Healthcare, Data Center, Storage, Hotel, Diversified, Mortgage REITs.
- REIT-specific valuation: dividend yield, price to FFO, AFFO payout ratio, NAV premium or discount.
- Interest-rate sensitivity: relationship between REIT returns, Treasury yields, and financing conditions.
- Portfolio analysis: REIT allocation, sector concentration, beta, covariance, correlation, and diversification.
- Educational comparison: stock-style valuation versus REIT-style valuation.

## Streamlit Cloud

Main file:

```text
streamlit_app.py
```

Recommended secrets:

```toml
FINNHUB_API_KEY = "your_finnhub_api_key_here"
```

The app can run with sample REIT data even when an API key is not configured.
