# Weekly learning — 2026-11-27

Which factors predicted returns vs QQQ over the following 5 and 20 trading days? **IC** = rank correlation between a factor and the later excess return (+0.05 is useful, 0 is nothing, negative is the wrong way). **Spread** = how much the top 20% of stocks on the factor beat the bottom 20% on average. **t** above 2 means the result was consistent.

## History: price factors, last 12 months (no look-ahead)

| Factor | Horizon | Samples | IC | t | IC > 0 | Top–bottom spread |
|---|---|---|---|---|---|---|
| trend | 5 days | 51 | -0.004 | -0.2 | 51% | -0.04% |
| momentum | 5 days | 51 | -0.003 | -0.1 | 47% | +0.04% |
| relative_strength | 5 days | 51 | -0.019 | -0.7 | 51% | -0.24% |
| volatility | 5 days | 51 | -0.008 | -0.4 | 37% | -0.19% |
| liquidity | 5 days | 51 | -0.006 | -0.3 | 53% | +0.01% |
| price score (combined) | 5 days | 51 | -0.009 | -0.3 | 49% | -0.03% |
| trend | 20 days | 13 | -0.032 | -0.8 | 38% | -0.07% |
| momentum | 20 days | 13 | -0.000 | -0.0 | 69% | +0.88% |
| relative_strength | 20 days | 13 | -0.058 | -1.5 | 31% | -0.93% |
| volatility | 20 days | 13 | +0.015 | 0.3 | 46% | -0.62% |
| liquidity | 20 days | 13 | -0.030 | -0.7 | 62% | -0.16% |
| price score (combined) | 20 days | 13 | -0.032 | -0.8 | 38% | +0.22% |

## Live ideas log (155 ideas logged)

| Factor | Horizon | Ideas | IC |
|---|---|---|---|
| score | 5 days | 130 | -0.284 |
| price_score | 5 days | 130 | -0.031 |
| news_score | 5 days | 130 | -0.326 |
| s_trend | 5 days | 130 | +0.020 |
| s_momentum | 5 days | 130 | -0.067 |
| s_relative_strength | 5 days | 130 | -0.155 |
| s_volatility | 5 days | 130 | +0.169 |
| s_liquidity | 5 days | 130 | -0.085 |
| sentiment | 5 days | 130 | -0.086 |
| score | 20 days | 65 | -0.263 |
| price_score | 20 days | 65 | -0.042 |
| news_score | 20 days | 65 | -0.307 |
| s_trend | 20 days | 65 | -0.073 |
| s_momentum | 20 days | 65 | -0.145 |
| s_relative_strength | 20 days | 65 | -0.084 |
| s_volatility | 20 days | 65 | +0.178 |
| s_liquidity | 20 days | 65 | +0.111 |
| sentiment | 20 days | 65 | -0.318 |

## Suggested price-score weights (NOT applied)

Rule: t ≥ 2 → ×1.25, t ≤ −1 → ×0.5, else unchanged; then scaled to the same total.

| Factor | Current | Suggested | Why |
|---|---|---|---|
| trend | 0.243 | 0.269 | no clear evidence either way |
| momentum | 0.379 | 0.419 | no clear evidence either way |
| relative_strength | 0.194 | 0.108 | pointed the wrong way over the last year (t = -1.5) |
| volatility | 0.039 | 0.043 | no clear evidence either way |
| liquidity | 0.146 | 0.161 | no clear evidence either way |

To use them, copy the Suggested column into `config.yaml` → `research.weights`.

Final-score mix stays {'price': 0.8, 'news': 0.2, 'insider': 0.05, 'history': 0.03, 'quality': 0.04} until the live log has at least 30 scored ideas to judge the news score.

*One year of history is a small sample and markets change; treat these as hints, not proof. Rule-based analysis, not financial advice.*

## Automatic weight updates

Monthly, walk-forward (learn on older picks, test on the newest month), applied only if better, each weight moves at most 20% a month, auto-revert if the next month is worse.

- Weights in use: config.yaml baseline (no automatic change yet)
- 2026-11-02: **waiting** — 50 scored picks, need 60
- 2026-10-09: **waiting** — 0 scored picks, need 60

## Claude vs app: headline ratings

Does a stock's headline rating predict its return vs QQQ? Spearman rank correlation (IC) on the same cases (stocks both rated): above 0 = higher ratings were followed by better returns. Report only: weights change only through the monthly self-learning.

| Horizon | Rater | Cases | IC |
|---|---|---|---|
| 5 days | Claude | 360 | +0.04 |
| 5 days | App (VADER) | 360 | -0.06 |
| 20 days | Claude | 180 | +0.11 |
| 20 days | App (VADER) | 180 | -0.18 |
