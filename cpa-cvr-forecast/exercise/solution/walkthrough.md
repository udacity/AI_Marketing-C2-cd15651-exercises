# Solution — Forecast CPA and CVR, Model the Month

*Worked solution. Numbers computed from the provided `steep_campaign_90day.csv`; a reasonable submission will land close, not identical, depending on method and band width. Artifacts in this folder: [`forecast-cpa-cvr-cpm-30day.csv`](forecast-cpa-cvr-cpm-30day.csv) and [`forecast-chart.png`](forecast-chart.png).*

## 1. Describe the data first (before forecasting)

Three patterns to separate — a fourth is defensible, since CPM drift and CTR erosion are separately significant with different causes, and a learner who splits them is not wrong:

- **Creative fatigue (a trend to carry forward).** CTR erodes across the 90 days, pushing CPA up steadily: daily CPA runs **~$28 in the first 10 days → ~$42 by days 66–75** (just before the spend ramp). This is a genuine trend, not noise.
- **Promo week (a discrete event to exclude).** Days ~40–46 (`notes = "Promo week (20% off sitewide)"`) spike CVR and drop CPA. Leaving it in the trend fit drags the baseline too optimistic — exclude it before fitting.
- **End-of-quarter spend ramp (a different cause).** Days ~76–89 (`notes = "End-of-quarter spend ramp"`) push daily spend up and lift CPM as more expensive inventory is bought. CPA rises here for an *auction-pressure* reason, distinct from fatigue.

## 2. Handle each anomaly

- **Exclude** promo week from the baseline trend fit.
- **Carry forward** the fatigue trend (don't forecast a flat line).
- **Exclude** the ramp from the trend fit for the same reason as promo week — it's a distinct spend-driven cause, not the underlying fatigue signal. CPM will revert if the ramp doesn't repeat.

## 3. 30-day forecast (linear trend on non-promo, non-ramp days; band = mid ± 1 residual σ)

| Metric | Low (avg) | Mid (avg) | High (avg) |
|---|---|---|---|
| **CPA** | ~$46.6 | **~$49.8** | ~$53.1 |
| **CVR** | ~2.8% | **~3.0%** | ~3.2% |
| CPM | ~$13.9 | **~$14.3** | ~$14.7 |

Full day-by-day projection: [`forecast-cpa-cvr-cpm-30day.csv`](forecast-cpa-cvr-cpm-30day.csv). Chart: [`forecast-chart.png`](forecast-chart.png).

**Two methods are acceptable here, and they land in different places.** The table above fits a trend line directly to CPA. The alternative — forecast CPM, CTR and CVR separately, then derive CPA from them — follows the decomposition more literally and lands nearer **~$54**. It is not wrong; on this dataset it is arguably the better read, because it lets each driver move at its own rate instead of averaging them into one slope. **Treat roughly $46–$55 as the acceptable band for a defensible CPA mid, and grade the reasoning, not the number.** What matters is that the learner states which method they used and why. A submission landing at $54 by decomposition is as good as one landing at $50 by direct fit; a submission landing anywhere without naming its method is not.

*What the chart shows: the 90 training days with promo week (squares) and the end-of-quarter ramp (triangles) marked as excluded from the fit, then the 30-day forecast mid and its ±1σ band — CPA in the upper panel, CVR in the lower. Every figure in it appears in the table above, so the chart is a second view rather than the only place the numbers live.*

**CPM is carried here for context only** — the exercise asks for CPA and CVR, and CPA is the anchor. It's included because it explains *why* CPA moves (CPM drift feeds CPC feeds CPA), not because it's a required deliverable. A read-out with only CPA and CVR is complete.

## 4. Assumptions and what drives the spread

- Trend is roughly linear over the horizon; fatigue continues at its recent slope.
- Promo week and the end-of-quarter ramp both excluded from the fit as one-offs; neither is assumed to repeat next month.
- Band = ±1 residual standard deviation from the trend fit — widen it if you expect another creative refresh or budget shift. CPA carries more uncertainty than CVR because it compounds CTR and CPC movement. This is a fixed-width uncertainty band, not a prediction interval — widen it manually if you expect volatility to compound (e.g. a creative refresh mid-month).

## 5. Budget → orders read-out

At a planned **~$30,000/month** spend (recent non-ramp daily spend ≈ $1,000 × 30) and the **mid CPA of ~$50**:

> **~600 orders** next month (≈ $30,000 ÷ $50).
> Range: ~$53.1 CPA → ~565 orders (downside), ~$46.6 CPA → ~644 orders (upside).
>
> Off the decomposed mid instead (~$54.30): **~552 orders**. That sits below the direct-fit downside, which is the honest consequence of the two methods disagreeing — not an error in either. Report the read-out off whichever mid you forecast, and say which.

**Biggest risk:** fatigue accelerating faster than the linear trend assumes — if CPA keeps climbing past the high case, orders fall below the low case. A creative refresh is the lever that resets it.

## Common mistakes

- Forecasting a **flat** CPA (ignoring fatigue) — the single most common error; it over-promises orders.
- Leaving **promo week** in the baseline — makes CVR/CPA look better than they'll be.
- Reporting a **single number** instead of a range.
- Blaming the ramp's CPA rise on fatigue — they're two different causes.
