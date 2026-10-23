---
name: workshop-to-notion
description: Agent 1, owned by the Delivery agent. After a State of Play workshop, write the saved canvas into the brand's client record in Bod Brands HQ (Notion), log the workshop as a meeting, and draft the summary and proposal for Adam to approve.
---

# Workshop to Notion (Agent 1) v0.3.1

Owned by the **Delivery agent**: its output is the onboarding brief. Runs straight after a `state-of-play-workshop`. It turns the saved canvas into the client record, so the canvas becomes the onboarding brief. It is also the hub's graduation test: Bod Brands HQ stays at "Testing" until one real workshop has gone through this skill end to end and Adam has checked the result.

## Inputs
- The brand's saved State of Play canvas (its own link) and the CSV export of the canvas.
- Adam's notes from the session, if any.

**Real run:** if either the canvas link or the CSV is missing, stop and ask Adam. Do not rebuild a canvas from memory or from the call.

**Test or dry run:** a text-only canvas transcript is accepted in place of the link and CSV, only when Adam says the run is a test or a dry run.
- **Dry run:** no writes of any kind. The output is shown to Adam in chat.
- **Test:** the record body opens with `TEST RUN: built from a text transcript, not a saved canvas`, and the Workshop canvas field stays blank.
- A transcript never stands in for the canvas on a real run, and a test or dry run never counts towards the graduation check.

## Labels
Every figure carries one label, kept from the canvas:
| Label | Meaning |
|---|---|
| `CONFIRMED` | Checked against an account, a backend or a document during or after the session |
| `STATED, UNVERIFIED` | Given by the brand but not checked against an account. Goes into the diagnostic brief for checking |
| `GUESS` | An estimate (a yellow box on the canvas) |
| `OPEN` | Not known (an orange box, or a blank) |

**Derived figures:** a figure calculated from other figures carries the weakest label of its inputs. If any input is a `GUESS`, the result is a `GUESS`; if any input is `OPEN`, the result is `OPEN` and isn't calculated.

## Duplicate check
Before creating anything, search Clients for candidate matches:
- Brand, case-insensitive, ignoring punctuation, "&" / "and" and words like "Ltd"; any shared distinctive word counts as a candidate.
- Website domain, where one is known.

Then:
- **No candidates:** create a new record.
- **One or more candidates:** stop and show them to Adam. He confirms whether it's the same brand.
- This skill **never merges, overwrites or auto-resolves** a match, and never writes to a candidate record until Adam has confirmed.

## Where things go
Client data goes into Notion only. Nothing from the canvas goes into this skill, the skills library, or any other file.

**Clients** (one record per brand):
| Field | What to write |
|---|---|
| Brand | After the duplicate check above. Never create a duplicate. |
| Stage | `Workshop done` |
| Workshop canvas | The link to this brand's canvas (blank on a test run) |
| Website, Main contact, Contact email | Only if the brand gave them |
| Monthly ad spend | Total spend as the brand stated it in the session, only when every channel's spend is known. Leave blank if they couldn't give it or if any channel is missing. Never write an estimate or a partial total into this field. |
| Primary channel | The channel with the most spend, as stated. Leave blank if unclear. |
| Next action, Next action date | The next step and date agreed at the close. Blank if none was agreed. |

**Meetings** (one new row):
| Field | What to write |
|---|---|
| Meeting | `State of Play workshop` |
| Type | `Workshop` |
| Client | Link to the client record |
| Date | Date of the session |
| Decisions | The three levers, in the brand's own words |
| Actions | One line per lever: owner and date, each marked `PROPOSED` until confirmed (see Levers) |
| Recording | Transcript link, if one exists |
| Written by | `Delivery agent` |

**Body of the client record**, as the onboarding brief. Sections and columns mirror the canvas, so every canvas number has one place to go:
1. **Goals:** revenue goal, contribution margin goal, their CAC target, why now, what stopped them, what they've tried, who the customer is.
2. **What a new customer is worth:** the business model and its inputs as on the canvas (one-off: order value; repeat: order value and orders in 12 months; subscription: monthly revenue per subscriber and monthly churn), gross margin %, and profit to keep per new customer (target CM2). Then the derived CM1 per customer and CAC ceiling, each carrying the weakest label of its inputs (see `cac-ceiling`). Lifetime value, if shown, is reference only.
3. **Channels, last month:** one row per channel, organic included, with these columns, each figure labelled:

   | Channel | Spend | New customers (platform) | Platform share | CAC (platform) | Share of new customers | Share source | Working CAC | Owner | Optimising for |
   |---|---|---|---|---|---|---|---|---|---|

   - **Share source** is `Their estimate` or `Exit poll`, as set on the canvas. An estimated share is a `GUESS`.
   - **Working CAC** is spend ÷ (share × total new customers), so it carries the share's label: from an estimate it is a `GUESS`.
   - Below the table: total new customers last month, blended CAC, and what the shares add up to (with the unexplained remainder).
4. **The reveal:** share of new customers the platforms can trace vs what the brand believes, and their CAC target vs the CAC ceiling vs blended CAC, as read out.
5. **Unknowns:** every orange box from the canvas, listed. These are the diagnostic's brief.
6. **Guesses:** every yellow box, labelled `GUESS`, with whether the brand confirmed or corrected it.
7. **To verify:** every `STATED, UNVERIFIED` figure, for the diagnostic to check.

