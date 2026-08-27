# Solution — Forecast LTV, Compare Cohorts, Build the Value Signal

*Worked solution. LTV modelled from `steep_cohorts.csv` with a churn-hazard method (below). Artifacts: [`ltv-by-acqtype.csv`](ltv-by-acqtype.csv), [`ltv-by-geo.csv`](ltv-by-geo.csv), [`bidding-signal-upload.csv`](bidding-signal-upload.csv), [`ltv-driver-chart.png`](ltv-driver-chart.png), and the allocation note [`allocation-note.md`](allocation-note.md).*

## Method (stated assumption)

Revenue-to-date understates value because most customers are still active (right-censored) — younger cohorts especially. So don't average revenue-to-date. Instead:

- **Monthly churn hazard** = churned ÷ total observed customer-months (per segment).
- **Expected lifetime** = 1 ÷ hazard (geometric).
- **Predicted LTV** = average monthly fee × expected lifetime.

## 1. LTV by acquisition type — the real driver

| Segment | n | Monthly churn | Exp. lifetime | LTV | CAC | LTV:CAC |
|---|---|---|---|---|---|---|
| **full_price** | 622 | 3.4%/mo | ~29.6 mo | **~$447** | ~$19 | ~23× |
| **discount** | 578 | 14.9%/mo | ~6.7 mo | **~$96** | ~$20 | ~5× |

Full-price customers are worth **~4.7× more** than discount-acquired ones. Discount customers churn fast and barely pay back beyond their acquisition cost.

## 2. The geography trap (a confound)

Raw LTV by geo *looks* like geography decides value:

| geo | LTV (raw) | % discount-acquired |
|---|---|---|
| CA | ~$213 | 25% |
| US | ~$204 | 41% |
| UK | ~$191 | 47% |
| **IN** | **~$112** | **79%** |

IN looks like the worst market. But split LTV **within** acquisition type and geography nearly flattens:

| geo | discount LTV | full_price LTV |
|---|---|---|
| CA | ~$85 | ~$376 |
| IN | ~$92 | ~$407 |
| UK | ~$107 | ~$488 |
| US | ~$99 | ~$547 |

An IN full-price customer (~$407) is worth about the same as a CA one (~$376). **IN only looks low-value because 79% of its customers were acquired on discount, vs. 25% in CA.** Geography is a confound; **acquisition type is the driver.** (income band is a weaker secondary confound — discount skews slightly lower-income.) See [`ltv-driver-chart.png`](ltv-driver-chart.png).

## 3. The value signal (for the platform)

A representative bidding-signal upload (segment + predicted value + tier) is in [`bidding-signal-upload.csv`](bidding-signal-upload.csv), tiered high / mid / low by predicted LTV. Format is generic (`segment, predicted_ltv, value_tier`) on purpose — real platform field specs change often; teach the concept, not this week's schema.

## 4. The human call

The allocation note is in [`allocation-note.md`](allocation-note.md). Headline: bid **up** on full-price-acquiring channels/geos, bid **down** on discount-acquisition — including **inside** IN, rather than cutting IN wholesale.

## 5. Limits

- Young cohorts carry the most forecast risk (least observed tenure); the hazard estimate is thinnest there.
- These LTV forecasts should be **validated against held-out cohorts over time** — its own discipline.
- This is cohort value analysis, not audience/persona research — the "who they are as people" is a separate question.

## Common mistakes

- Using **average revenue-to-date** as LTV — badly under-values active/young cohorts (the censoring trap).
- Stopping at **"cut India"** — the headline read, and wrong; it's an acquisition-mix artifact.
- Shipping only the signal file **or** only the allocation note — the deliverable is both.
