# Professor Review Audit

Last checked: 2026-05-18

This file summarizes the pre-share review for LY-STScope Ver.2. It is intended
to help explain data provenance, known limitations, and error-handling behavior
before sharing the app with a professor.

## Scope Reviewed

- Main Streamlit app: `streamlit_app.py`
- Personal finance engine and UI: `personal_finance_engine.py`,
  `personal_finance_module.py`
- REIT analysis module: `reit_analysis_module.py`
- Data and legal notices: `DATA_SOURCES.md`, `PRIVACY_NOTICE.md`,
  `THIRD_PARTY_NOTICES.md`, `LICENSE`
- Tests: `tests/test_personal_finance_engine.py`

## Data Source Cross-Check

| Area | Source Used | Cross-Check Result | Presentation Guidance |
| --- | --- | --- | --- |
| U.S. stocks | Finnhub API | Code uses search, quote, profile, metric, peers, and candle endpoints. API key is read from Streamlit Secrets or environment, not hard-coded. | Present as third-party market/fundamental data that may be delayed, incomplete, quota-limited, or unavailable. |
| Korean stocks | Yahoo Finance through `yfinance` | Korean tickers are mapped locally, then price history and available info are pulled through `yfinance`. | Present as prototype research access, not official exchange or Yahoo-licensed production data. |
| USD/KRW | Yahoo Finance `KRW=X` through `yfinance` | App uses live FX when available and a manual fallback rate when unavailable. | State clearly that currency conversion is educational and may differ from broker/exchange rates. |
| Trading charts | TradingView widget | App embeds chart UI and keeps attribution-visible chart behavior. | Present charts as third-party visual reference, not app-owned market data. |
| REIT analysis | Internal sample data | REIT records in `SAMPLE_REITS` are hard-coded educational sample values. | Do not describe the REIT module as live market data. Say it is a finance-framework prototype. |
| Personal finance | User-entered values | Calculations come from session inputs and deterministic formulas. | Use sample inputs for professor demo; do not enter sensitive real financial data. |
| Portfolio cost basis | User-entered purchase price and shares | Unrealized P/L is calculated from current market value minus user-entered cost basis. | Explain that taxes, fees, dividends, FX execution rate, and realized gains are not included. |
| AI Coach | Rule-based by default; optional OpenAI Responses API | Verified model mode is optional and requires `OPENAI_API_KEY`. It sends structured app context and validates the response before display. | Position as educational reasoning support, not investment advice. |

## Official Reference Points

- Finnhub API documentation: https://finnhub.io/docs/api
- yfinance legal notice: https://ericpien.github.io/yfinance/getting_started/legal.html
- TradingView widgets: https://www.tradingview.com/widget/
- OpenAI Responses API guide: https://platform.openai.com/docs/guides/responses
- Streamlit docs: https://docs.streamlit.io/

## Error and Warning Review

| Check | Result |
| --- | --- |
| Python syntax compile | Passed for main app, REIT module, personal finance module, engine, and REIT page. |
| Personal finance tests | Passed. |
| Streamlit deprecated `use_container_width` | Replaced with `width="stretch"` / `width="content"` in active app modules. |
| Deprecated `st.components.v1.html` chart embed | Replaced with `st.html(..., unsafe_allow_javascript=True)` for the TradingView embed. |
| API key exposure | No API key is committed in source. `.streamlit/secrets.toml` is ignored. |
| Python cache files | Added `.gitignore` for `__pycache__` and `*.pyc`; cached files should not be shared as source. |
| Missing Finnhub key | App warns users and still allows Korean stock/yfinance paths and sample REIT module. |
| Missing OpenAI key | AI Coach remains local rule-based and shows a configuration warning. |
| Yahoo/yfinance failure | FX and price history functions fall back or return empty data; portfolio risk asks for enough holdings/history. |
| OpenAI API failure | Verified AI model falls back to rule-based AI Coach and displays the reason safely. |

## Known Limitations to Explain

- The app is an educational prototype, not a financial advisory product.
- Market data may be delayed, incomplete, inaccurate, quota-limited, or
  unavailable.
- REIT data is currently sample data and should not be cited as live market
  data.
- Valuation models use simplified assumptions: CAPM, peer P/E, dividend/EPS
  capitalization, book-value weighting, and user-controlled macro assumptions.
- Portfolio P/L excludes taxes, commissions, dividends, realized gains,
  lot-level accounting, and broker-specific FX execution rates.
- Personal Finance results are heuristic readiness signals, not professional
  financial planning.
- AI Coach is constrained to educational reasoning and should not provide buy,
  sell, legal, tax, immigration, or guaranteed-return advice.
- The public prototype should not collect sensitive personal financial
  information.

## Professor Demo Checklist

1. Open the main app and enter the LY-STScope dashboard.
2. Search one U.S. ticker such as `AAPL` or `MSFT` if Finnhub is configured.
3. Search one Korean stock such as `삼성전자` or `005930.KS` to show yfinance
   fallback coverage.
4. Add one or two holdings to Portfolio and enter sample shares plus average
   purchase price.
5. Open Calculation Details and show the cost-basis and unrealized P/L formula.
6. Open Personal Finance with sample values, then run a What-if Scenario.
7. Open Financial Diary, generate a Current Situation Report, and send it to
   AI Coach.
8. Use AI Coach's linked cards to explain how the app connects source data,
   assumptions, risk, and memory.

## Recommendation Before Sharing

The app is suitable for professor feedback as an educational prototype if it is
presented with the limitations above. For public or commercial launch, replace
prototype market data usage with licensed data plans, add formal privacy and
security controls, and review F-1, legal, financial-advice, tax, and data
licensing boundaries with qualified professionals.
