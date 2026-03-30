# Alpha Gathering Process — Documentation
*Started 2026-03-23 | Living document*

---

## Overview

Daily alpha synthesis pulling from Telegram signal groups via MCP, processed and written to Obsidian as a dated daily note. The goal is a 10-minute read each morning that replaces hours of tab-switching across channels.

Output format: `Alpha Reports/YYYY-MM-DD-daily-alpha.md`

---

## Step 1 — Pull Channel List

Run `mcp__telegram__list_chats` to get the full channel list with unread counts and last-active timestamps. Used to identify which channels have had meaningful activity in the target window.

```
tool: mcp__telegram__list_chats
params: { type_filter: "all" }
```

---

## Step 2 — Pull High-Signal Channels

Run `mcp__telegram__get_multi_chat_messages` across the core watchlist. Split into two batches if needed (tool handles comma-separated chat names).

**Batch 1 — Primary alpha channels:**
```
chats: Grand Exchange v8, 1000x (NDA), Crypto Narratives, Lookonchain,
       Shoal Research Hub, LinXBT's Financial Advice Channel, QCP Broadcast,
       Olimpio Alpha, Monitoring The Situation, infinityhedge
days_back: 1
limit_per_chat: 50
```

**Batch 2 — News and secondary channels:**
```
chats: C4, Cookie Reads 🍪, The Block News Feed, Wu Blockchain News,
       unfolded., Tree News, Grand Exchange v8 Chat
days_back: 1
limit_per_chat: 30
```

**Supplementary — on-demand:**
- `Yield Hunting` — personal bookmarking / reference channel, pull weekly not daily
- `Greeks.live Official Chat room` — options flow, pull when vol events are happening
- `Paradigm - Institutional Liquidity Network` — institutional options flow, pull when macro is moving
- `GSR Market Commentary` — market maker view, pull weekly
- `Paradigm Edge` — research, pull weekly
- `Shoal Research Hub` — already in Batch 1 daily

---

## Step 3 — Synthesise

Write the daily note covering the following sections. Not all sections are needed every day — only include what has genuine signal.

### Section template

```
# Daily Alpha Summary — YYYY-MM-DD

## Dominant Theme
[What was the single biggest driver of price action / narrative today]

## Crypto Market Snapshot
[BTC, ETH, key large cap moves with context — not just price, why]

## ETF Flows
[BTC/ETH/SOL ETF daily and weekly flows from Lookonchain or Wu Blockchain]

## [Asset name] — Position Update
[Any update relevant to current book positions — HYPE, BTC, AI sleeve]

## Book-Relevant: [Catalyst/Event]
[Anything with direct implication for current positions or theses]

## Regulatory
[Any SEC, CFTC, legislative, enforcement developments]

## Exploits / Risk
[Protocol exploits, contagion risk, anything that changes DeFi risk landscape]

## Narratives Worth Watching
[Emerging themes, rotation signals, new projects worth tracking]

## Geopolitical Tail Risk Monitor
[Table: Risk | Status | Book implication — update only when active]

## Key Numbers to Track This Week
[Specific metrics to check in next 7 days]
```

---

## Channel Tier List

Ranked by signal-to-noise ratio based on experience. Update as channels degrade or new ones are added.

### Tier 1 — Pull daily
| Channel | Signal type | Notes |
|---|---|---|
| Grand Exchange v8 | Macro/geopolitical, trade ideas | Small group, directional macro views |
| Monitoring The Situation | Geopolitical real-time | Best for Middle East / macro tail risk |
| Lookonchain | On-chain flows, whale tracking | Whale wallet moves, ETF flows |
| 1000x (NDA) | Cross-asset macro discussion | Small group, high conviction commentary |
| Shoal Research Hub | Research rollups, project updates | Clean daily rollup format |
| LinXBT | TA + directional commentary | Specific levels on major assets |
| The Block News Feed | News | Factual, fast |
| Wu Blockchain News | News + data | Good unlock calendar, ETF flow data |
| infinityhedge | Breaking macro headlines | Rapid-fire, good for geopolitical breaks |

