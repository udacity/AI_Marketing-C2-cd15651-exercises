# Solution — Forecast CPA and CVR, Model the Month

*Worked solution. Numbers computed from the provided `steep_campaign_90day.csv`; a reasonable submission will land close, not identical, depending on method and band width. Artifacts in this folder: [`forecast-cpa-cvr-cpm-30day.csv`](forecast-cpa-cvr-cpm-30day.csv) and [`forecast-chart.png`](forecast-chart.png).*

## 1. Describe the data first (before forecasting)

Three patterns to separate:

- **Creative fatigue (a trend to carry forward).** CTR erodes across the 90 days, pushing CPA up steadily: daily CPA runs **~$28 in the first 10 days → ~$42 by days 66–75** (just before the spend ramp). This is a genuine trend, not noise.
- **Promo week (a discrete event to exclude).** Days ~40–46 (`notes = "Promo week (20% off sitewide)"`) spike CVR and drop CPA. Leaving it in the trend fit drags the baseline too optimistic — exclude it before fitting.
- **End-of-quarter spend ramp (a different cause).** Days ~76–89 (`notes = "End-of-quarter spend ramp"`) push daily spend up and lift CPM as more expensive inventory is bought. CPA rises here for an *auction-pressure* reason, distinct from fatigue.

## 2. Handle each anomaly

- **Exclude** promo week from the baseline trend fit.
- **Carry forward** the fatigue trend (don't forecast a flat line).
- **Exclude** the ramp from the trend fit for the same reason as promo week — it's a distinct spend-driven cause, not the underlying fatigue signal. CPM will revert if the ramp doesn't repeat.

## 3. 30-day forecast (linear trend on non-promo days; band = mid ± 1 residual σ)

| Metric | Low (avg) | Mid (avg) | High (avg) |
|---|---|---|---|
| **CPA** | ~$46.6 | **~$49.8** | ~$53.1 |
| **CVR** | ~2.8% | **~3.0%** | ~3.2% |
| CPM | ~$13.9 | **~$14.3** | ~$14.7 |

Full day-by-day projection: [`forecast-cpa-cvr-cpm-30day.csv`](forecast-cpa-cvr-cpm-30day.csv). Chart: [`forecast-chart.png`](forecast-chart.png).

## 4. Assumptions and what drives the spread

- Trend is roughly linear over the horizon; fatigue continues at its recent slope.
- Promo excluded as a one-off; no comparable promo assumed next month.
- Band = ±1 residual standard deviation from the trend fit — widen it if you expect another creative refresh or budget shift. CPA carries more uncertainty than CVR because it compounds CTR and CPC movement. This is a fixed-width uncertainty band, not a prediction interval — widen it manually if you expect volatility to compound (e.g. a creative refresh mid-month).

## 5. Budget → orders read-out

At a planned **~$30,000/month** spend (recent non-ramp daily spend ≈ $1,000 × 30) and the **mid CPA of ~$50**:

> **~600 orders** next month (≈ $30,000 ÷ $50).
> Range: ~$53.1 CPA → ~565 orders (downside), ~$46.6 CPA → ~644 orders (upside).

**Biggest risk:** fatigue accelerating faster than the linear trend assumes — if CPA keeps climbing past $54, orders fall below the low case. A creative refresh is the lever that resets it.

## Common mistakes

- Forecasting a **flat** CPA (ignoring fatigue) — the single most common error; it over-promises orders.
- Leaving **promo week** in the baseline — makes CVR/CPA look better than they'll be.
- Reporting a **single number** instead of a range.
- Blaming the ramp's CPA rise on fatigue — they're two different causes.
