---
name: google-ads-channel-standard
description: The Google Ads channel standard (Search, AI Max, Shopping, Performance Max, Demand Gen / YouTube) across the five pillars, with Basic / Standard / Best in class levels and open tests, used to diagnose an account and score it monthly.
---

# Google Ads Channel Standard v0.1.1

Status: draft standard, to be challenged over time. Same five pillars as the Meta playbook. No thresholds fixed yet: every `[ ]` is a blank to calibrate on real clients. Each change gets logged with the evidence behind it.
IP rule: generic principles only. No employer data, no agency proprietary models.

**How to read it**
- **Basic / Standard / Best in class**: the score a channel gets in the monthly state of play.
- **TEST**: this source disagrees with, or bends, a principle in `meta-playbook`. Not a decision. Run it on a client and log the result.
- **OPEN**: not verified. Don't guess; confirm before relying on it.
- Source tags [S1]–[S5] are listed at the end.

**Scope**: Search (including AI Max), Shopping, Performance Max (PMax), Demand Gen / YouTube. App campaigns out of scope for v0.1.

**Platform context (Oct 2026)**: Google is pushing Search toward AI Max. Campaign-level broad match and automatically created assets began auto-migrating to AI Max on 1 Sep 2026; the Dynamic Search Ads migration was pushed to Feb 2027. **OPEN**: confirm status in each client account at audit.

---

## 1. Signal: feed the algorithm the truth

Principle: same as Meta. Optimise to the event closest to money, on one clean dataset, and calibrate against reality.

| | Basic | Standard | Best in class |
|---|---|---|---|
| Conversion goal | One primary conversion, firing correctly | Primary goal is the money event; micro-conversions set to secondary (observe only) | Bidding on value (revenue, margin or predicted LTV), not count |
| Data quality | Google tag + GA4 linked | Enhanced conversions on; consent mode set up; no zero-value conversions in value bidding [S1] | Offline / CRM conversions imported (enhanced conversions for leads); conversion value rules for high-value customer types [S1] |
| Volume | Primary goal hits `[ ]` conversions / 30 days per campaign | Hits `[ ]` / 30 days | Hits `[ ]` / 30 days with value variance the model can learn from |
| Reality check | Platform numbers reported as-is | Platform numbers adjusted by exit-poll multiplier | Brand and non-brand calibrated separately; at least one holdout test run per year [S5] |

- **TEST (vs "optimise to the event closest to money")**: Google advises bidding on a funnel stage with a short conversion delay and at least 15 monthly conversions [S1]. For long sales cycles that may be one step before money. Test: money event vs nearest high-volume proxy.
- **TEST (vs "click-based over view-through")**: Google says a large share of YouTube / Demand Gen conversions come via engaged views, not clicks [S2]. Test whether engaged-view conversions survive the exit poll and holdout before counting them.
- **OPEN**: does Google's data-driven attribution window need to match the Meta click window for fair cross-channel comparison?

## 2. Creative: on Google, intent is the targeting

Principle: on Search, the query does the targeting and creative's job is to match it. On PMax / Demand Gen / YouTube, creative does the targeting, as on Meta. On Shopping, the feed is the creative.

| | Basic | Standard | Best in class |
|---|---|---|---|
| Search ads | RSAs live, Ad Strength ≥ Good | Headlines map to query themes; messaging matches landing page | Query themes refreshed from search-terms report every `[ ]` weeks |
| Feed (Shopping / PMax) | Merchant Center feed approved, no critical errors | Titles, images, GTINs and attributes optimised for search intent | Feed segmented by margin / stock / performance tier; feed tested like creative |
| Visual assets (PMax / Demand Gen) | Minimum asset set filled | Full set across formats: vertical, square and horizontal video [S2] | Weekly creative cadence, shared with Meta's sandbox; low-rated assets replaced on a fixed cadence |
| Testing | None | Asset testing within PMax (feed-only vs feed + assets) | Graduation rules shared with Meta playbook |

