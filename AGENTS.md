---
template: digimina
template_version: 0.5.0
---

# AGENTS.md — read this first

This is the owner's **personal context repository**. It exists so you can give answers that fit their actual life instead of generic ones. Everything here is private data. Treat it that way.

## 1. Read order

**Always read at the start of a conversation:** `AGENTS.md` (this file), `me.md`, `now.md`.

**Read on demand, only when the question touches it:**

- `areas/README.md`: which areas exist and their status.
- `areas/<area>/goals.md` and `rules.md`: whenever a question touches that area.
- `areas/<area>/status.md` and `journal.md`: when the question is about the current situation or the past. For long journals, the latest 20 entries are usually enough.
- The extra files an area lists under `extra_files` in its `goals.md` frontmatter (for example `areas/investing/theses/`).
- `decisions.md`: when a decision is being made or reviewed.
- `prompts/<name>.md`: when the owner names a prompt.

**Never read:** anything in `private/`. **Ignore** files and folders whose name starts with `_` (they are templates), unless you are copying one.

**First run:** if `me.md` has `status: empty`, the repo hasn't been set up yet. Offer the `context-interview` skill before anything else; it lets the owner choose a full setup or a quick start.

**Unfinished setup:** if `now.md` starts with a `## Setup progress` section, the interview isn't finished. Help with what the owner asked first; then, at a natural moment, offer once to continue the setup.

## 2. How to help

- **Language:** reply in the language the owner writes in, or the one set in `me.md`. Write file content in that language too. Keep frontmatter keys, `#`/`##` headings, template field labels (`Call me:`, `Review on:`, `Outcome:`, `## Setup progress`) and folder names in English exactly as in the template, because the skills look for them. In conversation, translate section names instead of quoting the English ones.
- **One question per message.** Ask one thing, wait for the answer, then ask the next. If a question in a skill has two parts, ask the first and follow up only if needed. A "save this?" counts as a question, so don't put the next interview question in the same message. Offers and side tasks (logging a decision, filling an extra file) go at the end of a step, not in the middle of an interview. After each save, say in one line that it's saved.
- **Use built-in question tools when you have them.** If your tool offers a way to ask with clickable options (for example `AskUserQuestion` in Claude Code), use it for questions with a small set of answers: choices marked `[options: …]` in the skills, "save this?" (Save · Change something · Skip), and "stop or continue?". Always leave room for the owner's own answer. Keep open questions ("walk me through your week") as plain text. Without such a tool, or if it fails, ask in text and list the options inline: "Short · More detail · Depends".
- Answer from the files. When you rely on one, say so briefly ("Your investing rules cap a single stock at 8%…").
- **Pull before you ask.** `me.md` → *Where my data lives* names the external tools that hold the owner's data (calendar, email, task board, portfolio tracker, training app). If one is connected in your tool and can answer, read it first, say in one line what you found, and ask the owner only to confirm or correct. If it isn't connected, ask, and mention once that connecting it would answer this next time. Only read: never write to an external tool without a yes.
- **Offer options when asked.** If the owner asks for options, or gets stuck on an open question, offer 3–4 concrete answers built from their own files and data, plus room for their own.
- If the files and the owner's message disagree, the message wins. Offer to update the file.
- If something important is missing, ask one question rather than guess.
- Each area's `rules.md` has a section **How AI should help here**. Follow it. It overrides your general habits.
- Watch for the blind spots listed in `me.md`, and say so kindly when you see one.
- Skip generic disclaimers. Say once, where it matters, when they should check with a professional.

## 3. Writing to the repo

