# Market Regime Detection — Checklist + Scorecard
*Living document | Started 2026-03-17 | Run weekly*

---

## How to use this document

Run the checklist first — it takes 10 minutes. Then score the scorecard. The score tells you which regime you're in. The regime tells you what to do with the book.

**Do not skip to the scorecard.** The checklist forces you to look at actual data. The scorecard is only as good as the inputs.

---

## Part 1 — Weekly Regime Detection Checklist

Run at the start of each week. Fill in the current value and the direction (↑ ↑↑ → ↓ ↓↓).

### Block 1 — Macro / Risk Appetite

| Indicator | Current | Direction | Notes |
|---|---|---|---|
| BTC dominance (%) | | | Rising = risk-off / rotation to BTC; Falling = alt season building |
| BTC 7d price change | | | Proxy for macro risk appetite |
| DXY direction (weekly) | | | USD strengthening = risk-off pressure on crypto |
| US 10y yield direction | | | Rising fast = liquidity drain; Falling = risk-on |
| Citadel / macro positioning signal | | | Track any public macro positioning shifts |

**Block 1 read:** ☐ Risk-on  ☐ Neutral  ☐ Risk-off

---

### Block 2 — Crypto Market Structure

| Indicator | Current | Direction | Source |
|---|---|---|---|
| BTC spot CVD (7d) | | | Buyers vs. sellers in spot — real demand signal |
| Stablecoin inflows to exchanges | | | Leading indicator of retail re-entry |
| Aggregate funding rates (BTC/ETH) | | | Sustained positive = leverage building; Negative = capitulation |
| Exchange BTC reserves (trend) | | | Falling = accumulation; Rising = distribution |
| ETH/BTC ratio direction | | | Rising = risk-on alt rotation; Falling = BTC dominance |

**Block 2 read:** ☐ Accumulation  ☐ Neutral  ☐ Distribution / Risk-off

---

### Block 3 — HYPE Revenue (Core Thesis Health)

| Metric | Current | Prior Week | vs. $40M Floor | vs. $55M Ceiling |
|---|---|---|---|---|
| 30d revenue | | | | |
| 7d revenue (annualised) | | | | |
| TVL direction | | | | |

*Data: `https://api.llama.fi/summary/fees/hyperliquid?dataType=dailyRevenue`*

**HYPE signal:** ☐ Strong (>$55M)  ☐ Hold ($40–55M)  ☐ Warning (<$40M)  ☐ Exit trigger hit

---

### Block 4 — AI Narrative Health

| Signal | Status | Notes |
|---|---|---|
| Capital flowing TO AI tokens (vs. memes / L1s / BTC) | ☐ Yes  ☐ No | Check CT, Kaito, narrative flow |
| RNDR utilisation / fee data trending | ☐ Up  ☐ Flat  ☐ Down | DefiLlama fees |
| VIRTUALS — new agent deployments / ACP activity | ☐ Active  ☐ Flat | |
| Any major AI×crypto integration announced this week | ☐ Yes  ☐ No | Named counterparty required — not blog posts |
| TAO subnet activity (proxy for ecosystem engagement) | ☐ Growing  ☐ Flat  ☐ Declining | |

**AI narrative read:** ☐ Accelerating  ☐ Stable  ☐ Rotating out  ☐ Collapsing

---

### Block 5 — Short Book Health

| Name | Thesis holding? | Squeeze risk? | Upcoming catalyst? | Action |
|---|---|---|---|---|
| TIA | ☐ Yes  ☐ No | ☐ Low  ☐ Med  ☐ High | | |
| APT | ☐ Yes  ☐ No | ☐ Low  ☐ Med  ☐ High | | |
| OP | ☐ Yes  ☐ No | ☐ Low  ☐ Med  ☐ High | | |
| LIT | ☐ Yes  ☐ No | ☐ Low  ☐ Med  ☐ High | | |
| XPL | ☐ Yes  ☐ No | ☐ Low  ☐ Med  ☐ High | | |

**Short squeeze risk:** ☐ Low  ☐ Elevated  ☐ High — reduce

**TIA unlock calendar note:** Track next major unlock date here: ___________

---

### Block 6 — Cash Deployment Decision Tree

Run this only if cash is still at 14%:

```
Is BTC/HYPE down 15–20% from recent high?
  → YES: Deploy 7% into BTC/HYPE (buy the dip tranche)

Are 3+ of the following true?
  - Funding rates negative across majors
  - BTC dominance rising week-on-week
  - Stablecoin inflows reversing
  - HYPE revenue trending below $45M/month
  - Macro shock event (rates spike, regulatory event)
  → YES: Convert 7% to macro hedge (BTC put or ETH short)

Neither condition met → hold cash, reassess next week
```

---

## Part 2 — Regime Scorecard

Score each indicator 1–5. Total determines regime classification.

### Scoring Guide

| Score | Meaning |
|---|---|
| 5 | Strongly bullish signal |
| 4 | Mildly bullish |
| 3 | Neutral |
| 2 | Mildly bearish |
| 1 | Strongly bearish / risk-off |

