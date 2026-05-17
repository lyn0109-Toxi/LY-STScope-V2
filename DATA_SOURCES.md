# Data Sources and Usage Notice

LY-STScope Ver.2 is an educational prototype that combines user-entered
assumptions with third-party market data. It is not an official market data
product and does not provide investment advice.

## Market Data

- Finnhub may be used for stock quotes, company profiles, and selected
  fundamental metrics when a valid API key is configured through Streamlit
  Secrets.
- Yahoo Finance data may be accessed through `yfinance` for exchange rates,
  Korean stock data, and historical price data where available.
- TradingView widgets may be embedded for interactive chart display.

## Important Restrictions

- Do not expose API keys in source code, screenshots, public repositories, or
  browser-side JavaScript.
- Do not remove or hide TradingView attribution from embedded widgets.
- Do not present third-party data as owned by LY-STScope.
- Do not resell, redistribute, bulk-download, or cache third-party market data
  unless the relevant provider plan and terms explicitly allow it.
- Before commercial launch, replace prototype data usage with a properly
  licensed market data plan.

## Korean Stocks and FX

Korean stock prices are normally denominated in KRW, while many U.S. stocks are
denominated in USD. LY-STScope may convert portfolio weights using a live
USD/KRW exchange rate when available and a manual fallback rate when live FX
data is unavailable. Currency conversion is for educational comparison only.

## Educational Use

All valuation, portfolio risk, correlation, complementarity, REIT, and personal
finance outputs should be treated as educational model outputs. They may be
incomplete, delayed, inaccurate, or unavailable depending on third-party data
coverage.

