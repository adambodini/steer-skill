---
name: cac-ceiling
description: Work out what a brand can afford to pay for a new customer from its contribution margin stack, and compare it with its CAC target and what it actually pays.
---

# CAC ceiling

The question is never "what is our ROAS?" It is "what is our CM2 per new customer, and does it justify what we spend to get them?" ROAS is a platform metric. CM2 is a business metric.

## The contribution margin stack
| Line | Meaning |
|---|---|
| Gross revenue | What the customer pays |
| − returns and refunds | |
| = Net revenue | The real starting point |
| − COGS | Product, fulfilment, delivery |
| = **CM1** (gross profit) | What's there before marketing |
| − working CAC | What it costs to win each customer |
| = **CM2** | Profit per customer after acquisition: the main operating metric |
| − allocated fixed costs | Platform fees, team, tools |
| = **CM3** | Fully loaded margin |

## The ceiling
Everything is measured over the same window: a new customer's **first 12 months**.

**CM1 per customer (12 months)**, by business model:
| Model | CM1 per customer |
|---|---|
| One-off purchase | average order value (net of returns) × gross margin % |
| Repeat purchase | average order value × gross margin % × orders in the first 12 months |
| Subscription | monthly revenue per subscriber × gross margin % × average months a subscriber stays in their first 12 months |

For a subscription, the months come from monthly churn: 1 + (1 − churn) + (1 − churn)² + … over 12 months. Example: 10% monthly churn ≈ 7.2 months.

**CAC ceiling** = CM1 per customer − target CM2 per customer.

**Target CM2** is the profit the brand wants to keep from each new customer's first 12 months, after paying to win them. It's the brand's choice: a higher target means a lower ceiling and safer, slower growth.

Example: £85 × 55% × 1 order = £46.75 CM1. Target CM2 £20 → ceiling £26.75.

### Why 12 months, not lifetime value
Lifetime value (for a subscription, monthly gross profit ÷ monthly churn) is shown for reference only. The ceiling uses the first 12 months so it doesn't depend on customers staying for years, and so a brand isn't told it can afford a CAC it would take years to earn back.

## What to look for
- **Do they know these numbers?** Most don't know their 12-month repeat rate. That is a gap.
- **Blended CAC vs ceiling.** Above it: they lose money on the average customer.
- **Their target vs ceiling.** Above it: hitting the target still loses money. Well below it: growth left on the table.
- **Each channel's working CAC vs ceiling.** Any channel above it for three months running without a credible plan gets cut or fixed.

## In the workshop
The ceiling is worked out silently and shown only at the reveal, next to their own target and what they pay.

## Change log
- v0.2 (23 Oct 2026): business models added (one-off, repeat, subscription); subscription value from monthly churn over 12 months; target CM2 defined with its time window; lifetime value shown for reference only.
- v0.1 (22 Oct 2026): first version, from STEER's contribution margin stack.
