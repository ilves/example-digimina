---
name: area-interview
description: Add a life area (investing, personal finance, health, career, home and family, learning, or any custom area) to the context repo and fill its files by interviewing the owner. Use when the owner says "add an area for X" or "let's set up my X", or when context-interview hands off.
---

# Area interview

**Goal:** a new or empty area folder becomes four filled files (`goals.md`, `rules.md`, `status.md`, `journal.md`), plus the extra files the area needs, in 10–20 minutes.

## 1. Identify the area

- Turn the name into a slug: lowercase, hyphens (`home-and-family`, `house-renovation`).
- Check `areas/README.md`. If the area exists and is `active`, ask whether they want to refresh it instead (`context-refresh`).
- Read `me.md` and `now.md`. Don't ask anything they already told you; confirm it instead ("You said you run three times a week. Still true?").
- Read `me.md` → *Where my data lives*. If a connected tool covers this area (a portfolio tracker for investing, a training or health app for health, the calendar for dates, a task board for open work), pull from it first and confirm instead of asking. If the area's numbers could live in the repo or in that tool, ask once which they prefer. `[options: In the repo · In the tool, the repo keeps a summary · Both]`
- If `inbox/<slug>-setup.md` exists, it holds answers the owner already gave for this area. Treat them as known, and delete the file once they're saved into the area.

## 2. Load the question bank

- If `question-banks/<slug>.md` exists, use it. Otherwise use `question-banks/_generic.md` and adapt the wording to the area.
- Each bank lists: extra files, sensitivity notes, suggested default rules for the AI, questions per file in order, and a first payoff.
- Tell the owner the plan in one line, naming every section in the bank's order (for investing: goals, rules, status, theses, journal).

## 3. Create the folder

- If the folder doesn't exist, say you'll copy `areas/_template/` to `areas/<slug>/` and create the bank's extra files. Do it on yes. If you can't create files, give the owner each new file's full text and path to paste.
- Replace `<area-slug>` and `<Area name>` placeholders. Set `extra_files` in `goals.md` frontmatter.
- If a bank's extra folder has a template inside it (a file starting with `_`, like `theses/_thesis-template.md`), copy that file for each new item and set the copy's `status: active`; never fill in the template itself.

## 4. Interview, one section at a time

**Order: follow the sections of the question bank** — goals → rules → status → the bank's extra sections (for example Theses) → journal seed.

For each section:
1. Ask the bank's questions one per message. Skip what's known, including anything a connected tool already answered (show it and let them confirm). If the owner asks for options, offer 3–4 built from their files and data. Questions marked `[options: …]` get clickable choices if your tool supports them (see AGENTS.md). If a bank question has two parts, ask the first and follow up only if needed.
2. Reflect back in two or three lines.
3. Draft the file. Show it. Save on yes. Set `status: active` and `last_updated`. Commit if you have git access.

Before the **status** section, read the bank's sensitivity note to the owner in one sentence (for example: "For health, I'll write down habits and goals, not diagnoses, unless you want me to.").

In the **rules** section, always ask explicitly: "In this area, what do you want me to do, and what should I never do?" Offer the bank's default AI rules as a starting point and let them edit.

For **extra sections**, ask once after status: "Do you have energy for <the extra, e.g. one thesis for your largest single stock> now?" `[options: Yes, now · Later]` If yes, ask the bank's questions and create the file from its `_` template; if `status.md` should point to the new file (for example the Thesis column), show that one-line change too and save on yes. If no, leave it and add an open loop to `now.md` ("Finish <area>: <what's left>").

For the **journal seed**, ask for one or two recent moments worth recording, so the journal doesn't start empty.

**Stay on the interview.** If a decision or another task comes up (for example logging a past trade), note it and offer it after Close, unless the owner asks to do it right now.

## 5. Stopping early

If the owner stops before Close, offer an open loop in `now.md`: `Finish <area> setup: <sections left>`. Show it and save on yes. Leave the area's status in `areas/README.md` unchanged.

## 6. Close

1. Update `areas/README.md`: status `active`, last reviewed today; clear or update the `Set up next:` line. Show the change and save on yes.
2. If you have git access: commit `<slug>: set up area`.
3. Deliver the bank's **first payoff**: do one useful thing in this area right away, using only what's now in the files.
4. Offer anything you parked during the interview.

## Adding a new question bank

To support a new kind of area, copy `question-banks/_generic.md` to `question-banks/<slug>.md` and keep its sections. The skill picks it up automatically.
