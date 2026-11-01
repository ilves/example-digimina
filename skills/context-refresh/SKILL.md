---
name: context-refresh
description: Find context files that are out of date and update them with a few quick questions; also close out decisions whose review date has passed. Use when the owner says "refresh" or "what's out of date?", once a month, or when a file read during a conversation is past its review date.
---

# Context refresh

**Goal:** in 5–10 minutes, bring stale files up to date and review past decisions, asking as few questions as possible.

## 1. Find what's stale

You need today's date. If you don't know it, ask.

Scan these files: the Markdown files in the repo root, and for every area marked `active` in `areas/README.md`, the files in `areas/<area>/` including the extra files and subfolders listed under `extra_files` in its `goals.md` (for example every thesis in `theses/`).

- **Skip** files or folders whose name starts with `_` (templates), files with no `review_every` (journals, `decisions.md`, archives), and files with `status: empty` or `status: template`.
- Read the frontmatter `last_updated` and `review_every` (for example `14d`, `30d`, `180d`).
- A file is **stale** if today is later than `last_updated + review_every`, or if `last_updated` is empty while `status` is `active`.

Also open `decisions.md` and list entries whose **Review on** date has passed and whose `Outcome:` line is empty.

## 2. Show the list first

Tell the owner, briefly:

```
Out of date: now.md (3 weeks), investing/status.md (6 weeks)
Decisions to review: 2
This should take about 8 minutes. I'll start with now.md; say "skip" to drop anything.
```

In the same message, go straight into step 3 for the first file; don't ask a separate yes/no. They can drop items or stop at any point.

## 3. Refresh one file at a time

- Start with `now.md`; it goes stale fastest.
- For each file, ask **one** opening question: "Here's what <file> says. What has changed?" Show the key lines, not the whole file.
- Ask at most two follow-ups, **one per message**. Keep offers (a journal lesson, a new decision, ideas to fill a free slot) for the Close.
- Propose a short diff with everything you'll change, including lines you reword or recalculate yourself. Save on yes. Update `last_updated`. If nothing changed, just update `last_updated` and say so.
- For an area's `status.md`, re-run the area's rule check if its `rules.md` defines limits (for example investing position limits), and put the new rule-check lines in the same diff. If the numbers don't add up (for example weights over 100%), ask rather than guess.

## 4. Review decisions

For each decision past its review date:

1. Show the entry.
2. Ask: "How did it turn out?" If the answer doesn't say whether they'd decide the same way again, ask that as the follow-up.
3. Fill in the `Outcome:` line with today's date and their answer. This is the one exception to append-only: the line was left blank for this purpose. Set `last_updated` in `decisions.md`.
4. If there's a lesson, offer to add it to the area's `journal.md`.

## 5. Look for patterns (only if there's enough history)

If there are at least five reviewed decisions or ten journal entries in an area, offer one observation about a pattern ("Three of your four regretted decisions were made in the same week as a big market drop."). Offer it as a question, not a verdict.

## 6. Close

- Update `areas/README.md` "Last reviewed" for areas you touched (show it; save on yes).
- If you have git access: commit `refresh: <files>`.
- One line: what's now up to date, and when the next refresh is due. Then, if any, the offers you parked, at most three bullets.
