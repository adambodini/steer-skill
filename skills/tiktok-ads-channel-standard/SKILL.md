---
name: tiktok-ads-channel-standard
description: The TikTok Ads channel standard (Smart+ and manual web conversion campaigns, Spark Ads) across the five pillars, with Basic / Standard / Best in class levels and open tests, used to diagnose an account and score it monthly.
---

# TikTok Ads Channel Standard v0.1.1

Status: draft standard, to be challenged over time. Same five pillars as the Meta playbook. No thresholds fixed yet: every `[ ]` is a blank to calibrate on real clients. Each change gets logged with the evidence behind it.
IP rule: generic principles only. No employer data, no agency proprietary models.

**How to read it**
- **Basic / Standard / Best in class**: the score a channel gets in the monthly state of play.
- **TEST**: this source disagrees with, or bends, a principle in `meta-playbook`. Not a decision. Run it on a client and log the result.
- **OPEN**: not verified. Don't guess; confirm before relying on it.
- Source tags [S1]–[S5] are listed at the end.

**Scope**: TikTok Ads Manager web conversion campaigns (Smart+ and manual), Spark Ads. TikTok Shop / GMV Max and app campaigns out of scope for v0.1.

**Platform context (Oct 2026)**: TikTok is making Smart+ the default way to create campaigns in Ads Manager, merging manual and automated setup into one flow. **OPEN**: confirm what manual controls remain in each client account at audit.

**The one-line difference from Meta**: TikTok's effect looks slower and more off-platform than Meta's, and its creative wears out faster. Most tests below come from those two facts.

---

## 1. Signal: feed the algorithm the truth

Principle: same as Meta. Optimise to the event closest to money, on one clean dataset, and calibrate against reality.

| | Basic | Standard | Best in class |
|---|---|---|---|
| Event setup | Pixel firing on the money event, checked with Pixel Helper | Pixel + Events API, deduplicated with a shared event ID | Pixel + Events API + CRM / offline events passed back; event counts reconciled to backend weekly |
| Data quality | Value and currency on purchase | Event match quality score ≥ `[ ]` | Value-based optimisation on, with value = revenue, margin or predicted LTV |
| Volume | Optimisation event hits `[ ]` / week per ad group | ~50 / week per ad group [S1] | Same, with value variance the model can learn from |
| Reality check | Platform numbers reported as-is | Exit-poll multiplier applied | Calibrated by holdout (geo or Conversion Lift Study), with a post-campaign read window [S3] |

- **TEST (vs "click-based over view-through")**: TikTok cites a TransUnion analysis saying advertisers see 1.4x more conversions with multi-touch attribution than last-touch [S2], and Haus found an extra 68% lift after campaigns ended [S3]. Click-only may undercount TikTok more than Meta. Test: click-only vs click + view vs holdout, per client.
- **TEST (vs "calibrate with the exit poll")**: the effect is delayed and partly off-site (e.g. Amazon). One Haus client saw a 5.11% lift on Amazon sales vs 4.14% on its own site [S3]. Test: does the exit-poll multiplier for TikTok match a holdout read that includes a 1–2 week tail?
- **TEST (vs "event closest to money")**: ~50 conversions per ad group per week is a high bar for small accounts [S1]. Test: purchase vs a higher-volume proxy (add to cart, sign-up) when budget can't feed 50.
- **OPEN**: TikTok's own help page gives both "10 conversions" and "50 conversions" for learning in the same section [S1]. Confirm current guidance.

## 2. Creative: creative is the targeting, and it burns faster

Principle: holds more strongly than on Meta. TikTok hands most targeting to the algorithm, so creative is the main lever. But it must be native to TikTok and replaced faster.

| | Basic | Standard | Best in class |
|---|---|---|---|
| Native fit | Vertical video, sound on | Made for TikTok: creator-led, hook in the first seconds; no straight ports of Meta or YouTube ads [S4] | Creator pipeline + Spark Ads boosting best organic posts [S4] |
| Volume | 3–5 creatives per ad group [S1] | `[ ]` new creatives / month | `[ ]` new / month, diverse concepts (not variants of one idea) [S5] |
| Fatigue | Replaced when results drop | Replaced on signal: hook rate, CTR and CPM vs the ad's own baseline | Refresh pipeline runs ahead of fatigue; queue ranked by spend at risk |
| Testing | None | Sandbox, graduate on a weekly cadence (shared with Meta) | Separate TikTok sandbox; graduation cadence set from observed fatigue speed |

