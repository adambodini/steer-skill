---
name: creator-channel-standard
description: The influencer / creator channel standard (paid creator partnerships and paid amplification of creator content, UK rules) across the five pillars, with Basic / Standard / Best in class levels and open tests, used to diagnose a programme and score it monthly.
---

# Influencer / Creator Channel Standard v0.1.1

Status: draft standard, to be challenged over time. Same five pillars as the Meta playbook, adapted to creator-led distribution. No thresholds fixed yet: every `[ ]` is a blank to calibrate on real clients. Each change gets logged with the evidence behind it.
IP rule: generic principles only. No employer data, no agency proprietary models.

**How to read it**
- **Basic / Standard / Best in class**: the score a channel gets in the monthly state of play.
- **TEST**: this source disagrees with, or bends, a principle in `meta-playbook`. Not a decision. Run it on a client and log the result.
- **OPEN**: not verified. Don't guess; confirm before relying on it.
- Source tags [S1]–[S5] are listed at the end.

**Scope**: paid creator partnerships (flat fee, gifted, affiliate / commission, ambassadors) and the paid amplification of creator content (Meta partnership ads, TikTok Spark Ads, YouTube creator boosts). UK market rules. Out of scope for v0.1: TikTok Shop affiliate programmes, celebrity / talent deals, events.

**How the pillars translate**
| Meta pillar | Creator equivalent |
|---|---|
| Signal | Can you see which creators actually drive customers? |
| Creative | Creators *are* the creative engine; the brief replaces the script |
| Media buying | Creator portfolio (who, how many, how long) + paid amplification |
| Offer | Code, commission and fee structure, and what the audience is offered |
| Post-click | Where the creator's audience lands, and whether it converts |

**The one-line difference from Meta**: most creator influence doesn't click, and the cost is a fee plus rights, not a bid. Most tests below come from those two facts.

---

## 1. Signal: know which creators actually drive customers

Principle: same as Meta, but the clean dataset is harder to get. Optimise rebooking decisions to the event closest to money, and treat every tracked number as a floor.

| | Basic | Standard | Best in class |
|---|---|---|---|
| Tracking | One code or link per creator | Unique code **and** tracked link per creator; codes monitored for leakage | Single-use or rotating codes; links and codes reconciled to backend orders weekly |
| Self-reported | None | Exit poll lists creators / "a creator I follow" as an option | Exit poll names individual creators; answers matched to orders |
| Unit of measure | Views, engagement | New customers and CAC per creator, fees + product + rights included | Payback per creator on 12-month value; rebook / drop decided on it |
| Reality check | Tracked sales reported as-is | Exit-poll multiplier applied to tracked sales | Holdout or geo test on the largest programmes; branded search watched during flights |

- **TEST (vs "click-based attribution over view-through")**: creator influence mostly doesn't click, so link tracking alone undercounts. Codes help, but are also a floor. Test: tracked sales vs exit-poll share vs holdout, per programme.
- **TEST (vs "one clean dataset")**: codes can over-count too. In one Uniqodo campaign, 30% of tracked sales on a generic influencer code came from users who never interacted with the influencer [S5]. Test: share of code redemptions from voucher sites or branded search, before and after moving to unique or single-use codes.
- **OPEN**: right attribution window for creator links. Practitioner advice ranges widely; no data-led source found.
- **OPEN**: whether geo holdouts work for organic creator posts, which can't be geo-fenced. Paid amplification can be; organic probably needs a time-based or synthetic-control design. Not verified.

## 2. Creative: creators are the creative engine

Principle: holds more strongly than on Meta. The creator's identity and audience are part of the creative. The brand writes the brief; the creator writes the ad.

| | Basic | Standard | Best in class |
|---|---|---|---|
| Brief | Product sent with talking points | Brief: one buying trigger, one proof point, must-say / must-not-say; creator's own voice | Briefs written from exit poll / JTBD triggers; hooks tested across creators |
| Rights | Organic post only | Paid usage rights and partnership-ad access in the first contract [S4] | Rights tiered by duration and placement; renewal priced on performance |
| Handle | Content reposted from the brand handle | Run as partnership ads / Spark Ads from the creator's handle [S1][S3] | Same, plus fatigued winners redeployed to new placements [S3] |
| Volume | `[ ]` creator assets / month | `[ ]` tests / month, sized to keep `[ ]` live winners [S3] | Replacement on a schedule, not a reaction [S3] |
| Disclosure | "#ad" or platform label, upfront [S2] | Disclosure written into every contract and brief; checked before amplification | Monthly audit across Stories, Reels, posts; non-compliant posts pulled |

