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
- OpenAI's Responses API may be used only when `OPENAI_API_KEY` is configured
  and the user enables the verified AI model toggle. Without this key, AI Coach
  remains rule-based inside the app.
- The REIT analysis module currently uses educational sample REIT records in
  `reit_analysis_module.py`; it should not be presented as a live REIT market
  data feed.
- Personal Finance, Portfolio cost basis, Financial Diary, and What-if Scenario
  outputs depend on user-entered assumptions and session data.

## Endpoint and Field Mapping

| App Feature | Primary Source | Code Path | Main Fields Used |
| --- | --- | --- | --- |
| U.S. stock search | Finnhub `/search` | `resolve_ticker` | symbol, description, type |
| U.S. quote | Finnhub `/quote` | `load_stock` | current price, percent change |
| U.S. profile | Finnhub `/stock/profile2` | `load_stock` | company name, industry, market capitalization |
| U.S. fundamentals | Finnhub `/stock/metric` | `safe_metric` | P/E, EPS, dividend yield, beta, book value |
| Peer reference | Finnhub `/stock/peers` plus `/stock/metric` | `average_peer_pe` | peer symbols, peer P/E |
| Price history | Finnhub `/stock/candle`, then Yahoo Finance fallback | `load_price_history` | daily close prices |
| USD/KRW | Yahoo Finance `KRW=X` through `yfinance` | `load_live_usdkrw` | daily close FX rate |
| Korean equities | Yahoo Finance through `yfinance` | `load_korean_stock` | price history and available company info |
| Chart display | TradingView widget script | `render_tradingview_chart` | chart UI, not app-owned data |
| AI Coach verified mode | OpenAI Responses API | `call_verified_openai_model` | structured app context and JSON-schema response |
| REIT module | Internal sample dataset | `SAMPLE_REITS` | educational sample REIT metrics |

## Important Restrictions

- Do not expose API keys in source code, screenshots, public repositories, or
  browser-side JavaScript.
- Do not remove or hide TradingView attribution from embedded widgets.
- Do not present third-party data as owned by LY-STScope.
- Do not resell, redistribute, bulk-download, or cache third-party market data
  unless the relevant provider plan and terms explicitly allow it.
- Before commercial launch, replace prototype data usage with a properly
  licensed market data plan.
- Do not present Yahoo Finance or yfinance as an official Yahoo-supported API.
  yfinance states that it is not affiliated with Yahoo and is intended for
  research and educational purposes.
- Keep AI Coach outputs educational. They are generated from app context and
  validation rules, not from a registered financial adviser.

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