- **TEST (vs "creative is the targeting")**: in Optmyzr's study, text-only PMax posted the best overall metrics, and adding audience signals and search themes was flat or worse [S3]. Creative may matter less here than on Meta. Test: feed-only vs full-asset PMax per client.
- **TEST (vs "volume scales with spend")**: on Search, more ads don't buy more reach; budget and keyword/query coverage do. Creative volume rule may only apply to Demand Gen / YouTube / PMax visual assets.
- **OPEN**: is creative fatigue predictable on Search the way it is on Meta? No source found.

## 3. Media buying: density beats cleverness, with fences

Principle: consolidate so each campaign learns, but fence off brand and expansion traffic so the algorithm can't take credit for demand you already own.

| | Basic | Standard | Best in class |
|---|---|---|---|
| Structure | Brand and non-brand in separate campaigns | Brand exclusions on PMax; Search partners off; campaigns only split by goal, target or budget | Each campaign hits its conversion threshold; ad groups below `[ ]` conversions / 30 days merged [S2] |
| Lanes | Always-on only | Always-on + testing lane with a budget cap | Three lanes (always-on, testing, experiments) with caps, shared with Meta |
| Bidding ladder | Max conversions | Target CPA, then Max conversion value | Target ROAS on value, set from multiplier-adjusted targets [S1] |
| Expansion (AI Max, broad, PMax) | On by default, unwatched | Search-terms reviewed every `[ ]` weeks; negatives and brand exclusions applied | Expansion run as a measured layer with its own ROAS read, not blended into core [S4] |
| Brand | Brand spend reported as performance | Brand reported separately from acquisition | Brand incrementality tested by geo holdout; spend set from the result [S5] |

- **TEST (vs "consolidate")**: Optmyzr found accounts putting more than half their budget into PMax got the strongest ROAS, but holding PMax to 10–25% of budget showed conversion rate and CPA advantages; 82% of advertisers ran PMax alongside other campaign types [S3]. Test: hybrid (PMax + Search/Shopping) vs consolidated PMax.
- **TEST (vs "bidding earns its way up")**: Google's own ladder is close (count → target → value) and lets value bidding start at ~15 monthly conversions [S1]. Test whether that bar is too low in practice.
- **TEST (new, no Meta equivalent)**: AI Max as expansion layer. smec found AI Max conversions at roughly 35% lower ROAS than traditional match types in the same retail campaigns, and that ~29% of exact-match impressions were being broadened by AI Max by July 2026 (EMEA ecommerce) [S4]. Test: AI Max on vs off per client via campaign experiment.
- **TEST (new)**: brand search. One brand ran three holdout tests on brand search (slow season, peak, new markets) and found ~1% lift at best, then switched it off [S5]. Default assumption: brand search is mostly not incremental until a holdout says otherwise.
- **OPEN**: right minimum daily budget per campaign for the UK market. Google quotes a US-dollar figure for Demand Gen [S2]; no UK equivalent verified.

## 4. Offer: a lever, not a constant

Principle: same as Meta. Test offers like creative; match the offer to the buying trigger.

| | Basic | Standard | Best in class |
|---|---|---|---|
| Offer in ads | Price / promo visible via assets (price, promo extensions) | Evergreen and promo asset groups kept separate so promos can switch on/off cleanly | Offers tested by query intent (e.g. comparison vs. high-intent queries get different offers) |
| Feed offers | Prices accurate | Sale prices and promotions in Merchant Center | Offer mix tested against margin, not just ROAS |
| New vs returning | No distinction | New-customer goal set (acquire vs retain) | New-customer value set from 12-month LTV, offer tuned to new-customer trigger |

- **OPEN**: how much of the offer effect is visible on Search vs only on PMax / Shopping surfaces? No data-led source found.
- **OPEN**: Google's new-customer acquisition settings and their reliability. Not verified for v0.1.

## 5. Post-click: the channel owner owns the click to the conversion

Principle: same as Meta. The page matches the ad; find the rate-limiting step.