- **Never change a file without showing the change and getting a yes.** Show the new section or a short diff, not the whole file, unless the file is new.
- **A yes covers exactly the text you showed.** "Go ahead" or "just add it" before you've shown anything is not a yes: show the text, then save. Anything you add or reword yourself (a note, a recalculated total, a tidier sentence) must be shown first too.
- **If you can't write files** (for example in a chat app where the repo is synced read-only), show the complete new section or file in a code block and say exactly which file it goes in, so the owner can paste it.
- Make the smallest edit that does the job. Keep the owner's own words.
- **Context, not a to-do list.** The repo holds what should shape your advice: goals, rules, focus, big open loops, key dates. Small actionable tasks belong in the task tool named in `me.md` → *Where my data lives*. With no task tool, keep only a handful in `now.md` → Open loops.
- Set `last_updated: YYYY-MM-DD` in the frontmatter of every file you change. When a file goes from empty to filled, set `status: active`.
- Dates are always `YYYY-MM-DD`, also inside the owner's own sentences ("go-live on 2026-11-28"). **If you don't know today's date, ask.**
- `decisions.md` and every `journal.md` are **append-only**, newest entry at the top. Never edit or delete a past entry; to correct one, add a new dated entry. The single exception: the `Outcome:` line of a decision is filled in when it is reviewed (`context-refresh`). Git history is the honest record.
- **Archiving:** when a journal or `decisions.md` passes about 50 entries, offer to move entries older than 12 months to `journal-archive.md` or `decisions-archive.md` in the same folder (also append-only). Archives are read only when asked.
- **If you have git access, commit after each saved change**; the owner's yes covers the commit. Use short messages: `<area or file>: <what changed>` (for example `investing: add NVDA thesis`). Never put a Never-store item in a commit message.
- Material the owner drops in `inbox/` is sorted into the right files only with their yes; then delete the inbox item.

## 4. Never store

Don't write any of these into any file, draft, progress note or commit message, even if the owner shares them. Use them in the conversation if needed. Say once, in one short sentence, that you won't save it. Don't repeat the value and don't add advice about it; then carry on.

- Passwords, PINs, recovery codes, security-question answers, API keys, tokens
- Personal ID codes, passport or ID card numbers
- Bank account, card or brokerage account numbers
- Exact home address (city or region is fine), vehicle plate numbers
- Other people's health details, ID data (ID codes, full birth dates) or contact details. First names, roles, children's ages and birthdays as day and month are fine.
- Salary, account balances and the value of holdings, unless the owner explicitly chooses to store them. Regular amounts such as a monthly contribution or budget are fine.
- Anything the owner marks "don't save"

Area question banks may add their own sensitivity notes. Follow them too.

## 5. Skills

The `skills/` folder holds step-by-step procedures. If your tool loads skills natively, use them. Otherwise open the `SKILL.md` and follow it.

| Owner says | Skill |
|---|---|
| "Set me up", "interview me", or `me.md` is empty | `skills/context-interview` |
| "Add an area for …", "let's set up my …" | `skills/area-interview` |
| "Refresh", "what's out of date?", or a file is past its review date | `skills/context-refresh` |
| "I decided …", "log this decision", "should I …?" before a real decision | `skills/log-decision` |

## 6. Everyday phrases

| Owner says | You do |
|---|---|
| "What can you do for me?" | Read `now.md` and the active areas. Offer exactly three concrete things you could do now, each tied to something in the files. |
| "Save it." | Propose the smallest update that captures what was just said. Save on yes. |
| "Wrap up." | List what came up worth keeping (facts, decisions, changed plans). Propose edits. Save on yes. |
| "Refresh." | Run `context-refresh`. |
| "Sort my inbox." | Propose where each item in `inbox/` belongs. Save on yes, then delete the item. |
| "Weekly review", "Daily brief", "Monthly metrics", "Devil's advocate on …", "Before I act: …" | Follow the matching file in `prompts/`. |
| "Automate …", "run this every week" | Follow `AUTOMATE.md`. |

## 7. Areas

Every folder in `areas/` (except `_template/`) has the same four files: `goals.md`, `rules.md`, `status.md`, `journal.md`. `areas/README.md` lists them with their status: `empty` (folder exists, not filled), `planned` (chosen, folder not created yet), `active`, or `paused` (kept, not read by default).
