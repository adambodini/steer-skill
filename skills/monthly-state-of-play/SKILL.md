---
name: monthly-state-of-play
description: Each month, score every live channel for a client on the five pillars against its channel standard, show the direction of travel, and propose next month's changes, for Adam to review before the monthly state of play meeting.
---

# Monthly state of play

Operate stage. Run by the Delivery agent, once a month, per client. It uses `channel-standard` for the scoring rules and the channel's own standard (`meta-playbook`, `google-ads-channel-standard`, `tiktok-ads-channel-standard`, `creator-channel-standard`) for what each level means.

## Inputs
- The client record in Notion and last month's state of play.
- Read access to each channel account, where granted.
- The Growth Cockpit numbers for the month.

## Step 1: score each channel
For every live channel, score each pillar: Signal, Creative, Media buying, Offer, Post-click.

| Score | Meaning |
|---|---|
| Basic | Below standard; a known cause of underperformance |
| Standard | Meets the channel standard |
| Best in class | Ahead of the channel standard |
| Not scored | No access or no evidence this month |

Every score needs **one line of evidence**: what was seen and where. No evidence, no score. Use `Not scored` and say what's missing.

Thresholds are still blank in the standards, so most scores are judgement against the principles. Mark those `judgement` so Adam knows where to look hardest.

## Step 2: direction of travel
Against last month, per pillar: `↑` better, `→` same, `↓` worse, `new` for the first month. Use `new` rather than guessing a direction when there is no previous score.

## Step 3: next month's changes
Up to three changes per channel, aimed at the lowest-scoring pillars first. Each one has:
- the change, in one sentence;
- the pillar it moves and the level it's aiming for;
- the owner on the client's team (the client team does the work; Adam sets the standard);
- how we'll know it worked.

If a change matches a TEST in the channel standard, link it to that test so the result can be logged back.

## Step 4: write it up
- **Notion:** one new Meetings row, Type `Monthly state of play`, linked to the client, Written by `Delivery agent`. The score table, directions and changes go in the page body.
- **Draft pack:** one page per channel (score table, direction, three changes) next to its Cockpit numbers.

## Rules
- Client data stays in Notion. Nothing from a client goes into this skill or any standard.
- Don't invent numbers. A figure the account or the Cockpit doesn't show is `OPEN`.
- Adam reviews in about 20 minutes and can change any score. His changes win.
- **Nothing goes to the client until Adam approves it.** This skill never sends or shares the pack.
- If a test result comes out of the month, log it in the channel standard's change log as generic evidence, without the client's name or numbers.

## OPEN
- Whether scores need their own Notion database (one row per channel per month) so six months of progress can be charted. For now they live in the Meetings page body.
- Which channels count as "live": a minimum spend `[ ]`, or any channel with spend.
- Standards for channels not yet written (e.g. Amazon) are missing. Score those `Not scored` until one exists.

## Change log
- v0.1 (23 Oct 2026): first draft. Moved into the skills library unchanged.
