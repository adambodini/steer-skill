# STEER skills library

The methodology behind Bod Brands growth consulting, written as portable skills. Owner: Adam Bodini.

## The separation rule

This repo holds **methodology only**: how things are done. It never holds client data, client names, client numbers or any employer material. Client data lives in Notion (Bod Brands HQ), one record per client. Nothing crosses between the two.

## What's here

| Folder | What it is | Lifecycle stage |
|---|---|---|
| `skills/prospect-research` | Public-data research, canvas pre-fill, outreach draft; also the bake-off job spec | Acquire |
| `skills/state-of-play-workshop` | Running the 90-minute State of Play workshop | Convert |
| `skills/workshop-to-notion` | Agent 1 (Delivery agent): canvas to client record, summary and proposal drafts | Convert, Onboard |
| `skills/cac-ceiling` | The contribution margin stack and the CAC ceiling | Convert, Diagnose |
| `skills/exit-poll-attribution` | Exit poll design, the attribution multiplier, working CAC | Diagnose, Operate |
| `skills/channel-standard` | How any channel is scored each month across five pillars | Operate |
| `skills/meta-playbook` | Meta standard: principles across the five pillars | Diagnose, Operate |
| `skills/google-ads-channel-standard` | Google Ads standard: levels and open tests | Diagnose, Operate |
| `skills/tiktok-ads-channel-standard` | TikTok Ads standard: levels and open tests | Diagnose, Operate |
| `skills/creator-channel-standard` | Influencer / creator standard: levels and open tests | Diagnose, Operate |
| `skills/monthly-state-of-play` | Monthly scoring of each live channel, for Adam to review | Operate |
| `skills/mentor-loop` | Mentor challenge brief before, test log after | Improve |
| `templates/state-of-play-canvas` | The master workshop canvas (HTML) | Convert |

## How a skill is written

Each skill is a folder with a `SKILL.md`: a short frontmatter (`name`, `description`) and plain instructions. The format works in Claude and is portable to other agent tools that read skill files.

## How a skill changes

1. Every change is a commit with a one-line reason.
2. Playbooks carry their own change log at the bottom: what changed, why, and the evidence (a client result, a mentor challenge, a test).
3. Principles first, thresholds later. A threshold only goes in once real results back it.

## How a client gets a skill

A client receives a **tailored copy** of a skill, installed in their own environment. They keep it after the engagement. The master stays here.
