# Changelog

Template changes only. Your own files are never part of an update.

## 0.5.0 — 2026-11-01

From a real first setup with connected tools (calendar, email, task board, portfolio tracker, training app):

- **Where your data lives:** `me.md` gets a *Where my data lives* section. The context interview has a new **Sources** step (both paths): which tools hold the owner's data, whether to read them, and whether tasks and numbers live in the repo or in those tools. It tells the owner where to connect a missing tool and never blocks on it.
- **Pull before you ask:** AGENTS.md, both interview skills and the investing, health, personal-finance, home-and-family and career banks read connected tools first and ask only to confirm.
- **Options on request:** when the owner asks for options or gets stuck, the assistant offers 3–4 built from their own files and data. More `[options: …]` in the generic, health and personal-finance banks.
- **Context, not a to-do list:** AGENTS.md and `now.md` say small tasks belong in the owner's task tool; the repo keeps goals, rules, focus, big open loops and dates.
- **Automation:** new `prompts/daily-brief.md` and `prompts/monthly-metrics.md`, the weekly review reads connected tools, and a new `AUTOMATE.md` covers scheduled tasks and their pitfalls (connectors per task, attaching the repo, saves on a separate branch).

## 0.4.0 — 2026-11-01

- **Quick start:** context-interview offers a full setup (~20 min) or a quick start (~5 min: name, language, how to talk to you, then straight into one area). The rest is tracked in a `## Setup progress` note and offered later.
- **Clickable options:** AGENTS.md tells assistants to use a built-in question/options tool (such as `AskUserQuestion` in Claude Code) for questions with a small set of answers, and to list the options inline otherwise. Questions with options are marked `[options: …]` in the question banks and skills.

## 0.3.1 — 2026-11-01

After re-running the investing-area, refresh and privacy scenarios on 0.3.0 (all passed):

- AGENTS.md: a "save this?" counts as a question; confirm each save in one line; decline Never-store items without repeating the value or adding advice.
- context-refresh: starts on the first file straight away; asks "How did it turn out?" with the second part only as a follow-up.
- context-interview: the progress note asks before keeping unsaved answers.
- area-interview: links a new extra file (e.g. a thesis) from `status.md`.
- Thesis template: `opened` split into `written` and `first_bought`.

## 0.3.0 — 2026-11-01

From seven simulated conversations (first run, investing area, rule-breaking decision, refresh, privacy trap, Estonian owner, resumed interview):

- AGENTS.md: one question per message; a yes covers only text already shown; file content in the owner's language with headings and labels kept in English; dates in YYYY-MM-DD inside sentences too; commit after each saved change; Never-store items stay out of drafts, notes and commits and are declined in one sentence; clearer rules for other people's details and for amounts.
- context-interview: privacy line up front; Round 4 always updates `areas/README.md` (new `Set up next:` line), parks early answers in `inbox/<slug>-setup.md`, asks separately whether to start the area now; progress note always offered when stopping, at the top of `now.md`.
- area-interview: follows the question bank's section order including extras such as theses; picks up `inbox/<slug>-setup.md`; parks side tasks until Close; new "Stopping early" step.
- log-decision: one field per message; waits for the owner's choice when a rule is broken; thesis log for adds and trims too; offers `status.md` / `now.md` updates.
- context-refresh: one follow-up per message; offers moved to the close; recalculated lines shown in the diff.
- Question banks: two-part questions split; investing first payoff reuses the status rule check; contributions may be stored.

## 0.2.0 — 2026-11-01

- AGENTS.md: language rule, "ask for today's date", what to do when the assistant can't write files, archiving for long journals, more items on the Never-store list, `Outcome:` exception to append-only, more everyday phrases, `template_version` frontmatter.
- START-HERE.md: "Use this template, not Fork"; Path B explains that apps read but don't write the repo, with paste-back steps; Path C uploads every file; Claude Code skills step is optional and uses `cp`.
- Skills: refresh skips `_` templates, journals and `decisions.md`, scans extra files; log-decision sets `last_updated` and reads the latest 20 entries; area-interview copies `_` templates instead of filling them; area status `planned`.
- README: Updating section (template files vs. your files), clearer privacy notes.

## 0.1.0 — 2026-11-01

- First version: core files, areas with a four-file skeleton, investing area, four skills with question banks, prompts.
