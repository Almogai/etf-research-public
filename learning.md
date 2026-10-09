# Weekly learning — 2026-10-09

Which factors predicted returns vs QQQ over the following 5 and 20 trading days? **IC** = rank correlation between a factor and the later excess return (+0.05 is useful, 0 is nothing, negative is the wrong way). **Spread** = how much the top 20% of stocks on the factor beat the bottom 20% on average. **t** above 2 means the result was consistent.

## History: price factors, last 12 months (no look-ahead)

| Factor | Horizon | Samples | IC | t | IC > 0 | Top–bottom spread |
|---|---|---|---|---|---|---|
| trend | 5 days | 51 | +0.004 | 0.2 | 45% | +0.13% |
| momentum | 5 days | 51 | +0.003 | 0.1 | 49% | +0.30% |
| relative_strength | 5 days | 51 | -0.010 | -0.3 | 47% | +0.06% |
| volatility | 5 days | 51 | -0.012 | -0.7 | 43% | -0.41% |
| liquidity | 5 days | 51 | +0.021 | 1.0 | 65% | +0.40% |
| price score (combined) | 5 days | 51 | +0.003 | 0.1 | 49% | +0.23% |
| trend | 20 days | 13 | -0.012 | -0.3 | 54% | +0.40% |
| momentum | 20 days | 13 | -0.005 | -0.1 | 46% | +1.02% |
| relative_strength | 20 days | 13 | -0.015 | -0.3 | 46% | +0.85% |
| volatility | 20 days | 13 | -0.022 | -0.8 | 31% | -1.86% |
| liquidity | 20 days | 13 | +0.030 | 0.7 | 62% | +1.68% |
| price score (combined) | 20 days | 13 | -0.007 | -0.2 | 46% | +0.90% |

## Live ideas log (5 ideas logged)

Not enough scored ideas yet (0 scored at 5 days; at least 30 needed). The news score can only be judged here, because there is no free news history.

## Suggested price-score weights (NOT applied)

Rule: t ≥ 2 → ×1.25, t ≤ −1 → ×0.5, else unchanged; then scaled to the same total.

| Factor | Current | Suggested | Why |
|---|---|---|---|
| trend | 0.250 | 0.250 | no clear evidence either way |
| momentum | 0.300 | 0.300 | no clear evidence either way |
| relative_strength | 0.200 | 0.200 | no clear evidence either way |
| volatility | 0.100 | 0.100 | no clear evidence either way |
| liquidity | 0.150 | 0.150 | no clear evidence either way |

No change suggested this week.

Final-score mix stays {'price': 0.8, 'news': 0.2} until the live log has at least 30 scored ideas to judge the news score.

*One year of history is a small sample and markets change; treat these as hints, not proof. Rule-based analysis, not financial advice.*
