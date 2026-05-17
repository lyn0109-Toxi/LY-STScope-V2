# LY-STScope Ver.2

LY-STScope Ver.2 is an educational personal financial intelligence prototype.
It connects stock valuation, portfolio risk, REIT analysis, personal finance,
calculation transparency, and financial diary reflection into one learning
dashboard.

## Purpose

This project is designed for educational and analytical discussion. It is not
an investment recommendation service, broker, adviser, tax tool, legal service,
or professional financial planning product.

The core goal is to help users learn how finance concepts can be applied to
real market examples:

- CAPM and required return
- Valuation triangulation
- Portfolio variance and covariance
- Correlation and diversification
- REIT-focused income and property exposure
- Personal finance health indicators
- Financial reflection and diary snapshots

## Data and Privacy Status

This is a prototype. Do not enter sensitive personal financial information.

Market data and charts may come from third-party services, including Finnhub,
TradingView, Yahoo Finance, and yfinance. Those services remain subject to their
own terms. Before any commercial launch, use a properly licensed market data
plan and complete a legal/privacy review.

## Main Files

- `streamlit_app.py`: main LY-STScope app
- `personal_finance_module.py`: personal finance interface
- `personal_finance_engine.py`: personal finance calculations
- `reit_analysis_module.py`: REIT-focused analytics module
- `pages/01_REIT_Focused_Analysis.py`: optional standalone REIT page
- `DATA_SOURCES.md`: data source and use notice
- `PRIVACY_NOTICE.md`: prototype privacy notice
- `THIRD_PARTY_NOTICES.md`: third-party notices
- `LICENSE`: source-visible educational prototype license

## Deployment

Recommended Streamlit secret:

```toml
FINNHUB_API_KEY = "your_finnhub_api_key_here"
```

The app keeps the Finnhub API key server-side through Streamlit Secrets. Do not
commit API keys to GitHub.

## License

Copyright (c) 2026 Young Lee. All rights reserved.

See `LICENSE`, `DATA_SOURCES.md`, `PRIVACY_NOTICE.md`, and
`THIRD_PARTY_NOTICES.md` before sharing, modifying, or commercializing this
project.