### Tier 2 — Pull 2-3x per week
| Channel | Signal type | Notes |
|---|---|---|
| Cookie Reads | Curated links, reads | Good secondary sources |
| Crypto Narratives | Narrative rotation signals | Useful for identifying what's rotating |
| C4 | Project launches, news rollup | Good for new project discovery |
| unfolded. | News with AI commentary | Clean format |
| Tree News | Breaking headlines | Fast but thin |
| Grand Exchange v8 Chat | Community discussion | More noise than main channel |

### Tier 3 — Pull weekly or on-demand
| Channel | Signal type | Trigger |
|---|---|---|
| Yield Hunting | Personal bookmarking | Weekly review |
| Greeks.live Chat | Options flow discussion | When vol events / options expiry |
| Paradigm (Institutional) | Institutional options flow | When macro is moving |
| GSR Market Commentary | Market maker commentary | Weekly |
| Paradigm Edge | Research | Weekly |
| QCP Broadcast | Options/vol commentary | When BTC vol elevated |
| Olimpio Alpha | Alpha | When active |
| Shoal Research Hub | Already Tier 1 | — |

### Not worth pulling regularly
| Channel | Reason |
|---|---|
| Binance Futures Liquidations | 100k+ unread, pure noise |
| Trench Alpha | Degen memecoin focus |
| Whale Alert | Too noisy, mostly irrelevant wallet alerts |
| SOYLANA MANLETS | Meme/noise |
| Unibot Chat | Bot/trading noise |

---

## Yield Hunting — Personal Reference Channel

This is a personal bookmarking channel (messages sent to self). Pull weekly, not daily. Contains:
- Links to reads worth reviewing
- Job applications (track these separately)
- STRC/Strategy tracking data
- Research papers bookmarked mid-session
- Personal notes/thoughts sent to self

**Pattern:** When a link appears here without commentary it was bookmarked quickly. When there's commentary it was worth reading properly.

---

## Weekly Supplement — Channels to Add

On Sunday or Monday, pull the following for the weekly picture:
- `GSR Market Commentary` — market maker weekly view
- `Paradigm Edge` — research digest
- `QCP Broadcast` — options market weekly positioning
- `Yield Hunting` — personal bookmarks from the week

---

## Unlock Calendar Integration

Pull from **Wu Blockchain News** weekly for the unlock calendar. Format flagged in daily note under "Book-Relevant" when any current short position has an upcoming cliff unlock.

Current short positions to watch:
- XPL (Plasma) — cliff unlocks flagged weekly
- LIT (Lighter) — cliff unlocks flagged weekly
- TIA (Celestia) — known unlock schedule, calendar maintained in `crypto-tracker.md`
- APT (Aptos) — VC vest schedule
- OP (Optimism) — foundation/ecosystem grant distributions

---

## Automation Path (Future)

The manual version of this process (pull → read → synthesise) takes ~30 minutes. The automated version using `tg-signal-monitor` (at `lab/tg-signal-monitor/`) runs Claude analysis on every message in real-time and logs to `signal_log.jsonl`.

The daily note can eventually be generated automatically from that log rather than pulling and reading raw channel data manually. Not yet implemented — the manual process produces better synthesis quality and catches context that the per-message classifier misses.

**To build:** A daily digest script that reads `signal_log.jsonl`, filters to the current date, groups by signal_type, and drafts the daily note structure. Would run each morning as a cron job.

---

## File Naming Convention

```
Alpha Reports/YYYY-MM-DD-daily-alpha.md
```

Weekly supplements (if needed):
```
Alpha Reports/YYYY-WXX-weekly-alpha.md
```

---

## Related Documents

- [[crypto-tracker]] — live position tracker, updated weekly
- [[regime-detection]] — weekly regime scorecard, run alongside daily alpha
- [[crypto-price-factors]] — master factor list for contextualising signals
- [[2026-03-17-crypto-portfolio-framework]] — portfolio rules and structure

---

*Process established: 2026-03-23*
