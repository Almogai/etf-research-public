# Weekly learning — 2026-11-20

Which factors predicted returns vs QQQ over the following 5 and 20 trading days? **IC** = rank correlation between a factor and the later excess return (+0.05 is useful, 0 is nothing, negative is the wrong way). **Spread** = how much the top 20% of stocks on the factor beat the bottom 20% on average. **t** above 2 means the result was consistent.

## History: price factors, last 12 months (no look-ahead)

| Factor | Horizon | Samples | IC | t | IC > 0 | Top–bottom spread |
|---|---|---|---|---|---|---|
| trend | 5 days | 51 | -0.002 | -0.1 | 43% | +0.02% |
| momentum | 5 days | 51 | -0.003 | -0.1 | 47% | +0.12% |
| relative_strength | 5 days | 51 | -0.014 | -0.5 | 43% | -0.03% |
| volatility | 5 days | 51 | -0.004 | -0.2 | 45% | -0.13% |
| liquidity | 5 days | 51 | -0.001 | -0.0 | 61% | -0.09% |
| price score (combined) | 5 days | 51 | -0.006 | -0.2 | 47% | +0.03% |
| trend | 20 days | 13 | -0.011 | -0.2 | 46% | -0.30% |
| momentum | 20 days | 13 | -0.010 | -0.2 | 46% | +0.35% |
| relative_strength | 20 days | 13 | -0.028 | -0.5 | 54% | -0.33% |
| volatility | 20 days | 13 | +0.014 | 0.3 | 54% | -0.56% |
| liquidity | 20 days | 13 | -0.017 | -0.3 | 54% | -0.52% |
| price score (combined) | 20 days | 13 | -0.018 | -0.3 | 46% | -0.50% |

## Live ideas log (135 ideas logged)

| Factor | Horizon | Ideas | IC |
|---|---|---|---|
| score | 5 days | 115 | -0.231 |
| price_score | 5 days | 115 | +0.042 |
| news_score | 5 days | 115 | -0.311 |
| s_trend | 5 days | 115 | +0.003 |
| s_momentum | 5 days | 115 | -0.038 |
| s_relative_strength | 5 days | 115 | -0.091 |
| s_volatility | 5 days | 115 | +0.158 |
| s_liquidity | 5 days | 115 | -0.048 |
| sentiment | 5 days | 115 | -0.123 |
| score | 20 days | 45 | -0.031 |
| price_score | 20 days | 45 | +0.158 |
| news_score | 20 days | 45 | -0.305 |
| s_momentum | 20 days | 45 | -0.291 |
| s_relative_strength | 20 days | 45 | -0.137 |
| s_volatility | 20 days | 45 | +0.426 |
| s_liquidity | 20 days | 45 | +0.223 |
| sentiment | 20 days | 45 | -0.262 |

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
| 5 days | Claude | 330 | +0.08 |
| 5 days | App (VADER) | 330 | -0.06 |
| 20 days | Claude | 150 | +0.05 |
| 20 days | App (VADER) | 150 | -0.18 |
