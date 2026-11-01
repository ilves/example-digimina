# Automate it

Some prompts work best when they run on their own: a brief every evening, a review every Friday, the numbers on the 1st of the month. Any assistant that can run scheduled tasks (for example Claude Code routines) can do this.

## Good candidates

| Prompt | When | What you get |
|---|---|---|
| `prompts/daily-brief.md` | Every evening | Tomorrow in a few bullets, plus at most one question |
| `prompts/weekly-review.md` | Once a week | What moved, one loop to close, proposed updates to `now.md` |
| `prompts/monthly-metrics.md` | 1st of the month | One new row in your metrics table, five lines on the trend |
| `context-refresh` | Every two weeks | Stale files and review dates |

## Setting it up

1. Ask your assistant: **"Automate the daily brief at 20:30"** (or another prompt and time). Give your time zone.
2. The scheduled task's instructions should say: read `AGENTS.md`, then follow the prompt file. Keep the AGENTS.md rules: one question per message, nothing saved without a yes.
3. Check three things before you rely on it, then run it once by hand:
   - **Tools (connectors).** A scheduled task only sees the tools attached to *it*, not the ones in your chat. Add the ones the prompt reads (calendar, task board, training app, portfolio tracker). In Claude Code, open the routine and add them under connectors.
   - **This repo.** The task needs your private repo attached, or it can't read `now.md`. If the routine has no repository setting, add the repo to the cloud environment it runs in.
   - **Where saves go.** Scheduled sessions may work on their own branch instead of `main`. For prompts that only read (daily brief, monthly metrics into an external tool) that doesn't matter; for prompts that save (weekly review), check where the first save landed and merge it if needed.
4. Turn on notifications for it, so the result reaches your phone.

## Keep it light

- Start with one automation, not four. Add the next only when you actually read the first.
- Every automated prompt should end with **at most one question**. More than that and you'll stop opening them.
- If a run can't reach a tool, it should say so in one line rather than guess.
