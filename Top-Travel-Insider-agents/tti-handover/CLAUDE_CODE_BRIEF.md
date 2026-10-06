# Brief for Claude Code (paste this into your Claude Code session)

I've added a folder called `tti-handover` to this project. It contains the content plan and context from planning work done elsewhere.

## Setup (one time)
1. Read `tti-handover/context/TTI_CONTEXT.md` fully. It explains the goal, roles, keyword scoring, pillar structure and post standard.
2. Create `.claude/agents/tti-writer.md` using the content of `tti-handover/agents/tti-writer.md`. Fill in its two TODOs: the folder where finished posts should go (the ready folder you pick up from for rendering) and the frontmatter fields from BLOG_TEMPLATE.md.
3. Check the SE Ranking MCP is available here (/mcp). If not, tell me how to connect it; the writer needs it.
4. Treat `tti-handover/context/content_plan.csv` as the topic tracker. Don't change rankings; only update the status and notes columns as posts move along.
5. Batch 1: take the 10 drafts in `tti-handover/drafts-batch-1/`. Using tti-writer, for each one: fit it to BLOG_TEMPLATE.md, fact-check it against official sources (nine have not been checked yet; see the notes column in content_plan.csv), check for overlap with posts already on the site or in our folders, then save it to the ready folder with status ready-for-render. Report anything you couldn't confirm or any overlaps before rendering.
6. Images and rendering continue as you normally do them. Keep tti-writer to research and writing only.

Confirm when the agent is set up and show me the filled-in TODOs before starting step 5.

## Daily schedule: 2 new posts per day, working window 09:20 to 15:50
Once batch 1 is through, set up a daily routine (local time on this computer):

- **09:20, post 1:** use tti-writer to take the highest-ranked "Not started" topic in content_plan.csv, re-check its keywords in SE Ranking, write and fact-check it, save it to the ready folder with status ready-for-render, and update the tracker.
- **12:30, post 2:** the same for the next "Not started" topic.
- **By 15:50:** both posts finished and handed off. Images and rendering follow your normal process. Post a short end-of-day summary: the two titles, primary keywords with volume and KD, word counts, file paths, and any facts that couldn't be confirmed.

Rules for the schedule:
- Never start a new post after 15:00. If a post isn't finished by 15:50, save it as a draft (not ready-for-render), note where it got to in the tracker, and finish it first thing next working window.
- If a topic turns out to duplicate a live post or an existing file, mark it "Skipped: duplicate" in the tracker and take the next one.
- If SE Ranking is unavailable, don't write from guessed data; note it in the summary and stop.

If scheduled tasks are available in this setup, create the two scheduled runs above and confirm the times. If they aren't, tell me, and I'll trigger it manually each day with: "Use tti-writer to write the next 2 posts from content_plan.csv."