| | Basic | Standard | Best in class |
|---|---|---|---|
| Message match | Ads land on a relevant page | Each query theme / asset group has a matching landing page | Landing page variant per top query cluster, tested on a cadence |
| URL control | Final URL expansion on by default | Expansion reviewed; URL exclusions set for pages that shouldn't receive paid traffic | Expansion only where landing page tests prove it |
| Rate-limiting step | Conversion rate tracked | Funnel step rates tracked from landing to conversion | Weakest step named and owned each month |
| Speed | Page loads | Mobile load time within `[ ]` | `[ ]` |

- **TEST (vs Meta)**: Google's AI Max and PMax can pick landing pages themselves. That cuts against "the channel owner owns message match". Test: expansion on vs off on conversion rate.
- **OPEN**: benchmark conversion rates. WordStream/LocaliQ's 2026 report gives cross-industry averages (US-based) but is not yet a source for this standard; review before using for calibration.

---

## Operating rhythm (Google-specific)

- **Weekly**: search-terms review (negatives, brand leakage, AI Max expansion); graduate and kill visual assets with Meta.
- **Monthly**: channel state of play; score each pillar Basic / Standard / Best in class. Report brand and non-brand separately.
- **Quarterly**: structure review; decide one holdout test (brand or PMax) for the next quarter.

## Tests against existing principles (summary)

| # | Meta principle | What Google sources say | Test |
|---|---|---|---|
| 1 | Event closest to money | Bid on a short-delay stage with ≥15 conversions/month [S1] | Money event vs high-volume proxy |
| 2 | Click over view-through | Many YouTube conversions are engaged views [S2] | Count engaged views only if holdout confirms |
| 3 | Creative is the targeting | Text-only PMax did best; signals flat or worse [S3] | Feed-only vs full-asset PMax |
| 4 | Creative volume scales with spend | Doesn't apply to Search | Scope rule to visual surfaces |
| 5 | Consolidate | Hybrid PMax + Search/Shopping common; tradeoffs by budget share [S3] | Hybrid vs consolidated |
| 6 | Channel owns message match | AI Max / PMax choose pages | URL expansion on vs off |
| 7 | (new) Expansion layer | AI Max ~35% lower ROAS in smec retail data [S4] | AI Max on vs off |
| 8 | (new) Brand search | Holdouts show little or no lift [S5] | Geo holdout on brand |

## Sources

- **[S1] Platform**: Google Ads Help, value-based bidding and conversion values best practices. https://support.google.com/google-ads/answer/14792795 and https://support.google.com/google-ads/answer/14791574
- **[S2] Platform**: Google Ads Help, best practices for Demand Gen campaigns. https://support.google.com/google-ads/answer/14693848
- **[S3] Data-led**: Optmyzr, Performance Max study (9,199 accounts, 24,702 campaigns). https://www.optmyzr.com/blog/performance-max-study/
- **[S4] Big-budget operator / data-led**: Smarter Ecommerce (smec), Mike Ryan's AI Max analyses, as reported by PPC Land and Search Engine Journal. https://ppc.land/exact-match-loses-1-in-4-impressions-to-ai-max-smec-finds/ and https://www.searchenginejournal.com/what-smecs-data-reveals-about-ai-max-performance/568866/
- **[S5] Operator / measurement**: Haus case study, three brand search incrementality tests. https://haus.io/case-study/a-series-of-3-incrementality-tests-prove-brand-search-to-be-ineffective

Note on source quality: S1–S2 are Google's own advice and favour more automation. S3–S4 come from tool vendors with an interest in "you need control". S5 is a vendor case study, single brand. Weigh accordingly.

## Change log
- v0.1.1 (23 Oct 2026): moved into the skills library. References to `meta-playbook-principles` renamed `meta-playbook`; IP line made generic (no employer or agency names). No change to principles, levels or tests.
- v0.1 (23 Oct 2026): first draft. Five pillars mirrored from Meta Playbook v0.1; 8 tests logged; thresholds blank.