- **TEST (vs "test in a sandbox, graduate on a weekly cadence")**: practitioner benchmarks say refresh every 2–4 weeks on Meta but weekly on TikTok [S5]. A weekly graduation may be too slow if creative half-life is days. Test: twice-weekly vs weekly cadence.
- **TEST (vs one shared creative engine)**: Fospha's TikTok playbook says moving Meta or YouTube creative straight to TikTok rarely works [S4]. Test: ported Meta winners vs TikTok-native concepts. If ports lose, TikTok needs its own lane in the creative engine.
- **OPEN**: the "37% lower CPMs from weekly refresh" claim [S5] comes via a creative vendor's blog; primary data not verified.

## 3. Media buying: density beats cleverness

Principle: same as Meta, and TikTok's own rules enforce it. Fewer ad groups, each fed enough conversions to learn.

| | Basic | Standard | Best in class |
|---|---|---|---|
| Structure | Smart+ for conversions | Ad groups ≤ weekly conversions ÷ 50 [S1] | Same, plus prospecting and retargeting fenced so retargeting doesn't take credit |
| Lanes | Always-on only | Always-on + testing lane with budget cap | Three lanes (always-on, testing, experiments) with caps, shared with Meta |
| Budget | Ad group budget ≥ `[ ]` × target CPA | Budget sized to reach ~50 conversions [S1]; no edits during learning | Budget changes kept within `[ ]`% steps after learning |
| Bidding ladder | Maximum delivery | Cost cap at multiplier-adjusted CPA [S1] | Value-based optimisation on multiplier-adjusted targets |
| Funnel mix | 100% conversion campaigns | `[ ]`% upper funnel | Upper-funnel share set by holdout result |

- **TEST (vs "optimise to money" as the only lane)**: Fospha says top-performing TikTok brands put at least 25% of media budget into upper-funnel campaigns [S4]. Test: conversion-only vs a fixed upper-funnel share, read by holdout.
- **TEST (vs short reads)**: Haus found TikTok lift often stays flat for the first half of a campaign, then accelerates [S3]. Kill rules built for Meta may kill TikTok too early. Test: kill window `[ ]` days on TikTok vs Meta.
- **TEST (TikTok can be zero lift)**: Ritual's first Haus test found TikTok drove no lift; after three buying changes it reached 8% lift [S3]. Default assumption: TikTok's lift is unproven until a holdout shows it, and set-up matters more than spend.
- **OPEN**: TikTok's guidance on how far to move budget and bid after learning (commonly quoted as 50% budget / 20% bid). Only found in third-party copies of the help article; verify.

## 4. Offer: a lever, not a constant

Principle: same as Meta. Test offers like creative; match to the buying trigger.

| | Basic | Standard | Best in class |
|---|---|---|---|
| Offer in ad | Offer on the landing page | Offer stated in the video (voice and on-screen) | Offers tested as creative variables, by concept |
| Offer by funnel | One offer for everyone | Discovery vs conversion audiences see different offers | Offer tuned to the trigger found in exit poll / JTBD research |
| Channel fit | DTC only | Offer consistent across DTC and marketplaces TikTok drives to | Offer tested on where the sale lands (DTC vs Amazon vs Shop) |

- **OPEN**: whether TikTok audiences respond to discount-led offers differently from Meta audiences. No data-led source found.
- **OPEN**: TikTok Shop / GMV Max as an offer channel. Out of scope for v0.1; decide in v0.2.

## 5. Post-click: the channel owner owns the click to the conversion

Principle: same as Meta. Page matches ad; find the rate-limiting step. On TikTok, a big share of the conversion may happen elsewhere later.

