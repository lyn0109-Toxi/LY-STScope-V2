# LY-STScope Ver.2 - REIT-Focused Analysis

LY-STScope Ver.2 is a separate educational prototype focused on Real Estate Investment Trusts, or REITs. It extends the finance learning direction of LY-STScope by applying valuation, risk, diversification, and macro sensitivity concepts to real estate securities.

## Purpose

This app is designed as an educational analytics tool, not an investment recommendation service. The goal is to study how finance theory can be applied to REITs using real market examples.

## Planned Analysis Areas

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
