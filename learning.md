# Weekly learning — 2026-11-06

Which factors predicted returns vs QQQ over the following 5 and 20 trading days? **IC** = rank correlation between a factor and the later excess return (+0.05 is useful, 0 is nothing, negative is the wrong way). **Spread** = how much the top 20% of stocks on the factor beat the bottom 20% on average. **t** above 2 means the result was consistent.

## History: price factors, last 12 months (no look-ahead)

| Factor | Horizon | Samples | IC | t | IC > 0 | Top–bottom spread |
|---|---|---|---|---|---|---|
| trend | 5 days | 51 | -0.007 | -0.3 | 41% | -0.04% |
| momentum | 5 days | 51 | -0.016 | -0.6 | 45% | -0.03% |
| relative_strength | 5 days | 51 | -0.019 | -0.7 | 43% | -0.09% |
| volatility | 5 days | 51 | +0.002 | 0.1 | 47% | -0.08% |
| liquidity | 5 days | 51 | -0.004 | -0.2 | 59% | -0.12% |
| price score (combined) | 5 days | 51 | -0.014 | -0.5 | 45% | -0.06% |
| trend | 20 days | 13 | -0.037 | -0.8 | 54% | -0.79% |
| momentum | 20 days | 13 | -0.043 | -0.9 | 38% | -0.82% |
| relative_strength | 20 days | 13 | -0.036 | -0.7 | 38% | +0.05% |
| volatility | 20 days | 13 | +0.007 | 0.2 | 31% | -0.56% |
| liquidity | 20 days | 13 | -0.006 | -0.1 | 54% | -0.07% |
| price score (combined) | 20 days | 13 | -0.041 | -0.8 | 38% | -0.71% |

## Live ideas log (90 ideas logged)

| Factor | Horizon | Ideas | IC |
|---|---|---|---|
| score | 5 days | 70 | -0.104 |
| price_score | 5 days | 70 | +0.250 |
| news_score | 5 days | 70 | -0.345 |
| s_trend | 5 days | 70 | +0.009 |
| s_momentum | 5 days | 70 | +0.093 |
| s_relative_strength | 5 days | 70 | +0.259 |
| s_volatility | 5 days | 70 | +0.076 |
| s_liquidity | 5 days | 70 | +0.000 |
| sentiment | 5 days | 70 | -0.297 |

## Suggested price-score weights (NOT applied)

Rule: t ≥ 2 → ×1.25, t ≤ −1 → ×0.5, else unchanged; then scaled to the same total.

| Factor | Current | Suggested | Why |
|---|---|---|---|
| trend | 0.243 | 0.243 | no clear evidence either way |
| momentum | 0.379 | 0.379 | no clear evidence either way |
| relative_strength | 0.194 | 0.194 | no clear evidence either way |
| volatility | 0.039 | 0.039 | no clear evidence either way |
| liquidity | 0.146 | 0.146 | no clear evidence either way |

No change suggested this week.

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
| 5 days | Claude | 225 | +0.12 |
| 5 days | App (VADER) | 225 | -0.14 |
| 20 days | Claude | 60 | +0.16 |
| 20 days | App (VADER) | 60 | +0.02 |
