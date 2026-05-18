# LY-STScope Ver.2

LY-STScope Ver.2 combines the original LY-STScope stock valuation platform with REIT-focused analysis, personal finance, calculation transparency, and a financial diary. The main app remains LY-STScope, while the REIT module is available inside the main app's `REIT Analysis` tab and also as a Streamlit page.

## Purpose

This app is designed as an educational personal financial intelligence platform, not an investment recommendation service. The goal is to help users understand, protect, and manage their financial life by connecting income, spending, savings, investments, real estate exposure, portfolio risk, and life goals with real market examples.

## AI Reasoning Era Direction

LY-STScope Ver.2 is being prepared as an early prototype for the coming AI reasoning and agentic intelligence era. The product direction is not to become a stock picker. It is to become a structured financial reasoning environment where a future AI assistant can help users ask better questions, understand trade-offs, and review the assumptions behind financial decisions.

Future-facing design principles:

- **Reasoning before recommendation:** the app should explain risk, trade-offs, assumptions, and scenarios before suggesting any action.
- **Life context before asset selection:** portfolio analysis should be interpreted alongside income, spending, savings, debt, emergency funds, real estate exposure, and life goals.
- **Scenario support:** users should be able to ask what happens if interest rates change, income falls, portfolio value declines, REIT dividends change, or a major life expense appears.
- **Memory with privacy:** the Financial Diary is a seed for user-controlled financial memory. It should support reflection without requiring sensitive account connections in the prototype stage.
- **Explainability:** Calculation Details should act as a reasoning audit trail, showing formulas, inputs, assumptions, limitations, and data sources.
- **Voice and agent readiness:** future interfaces may use AirPods, mobile assistants, or AI agents. LY-STScope should support short summaries, deeper explanations, and detailed evidence views.

## Current Preparation Stage

The current project should be treated as an educational prototype and venture-preparation asset. It can support user interviews, professor feedback, portfolio demonstration, pitch preparation, and product validation. It should not be operated as a paid financial advisory service without legal, data licensing, privacy, and immigration review.

Because the founder is considering venture creation while in F-1 student status, monetization, employment through a founder-owned company, and commercial operation should be reviewed with the university DSO and a qualified immigration attorney before launch. In the current stage, the safer positioning is free educational beta, academic validation, and responsible prototype development.

## App Structure

- `streamlit_app.py`: Main LY-STScope stock valuation and portfolio analytics app.
- `reit_analysis_module.py`: REIT-focused Ver.2 module used inside the main app.
- `pages/01_REIT_Focused_Analysis.py`: Optional standalone REIT-focused page.
- `personal_finance_engine.py`: Experimental Personal Finance calculation engine.
- `personal_finance_module.py`: Personal Finance Streamlit UI module.
- `docs/`: REIT analysis blueprint and data dictionary.
- `ontology/`: Initial REIT ontology structure.
- `DATA_SOURCES.md`: Data source, API, limitation, and usage notice.
- `PROFESSOR_REVIEW_AUDIT.md`: Pre-share audit for data provenance, warnings,
  known limitations, and professor demo checklist.

## Planned Analysis Areas

- Stock valuation and portfolio analytics from the original LY-STScope.
- Korean stock search expansion with approximately 100 major KOSPI/KOSDAQ companies searchable by company name or ticker.
- Multi-currency portfolio view for US and Korean stocks, with USD/KRW conversion using a live FX rate when available and a manual fallback rate when live data is unavailable.
- REIT sector classification: Retail, Industrial, Residential, Office, Healthcare, Data Center, Storage, Hotel, Diversified, Mortgage REITs.
- REIT-specific valuation: dividend yield, price to FFO, AFFO payout ratio, NAV premium or discount.
- Interest-rate sensitivity: relationship between REIT returns, Treasury yields, and financing conditions.
- Portfolio analysis: REIT allocation, sector concentration, beta, covariance, correlation, diversification, cost basis, unrealized profit/loss, and personal return tracking.
- Educational comparison: stock-style valuation versus REIT-style valuation.
- Personal Finance test engine: net worth, cash flow, emergency fund, savings rate, debt-to-income, risk capacity, and financial health score.
- What-if Scenario Lab: stress-test income, expenses, cash shocks, portfolio moves, USD/KRW changes, interest-rate moves, and rate-sensitive allocation.
- Calculation Details: transparent formulas, data inputs, assumptions, valuation contribution, covariance, correlation, and personal finance score breakdown.
- Financial Diary: session-based portfolio and personal finance snapshots, current situation reports, user notes, next actions, and JSON download/restore.
- Life Design entry screen: one-click first screen that frames LY-STScope as a personal life and financial intelligence dashboard before entering the main app.
- AI Coach: rule-based by default, with linked guidance cards for Portfolio, Personal Finance, Scenario, Diary, and Calculation Details plus an optional verified OpenAI Responses API layer for structured reasoning answers.
- Structured Scenario Packet: downloadable JSON context that can later become an input format for an AI financial reasoning coach.

## Streamlit Cloud

Main file:

```text
streamlit_app.py
```

Recommended secrets:

```toml
FINNHUB_API_KEY = "your_finnhub_api_key_here"
OPENAI_API_KEY = "your_openai_api_key_here"
OPENAI_MODEL = "gpt-5-mini"
OPENAI_REASONING_EFFORT = "medium"
OPENAI_AI_DEFAULT_ON = "false"
```

The app can run with sample REIT data even when an API key is not configured.

`OPENAI_API_KEY` is optional. Without it, AI Coach remains a local rule-based prototype. With it, users can enable a verified model mode that sends structured LY-STScope context to OpenAI's Responses API and then passes the answer through local safety validation before display.