| | Basic | Standard | Best in class |
|---|---|---|---|
| Message match | Ad lands on a relevant page | Landing page matches the video's hook and offer | Landing variant per top concept, tested on a cadence |
| In-app browser | Page loads in TikTok's in-app browser | Mobile load time within `[ ]`; checkout works in-app | `[ ]` |
| Rate-limiting step | Conversion rate tracked | Step rates tracked from landing to conversion | Weakest step named and owned each month |
| Off-site conversion | Ignored | Branded search and marketplace sales watched during flights | Off-site effect measured by holdout [S3] |

- **TEST (vs "the channel owner owns click to conversion")**: if a large share of TikTok's effect lands later, via search or Amazon [S3][S4], the TikTok owner doesn't own most of the conversion path. Test: what share of incremental lift lands off the landing page?
- **OPEN**: how TikTok's in-app browser affects checkout conversion vs Meta's. Not verified.

---

## Operating rhythm (TikTok-specific)

- **Twice weekly (TEST)**: creative fatigue check; refresh queue.
- **Weekly**: graduate and kill (shared with Meta); reconcile Events API counts to backend.
- **Monthly**: channel state of play; score each pillar Basic / Standard / Best in class.
- **Quarterly**: structure review; one holdout with a post-flight read window.

## Tests against existing principles (summary)

| # | Meta principle | What TikTok sources say | Test |
|---|---|---|---|
| 1 | Click over view-through | Last-touch undervalues TikTok; delayed lift [S2][S3] | Click vs click+view vs holdout |
| 2 | Calibrate with exit poll | Effect is delayed and off-site [S3] | Exit-poll multiplier vs holdout with tail |
| 3 | Event closest to money | ~50 / week per ad group is a high bar [S1] | Purchase vs proxy event at low volume |
| 4 | Weekly graduation | TikTok refresh benchmark is weekly, fatigue in days [S5] | Twice-weekly vs weekly |
| 5 | One creative engine | Ported Meta creative rarely works [S4] | Ports vs native concepts |
| 6 | Optimise to money only | Top brands put ≥25% in upper funnel [S4] | Fixed upper-funnel share vs none |
| 7 | Kill fast | Lift flat early, then accelerates [S3] | Longer kill window on TikTok |
| 8 | Channel owner owns the conversion | Much of the effect lands off-site [S3][S4] | Share of lift off the landing page |

## Sources

- **[S1] Platform**: TikTok Ads Help, bidding and budget solutions for auction ads (learning phase, budget sizing, cost cap). https://ads.tiktok.com/help/article/bidding-budget-solutions-drive-tiktok-auction-ad-performance
- **[S2] Platform**: TikTok for Business, TransUnion meta-analysis of multi-touch attribution. https://ads.tiktok.com/business/en-US/blog/transunion-meta-analysis-incremental-sales
- **[S3] Data-led / measurement**: Haus, TikTok incrementality experiments (Ritual and Newton Baby case studies; delayed-lift research as reported by eMarketer). https://haus.io/customer/ritual , https://www.haus.io/customer/newton-baby , https://www.emarketer.com/content/tiktok-s-true-ad-impact-slow-burn--incrementality-research-shows
- **[S4] Big-budget operator / measurement**: Fospha, TikTok best-practices playbook and cross-client TikTok data. https://academy.fospha.com/tiktok-best-practices , https://ads.tiktok.com/business/en-US/inspiration/necessaire-full-funnel-measurement
- **[S5] Data-led benchmark**: Billo, creative volume and refresh benchmarks drawing on AppsFlyer and Motion reports. https://billo.app/blog/how-many-ad-creatives-do-you-need/

Note on source quality: S1–S2 are TikTok's own and favour more spend and more credit. S3–S4 sell measurement, and S4's figures appear in TikTok-published case studies. S5 is a creative vendor quoting others' reports. Every source here has a reason to say TikTok is under-measured; the Ritual zero-lift result is the main counterweight. Weigh accordingly.

## Change log
- v0.1.1 (23 Oct 2026): moved into the skills library. References to `meta-playbook-principles` renamed `meta-playbook`; IP line made generic (no employer or agency names). No change to principles, levels or tests.
- v0.1 (23 Oct 2026): first draft. Five pillars mirrored from Meta Playbook v0.1; 8 tests logged; thresholds blank.
