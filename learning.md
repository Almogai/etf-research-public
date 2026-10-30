# Weekly learning — 2026-10-30

Which factors predicted returns vs QQQ over the following 5 and 20 trading days? **IC** = rank correlation between a factor and the later excess return (+0.05 is useful, 0 is nothing, negative is the wrong way). **Spread** = how much the top 20% of stocks on the factor beat the bottom 20% on average. **t** above 2 means the result was consistent.

## History: price factors, last 12 months (no look-ahead)

| Factor | Horizon | Samples | IC | t | IC > 0 | Top–bottom spread |
|---|---|---|---|---|---|---|
| trend | 5 days | 51 | -0.000 | -0.0 | 43% | +0.03% |
| momentum | 5 days | 51 | -0.011 | -0.4 | 45% | +0.06% |
| relative_strength | 5 days | 51 | -0.012 | -0.4 | 45% | +0.01% |
| volatility | 5 days | 51 | -0.004 | -0.2 | 45% | -0.21% |
| liquidity | 5 days | 51 | +0.006 | 0.3 | 61% | +0.09% |
| price score (combined) | 5 days | 51 | -0.007 | -0.2 | 47% | +0.05% |
| trend | 20 days | 13 | -0.038 | -0.9 | 54% | -0.66% |
| momentum | 20 days | 13 | -0.030 | -0.7 | 54% | -0.25% |
| relative_strength | 20 days | 13 | -0.051 | -1.1 | 46% | -0.41% |
| volatility | 20 days | 13 | +0.009 | 0.2 | 54% | -0.97% |
| liquidity | 20 days | 13 | -0.007 | -0.2 | 38% | +0.72% |
| price score (combined) | 20 days | 13 | -0.041 | -0.9 | 54% | -0.14% |

## Live ideas log (70 ideas logged)

| Factor | Horizon | Ideas | IC |
|---|---|---|---|
| score | 5 days | 45 | -0.045 |
| price_score | 5 days | 45 | +0.393 |
| news_score | 5 days | 45 | -0.490 |
| s_momentum | 5 days | 45 | -0.157 |
| s_relative_strength | 5 days | 45 | +0.204 |
| s_volatility | 5 days | 45 | +0.364 |
| s_liquidity | 5 days | 45 | -0.098 |
| sentiment | 5 days | 45 | -0.377 |

## Suggested price-score weights (NOT applied)

Rule: t ≥ 2 → ×1.25, t ≤ −1 → ×0.5, else unchanged; then scaled to the same total.

| Factor | Current | Suggested | Why |
|---|---|---|---|
| trend | 0.243 | 0.269 | no clear evidence either way |
| momentum | 0.379 | 0.419 | no clear evidence either way |
| relative_strength | 0.194 | 0.108 | pointed the wrong way over the last year (t = -1.1) |
| volatility | 0.039 | 0.043 | no clear evidence either way |
| liquidity | 0.146 | 0.161 | no clear evidence either way |

To use them, copy the Suggested column into `config.yaml` → `research.weights`.

Final-score mix stays {'price': 0.8, 'news': 0.2, 'insider': 0.05, 'history': 0.03, 'quality': 0.04} until the live log has at least 30 scored ideas to judge the news score.

*One year of history is a small sample and markets change; treat these as hints, not proof. Rule-based analysis, not financial advice.*

## Automatic weight updates

Monthly, walk-forward (learn on older picks, test on the newest month), applied only if better, each weight moves at most 20% a month, auto-revert if the next month is worse.

- Weights in use: config.yaml baseline (no automatic change yet)
- 2026-10-09: **waiting** — 0 scored picks, need 60

## Claude vs app: headline ratings

Does a stock's headline rating predict its return vs QQQ? Spearman rank correlation (IC) on the same cases (stocks both rated): above 0 = higher ratings were followed by better returns. Report only: weights change only through the monthly self-learning.

| Horizon | Rater | Cases | IC |
|---|---|---|---|
| 5 days | Claude | 120 | +0.16 |
| 5 days | App (VADER) | 120 | -0.09 |
| 20 days | Claude | 0 | n/a |
| 20 days | App (VADER) | 0 | n/a |

Fewer than 20 cases: too early to trust these numbers.