## Partial totals and the gate
- When only some channels' spend is known, show the known spend in the record body as `PARTIAL TOTAL`, naming the channels it covers and the channels it leaves out. It never goes into Monthly ad spend.
- Any gate reading taken from incomplete or unverified data is reported as `GATE: UNVERIFIED`. Never report it as pass or fail.
- Qualification decisions stay with Adam. This skill reports what is known and missing; it never qualifies or disqualifies a brand.

## Levers
At the close, the chair asks for an owner and a date for each lever.
- Owner and date given and agreed: write them in Actions.
- Owner or date suggested but not agreed, or not given: write them as `PROPOSED`, not as commitments. A missing owner or date is `OPEN`.
- Adam confirms proposals after the session; until then they stay `PROPOSED`.

## Rules
- Copy what the canvas says. Don't fill a gap, round a number or infer a figure. A blank stays blank and goes in Unknowns.
- Keep the labels from the canvas. A guess the brand didn't confirm stays a guess.
- If the canvas and Adam's notes disagree, write both and flag it for Adam. Don't pick one.

## After writing
1. Draft the one-page summary and the proposal (sections below) from the record. Save both as drafts on the client record.
2. Tell Adam what was written and list anything blank, flagged, `PROPOSED`, `UNVERIFIED` or a duplicate candidate.
3. **Nothing goes to the brand until Adam approves it.** This skill never sends an email or shares a page.

## The proposal draft
Seven sections, each from a named source. Nothing in the proposal is invented; a section whose source is empty says so.

| # | Section | Source |
|---|---|---|
| 1 | What we heard | Goals, in the brand's own words |
| 2 | What we found | The reveal and the unknowns count, with labels kept |
| 3 | The three levers | Meetings → Decisions, in the brand's own words |
| 4 | What we'll do | The standard engagement: Diagnose, then Install, then Operate. Core package: exit poll, attribution multiplier, multiplier-adjusted bids, Steering pack |
| 5 | Timeline | The standard engagement: 6 months, months 1–3 then months 4–6 |
| 6 | Investment and terms | The standard offer as recorded in Notion → Decisions, copied as it stands, marked `ADAM TO CONFIRM`. Add-ons only if Adam has named them for this brand. Month-3 break clause on objective triggers |
| 7 | What we need from you | Data and account access, a named owner per channel, exit poll install in week 1, the next step and date from the close |

- The agent never changes a fee, discount or term for a brand. Any change is Adam's, made by hand.
- Offer items still marked Hypothesis in Decisions stay flagged in the draft.

## Graduation check (first run only)
Adam opens the record and confirms four things: no duplicate record, every canvas number matches, unknowns are complete, and the drafts are usable. When all four pass, set the hub's roadmap item to `Live`. Test and dry runs don't count.

## OPEN
- The CSV column names aren't documented in this skill. Confirm them against the first real export, then map them here.
- Where drafts live: a page under the client record, or in Engagements once one exists.
- How the `Passes £50k gate` formula shows a blank Monthly ad spend (fail vs empty). Not readable through the connector; Adam to check in Notion. The rule above applies whatever the formula shows.
- The £50k gate policy itself: Adam's decision, not changed here.
- Scheduling and the graduation-hold definition: Adam's decisions, not covered by this skill.
- **Duplicate check on an empty database.** The fuzzy check can't be properly tested while Clients is empty. Re-test once real records exist.

## Change log
- v0.3.1 (23 Oct 2026): unit economics follow the canvas's business model (one-off, repeat, subscription). "Optimising for" is now a fixed list on the canvas; "Not sure" counts as `OPEN`.
- v0.3 (23 Oct 2026): three decisions from Adam.
  1. The Delivery agent owns this skill; Written by is `Delivery agent`.
  2. The brief mirrors the canvas: the channels table now has the canvas's columns (platform customers, platform share, share of new customers with its source, working CAC), and the goals and unit-economics sections match the canvas fields. Working CAC from an estimated share is a `GUESS`.
  3. The proposal has seven defined sections, each with its source; fees are copied from the standard offer in Decisions and marked `ADAM TO CONFIRM`.
  The lever prompt (owner + date per lever) is now in `state-of-play-workshop`, closing that OPEN item. Still OPEN: CSV mapping, where drafts live, gate formula display, gate policy, scheduling, graduation hold, duplicate re-test.
- v0.2 (23 Oct 2026): six fixes from the dry run, approved by Adam.
  1. A figure derived from a guess carries the guess's label (weakest input wins).
  2. New label `STATED, UNVERIFIED` for brand figures not checked against an account; listed under "To verify".
  3. Partial totals shown as `PARTIAL TOTAL`, never in Monthly ad spend; any gate reading from incomplete data is `GATE: UNVERIFIED`, never pass or fail; qualification stays with Adam.
  4. Input gate accepts a text-only canvas transcript for tests and dry runs, marked as such; dry runs make no writes; never counts for graduation.
  5. Duplicate check uses fuzzy name and domain matching to surface candidates for Adam to confirm; never merges, overwrites or auto-resolves.
  6. At the close the chair prompts for owner + date per lever; unconfirmed ones are recorded as `PROPOSED`, not commitments.
- v0.1 (23 Oct 2026): first draft; validated by dry run with a fictional brand; nine issues logged.