---

### Scorecard Table

| Indicator | Score (1–5) | Weight | Weighted |
|---|---|---|---|
| BTC dominance direction | | 15% | |
| Funding rates (aggregate) | | 15% | |
| Stablecoin exchange inflows | | 10% | |
| BTC spot CVD (7d) | | 10% | |
| HYPE 30d revenue vs. floor | | 20% | |
| AI narrative flow direction | | 15% | |
| Short squeeze risk (inverted) | | 15% | |
| **Total** | | **100%** | |

---

### Regime Classification

| Score | Regime | Portfolio posture |
|---|---|---|
| 4.0–5.0 | 🟢 **Scenario 1 — Full Bull** | Cut weakest shorts (LIT/XPL first). Let HYPE + AI run. Consider reducing OP/APT. |
| 3.2–3.9 | 🟢 **Scenario 2 — Controlled Bull** | Hold book. This is the designed environment. Monitor weekly, no major changes. |
| 2.5–3.1 | 🟡 **Scenario 6 — Sideways / Choppy** | HYPE core does the work. Let shorts grind. Don't add risk. Deploy cash only on clear dip. |
| 1.8–2.4 | 🔴 **Scenario 3 — Risk-off** | Cover some shorts into panic (take profit). Rotate into BTC + HYPE if revenue holds. Reduce VIRTUALS/TAO first. |
| Any score + AI signals all ☐ Rotating out | 🟡 **Scenario 4 — AI Collapse** | Cut VIRTUALS first, then TAO. Rotate to HYPE. Do not panic-sell RNDR without checking fee data. |
| Score 3.0–4.5 + squeeze risk HIGH | 🔴 **Scenario 5 — Short Squeeze** | Reduce short exposure immediately. Keep only OP + TIA. Do not fight momentum. |

---

### Regime Log

| Date | Score | Regime | Book changes made | Notes |
|---|---|---|---|---|
| 2026-03-17 | — | 🟡 Scenario 6 default | Initial book set | Awaiting data confirmation |
| | | | | |
| | | | | |

---

## Part 3 — Book Adjustment Rules by Regime

### 🟢 Full Bull detected (score 4.0+)
- [ ] Cut LIT and XPL — close or reduce to 3% each
- [ ] Reduce APT to 2.5%
- [ ] Let HYPE drift toward 18–20% through appreciation (do not trim)
- [ ] Add to RNDR if AI narrative is confirmed accelerating
- [ ] Do not add new shorts until regime shifts

### 🟢 Controlled Bull (score 3.2–3.9)
- [ ] Hold book as constructed
- [ ] Weekly checklist only — no structural changes unless a threshold is crossed
- [ ] HYPE revenue check is the primary canary

### 🟡 Sideways (score 2.5–3.1)
- [ ] Hold book — designed for this
- [ ] Monitor NEAR bleed (inflation pressure, no narrative catalyst → trim toward 1.5% if no signal by month 2)
- [ ] Let structural shorts work slowly
- [ ] Do not add to AI sleeve without a named catalyst

### 🔴 Risk-off (score 1.8–2.4)
- [ ] Cover LIT and XPL (highest squeeze risk in panic, take profit)
- [ ] Reduce VIRTUALS to 1% or close — no floor in risk-off
- [ ] Reduce TAO to 1.5% — narrative collapses in risk-off
- [ ] Rotate proceeds to BTC
- [ ] Check HYPE revenue before deciding whether to hold or trim HYPE position
- [ ] Keep OP, APT, TIA shorts — they fall harder than BTC in this scenario

### 🟡 AI Collapse (narrative signal only)
- [ ] Cut VIRTUALS first (most reflexive, steepest drawdown)
- [ ] Trim TAO to 1.5%
- [ ] Check RNDR fee utilisation data before cutting — if real usage is holding, hold the position
- [ ] Trim NEAR to 1.5% (was already optionality — reduce further)
- [ ] Rotate into HYPE (trading activity holds in any market)

### 🔴 Short Squeeze (score 3.0–4.5 + squeeze risk HIGH)
- [ ] Reduce shorts immediately — priority: LIT, XPL, APT
- [ ] Keep OP and TIA only (structural / unlock-driven, less reflexive to squeeze dynamics)
- [ ] Do not add to shorts during squeeze — wait for momentum to exhaust
- [ ] Deploy cash into regime confirmation trade once squeeze peaks

---

## HYPE Position-Sizing Override Rule

*Added after PM stress test 2026-03-17*

If HYPE 30d revenue is confirmed above $55M for two consecutive months:
- Increase HYPE from 14% → 18–22%
- Reduce BTC from 28% → 22–24%

**Rationale:** At current sizing, BTC (28%) is double HYPE (14%) implying BTC beta is higher conviction than the specific HYPE trade. This is inconsistent — HYPE is the highest-conviction specific idea in the book. The override corrects that when revenue confirms the thesis.

---

*Related: [[crypto-tracker]] | [[2026-03-17-crypto-portfolio-framework]] | [[2026-03-17-HYPE-investment-memo]]*