- **TEST (vs "test in a sandbox, graduate on a weekly cadence")**: Agentio's data across 65,000 Meta partnership ads found 45% of eventual winners still looked like losers before $100 of spend, and recommends a ~$1,000 spend floor before the kill call [S3]. A fast weekly kill rule may cut creator winners too early. Test: kill at Meta-standard spend vs a creator spend floor of `[ ]`.
- **TEST (vs "fatigue is predictable")**: Agentio found creator winners fatigue after ~36 days on average, with CPA rising 1.4x if kept past that [S3]. That may be slower than brand creative on TikTok and faster than assumed on Meta. Test: measure each client's own fatigue clock for creator vs brand assets.
- **TEST (vs one creative engine)**: partnership ads beat the same licensed UGC run from the brand handle (+19% CTR, +10% CVR, −5% CPA) [S3]. The handle may matter as much as the asset. Test: same asset, creator handle vs brand handle.
- **OPEN**: Meta's headline claim of 19% lower CPA for partnership ads [S1] is a platform average with no published method. Don't use it for forecasting.

## 3. Media buying: portfolio and amplification

Principle: density still beats cleverness, but here density means fewer creators fed enough to learn from, and paid amplification focused on proven assets.

| | Basic | Standard | Best in class |
|---|---|---|---|
| Portfolio | One-off creators picked by follower count | Creators picked by audience fit and past CAC; repeat bookings for winners | Tiered portfolio: always-on ambassadors, testing pool, experiments; caps per lane |
| Concentration | Spread across many creators | Enough posts per creator to read a result (`[ ]` posts before verdict) | Spend concentrated on creators with proven payback; testing pool sized at `[ ]`% |
| Amplification | Organic only | Best-performing organic posts amplified as partnership ads / Spark Ads | Amplification lane run inside the paid playbook (same lanes, bidding ladder, multiplier-adjusted targets) |
| Cost model | Flat fee per post | Fee + rights + product cost counted as CAC | Hybrid fee + commission; rates benchmarked; rights renewed on performance [S4] |

- **TEST (vs "density beats cleverness")**: on paid media, density means fewer ad sets. With creators, it may mean fewer creators booked repeatedly, but audiences saturate. Test: repeat-booked ambassadors vs a rotating pool of new creators, CAC by post number.
- **TEST (vs "bidding earns its way up")**: creator fees are negotiated, not bid. There's no ladder for the organic post itself; the ladder only applies to amplification. Test: total CAC (fee + amplification) vs organic-only CAC per creator.
- **OPEN**: usage-rights and whitelisting premiums. 2026 creator-platform benchmarks quote these as a percentage on top of the base fee [S4], but they are US-led and survey-based; UK rates not verified.

## 4. Offer: a lever, not a constant

Principle: same as Meta. Test offers like creative; match to the buying trigger. On creators, the offer is also the tracking device, so it has two jobs.

| | Basic | Standard | Best in class |
|---|---|---|---|
| Audience offer | Same discount for every creator | Offer matched to the creator's audience and the buying trigger | Offers tested across creators like creative variables |
| Code economics | Discount code with no margin check | Discount cost counted in CAC; leakage checked | Single-use codes or no-discount tracking codes where the discount isn't needed to convert [S5] |
| Creator terms | Flat fee | Fee + commission for proven creators | Terms tiered by payback; commission on new customers only |
| Compliance | Affiliate links and codes labelled as ads [S2] | Same, written into contracts | Same, audited monthly |

- **TEST (vs "offer is a lever")**: a discount on a creator code may buy tracking rather than conversion. Test: discount code vs no-discount code (same creator, different posts or audiences): CVR, CAC and margin.
- **OPEN**: whether commission-only creators drive new customers or mostly capture existing demand. The affiliate incrementality evidence found is single-case; not verified for creators.

## 5. Post-click: the channel owner owns the click to the conversion

Principle: same as Meta. The page matches the creator's message; find the rate-limiting step. On creators, much of the conversion arrives later via search or direct.

