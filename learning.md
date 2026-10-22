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
| price score (combined) | 5 days | 51 | +0.003 | 0.1 | 49% | +0.22% |
| trend | 20 days | 13 | -0.012 | -0.3 | 54% | +0.40% |
| momentum | 20 days | 13 | -0.005 | -0.1 | 46% | +1.02% |
| relative_strength | 20 days | 13 | -0.015 | -0.3 | 46% | +0.86% |
| volatility | 20 days | 13 | -0.022 | -0.8 | 31% | -1.86% |
| liquidity | 20 days | 13 | +0.030 | 0.7 | 62% | +1.68% |
| price score (combined) | 20 days | 13 | -0.006 | -0.1 | 46% | +0.93% |

## Live ideas log (5 ideas logged)

Not enough scored ideas yet (0 scored at 5 days; at least 30 needed). The news score can only be judged here, because there is no free news history.

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
- 2026-10-09: **waiting** — 0 scored picks, need 60

## Claude vs app: headline ratings

Does a stock's headline rating predict its return vs QQQ? Spearman rank correlation (IC) on the same cases (stocks both rated): above 0 = higher ratings were followed by better returns. Report only: weights change only through the monthly self-learning.

| Horizon | Rater | Cases | IC |
|---|---|---|---|
| 5 days | Claude | 75 | +0.32 |
| 5 days | App (VADER) | 75 | -0.03 |
| 20 days | Claude | 0 | n/a |
| 20 days | App (VADER) | 0 | n/a |

Fewer than 20 cases: too early to trust these numbers.
