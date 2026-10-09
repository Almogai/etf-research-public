# ETF research public feed

Daily market research produced automatically after the US close by a private, rule-based app.
It contains **market research only**: no holdings, balances, positions or other account data.

| File | What it is |
|---|---|
| `research_input.md` | Full daily research input: market regime, sectors, HOT 15 and COLD 15 with reasons, headlines, SEC filings, insider activity, events |
| `research_input.json` | The same data, structured |
| `screen.md` | Short summary: regime, HOT and COLD tables |
| `scorecard.md` | Track record of past picks after 5, 20 and 60 trading days, plus a backtest |
| `learning.md` | Weekly review of which factors predicted returns (suggestions only) |
| `health.json` | When the last run happened, which session it covers, which steps succeeded |

Data: Yahoo Finance (yfinance), Google News RSS, Yahoo Finance RSS, SEC EDGAR. All free sources.

*Rule-based analysis, not financial advice. Past patterns do not guarantee future results.*