| | Basic | Standard | Best in class |
|---|---|---|---|
| Message match | Link to homepage | Landing page matches the creator's hook and offer | Creator-specific landing pages (their face, words, code pre-applied) for top creators |
| Code journey | Code entered manually at checkout | Code auto-applied from the link | Same, plus code still works for delayed buyers who come back via search |
| Rate-limiting step | Conversion rate tracked | Step rates tracked from creator landing to conversion | Weakest step named and owned each month |
| Off-site conversion | Ignored | Branded search watched during and after flights | Off-site effect measured by holdout on the largest programmes |

- **TEST (vs "the channel owner owns click to conversion")**: if most creator influence lands later via branded search or direct, the creator channel owner doesn't own most of the path, and paid search may take the credit. Test: branded search volume and paid-search conversions in weeks with vs without big creator posts.
- **OPEN**: conversion impact of creator-specific landing pages vs a matched standard page. No data-led source found.

---

## Operating rhythm (creator-specific)

- **Weekly**: amplification graduate and kill (shared with Meta / TikTok, with the creator spend floor from TEST 3); code leakage check; disclosure check on new posts.
- **Monthly**: channel state of play; score each pillar Basic / Standard / Best in class; rebook / drop decisions on payback per creator.
- **Quarterly**: portfolio review (tiers, lanes, rates, rights renewals); one holdout or geo test on the largest programme.

## Tests against existing principles (summary)

| # | Meta principle | What creator sources say | Test |
|---|---|---|---|
| 1 | Click over view-through | Creator influence mostly doesn't click | Tracked sales vs exit poll vs holdout |
| 2 | One clean dataset | Codes also over-count via leakage [S5] | Leakage share before/after unique codes |
| 3 | Weekly graduation / kill fast | 45% of winners look like losers before $100 [S3] | Creator spend floor before kill |
| 4 | Fatigue is predictable | Creator winners fatigue ~36 days [S3] | Client's own creator fatigue clock |
| 5 | One creative engine | Creator handle beats brand handle on same asset [S3] | Same asset, two handles |
| 6 | Density beats cleverness | Density = repeat creators, but audiences saturate | Ambassadors vs rotating pool |
| 7 | Bidding earns its way up | Fees are negotiated, not bid | Total CAC vs organic-only CAC |
| 8 | Offer is a lever | Discount may buy tracking, not conversion | Discount vs no-discount code |
| 9 | Channel owner owns conversion | Influence lands later via search / direct | Branded search with vs without posts |

## Sources

- **[S1] Platform**: Meta partnership ads update and performance claims, as reported by eMarketer. https://www.emarketer.com/content/meta-expands-partnership-ads-turn-creator-content-performance
- **[S2] Regulator**: ASA / CAP and CMA influencer disclosure guidance and the ASA's consumer research, summarised by RPC. https://www.rpclegal.com/snapshots/advertising-and-marketing/winter-2025/cma-and-asa-publish-updated-influencer-guidance-on-social-media-endorsements/ , https://www.asa.org.uk/resource/labelling-of-influencer-advertising.html
- **[S3] Data-led / big-budget operator**: Agentio, analysis of $130M spend across 65,000 Meta partnership ads (Aug 2026). https://www.agentio.com/blog/infinite-creative-engine
- **[S4] Data-led benchmark**: Aspire, State of Influencer Marketing 2026 (platform data + ~900 marketers and creators); Later, influencer pricing benchmarks 2026. https://www.aspire.io/guides/the-state-of-influencer-marketing-2026 , https://later.com/blog/influencer-pricing-benchmarks-the-complete-2026-guide/
- **[S5] Data-led / measurement**: Uniqodo, code leakage in influencer and affiliate tracking. https://www.uniqodo.com/post/the-future-of-affiliate-tracking

Note on source quality: S1 is Meta's own claim, unaudited. S3, S4 and S5 sell creator or code tooling and benefit from "creators work, but you need our system". S2 is the regulator and the only neutral source; its rules are mandatory, not tests. No independent holdout evidence on creator incrementality was found for v0.1; that is the biggest gap. Weigh accordingly.

## Change log
- v0.1.1 (23 Oct 2026): moved into the skills library. References to `meta-playbook-principles` renamed `meta-playbook`; IP line made generic (no employer or agency names). No change to principles, levels or tests.
- v0.1 (23 Oct 2026): first draft. Five pillars adapted from Meta Playbook v0.1 to creator-led distribution; 9 tests logged; thresholds blank.
