---
name: exit-poll-attribution
description: Set up a post-purchase exit poll, calculate each channel's attribution multiplier and working CAC, and adjust platform bids to the truth. The core of the STEER offer.
---

# Exit poll attribution

Platforms over-claim. Never add up new customers across platforms: every one of them double-counts. The exit poll is the truth; platform data is for relative, over-time decisions.

## 1. The exit poll
- One question, as a popup straight after purchase or lead capture, before the thank-you page. New customers only.
- Headline: "We'd love your feedback!" Question: "How did you first hear about [Brand]?"
- Close button at the bottom, not top-right. Answer order randomised, nothing pre-selected.
- Target: 40%+ completion from new customers.

### Answer options
- Customer language, not marketer language ("Google", not "SEA").
- Every channel driving 3%+ of new customers.
- "Referral from a friend or family member", for word of mouth no platform sees.
- A control option for a channel they don't run (e.g. Radio): its responses are noise and calibrate the baseline.
- Free-text "Other". Over 8% of responses means a channel is missing from the list.
- Ads and influencers on the same platform: add a second question ("an ad from [Brand]" vs "an influencer I follow").

## 2. The numbers
- **Exit poll new customers per channel** = channel share of poll responses × total new customers.
- **Attribution multiplier (M)** = exit poll new customers ÷ platform-reported new customers, per channel, monthly.
- **Working CAC** = channel spend ÷ exit poll new customers.
- Plan on a rolling 3–6 month average of M.

| M | Meaning | Action |
|---|---|---|
| Above 1.0 | Brand reach is wider than the platform sees; true CAC is lower | Scale with confidence |
| About 1.0 | Platform roughly right | Hold |
| Below 1.0 | Platform over-claims; true CAC is higher | Treat scaling with scepticism |

## 3. Bidding to the truth
- **New target CPA** = current platform target CPA × M. Example: €75 × 1.27 = €95.
- Apply gradually; don't shock the algorithm.
- Every channel's working CAC must sit under the CAC ceiling (see `cac-ceiling`).

## Volume check
Below roughly 300 new customers a month, per-channel shares get noisy. That is why the qualification gate sits at £50k+ monthly ad spend.

## In the engagement
- Week 1: poll live (e.g. a Shopify post-purchase survey app).
- Month 2: first multiplier read.
- Month 3: stable enough to change bids.
