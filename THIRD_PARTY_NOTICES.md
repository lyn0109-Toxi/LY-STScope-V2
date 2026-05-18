# Third-Party Notices

LY-STScope Ver.2 uses open-source libraries and may connect to third-party data
and chart services. Third-party names, trademarks, ticker symbols, logos, and
data remain the property of their respective owners.

## Python Libraries

The app currently depends on:

- Streamlit
- pandas
- Altair
- Requests
- yfinance

These packages are generally distributed under permissive open-source licenses
such as Apache-style or BSD-style licenses. Their original license notices
remain with their respective projects.

## Market Data and Charts

- Finnhub: stock market API data, subject to Finnhub account, plan, and terms.
- Yahoo Finance / yfinance: prototype access to Yahoo Finance data through the
  yfinance library, subject to Yahoo's data terms and yfinance project notices.
- TradingView: embedded interactive chart widgets, subject to TradingView terms
  and attribution requirements.
- OpenAI: optional AI Coach reasoning model access through the OpenAI Responses
  API when a user-provided API key is configured. Without a key, the app uses a
  local rule-based coach.

## Internal Prototype Data

- REIT records in `reit_analysis_module.py` are educational sample inputs for
  model design and classroom discussion. They are not a live REIT data feed.
- Portfolio cost basis, diary entries, scenario assumptions, and personal
  finance results are generated from user-entered session data.

## Visual Assets

The app interface, CSS, and custom UI elements are original LY-STScope design
work unless otherwise noted. Generated or reference-based images should be kept
with clear provenance records before public or commercial use.
