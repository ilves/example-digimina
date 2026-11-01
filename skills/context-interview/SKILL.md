---
name: context-interview
description: Interview the owner to fill the core context files (me.md, now.md) and choose their first life areas, as a full setup (~20 min) or a quick start (~5 min, then straight into one area). Use on first run when me.md has status empty, when now.md has a "Setup progress" section, or when the owner says "set me up", "interview me" or "start over".
---

# Context interview

**Goal:** turn a relaxed conversation into a filled `me.md` and `now.md`, and a short list of areas to set up next. The owner talks. You do the writing. There are two paths: a **full setup** (about 20 minutes) and a **quick start** (about 5 minutes, then straight into one area; the rest can be done later).

## Principles

- **One question per message.** One thing to answer, one question mark. Say what shape of answer you want: "one line", "a few bullets", "just ramble, I'll tidy it". When a question in the bank has two parts, ask the first and follow up only if needed.
- **Concrete before abstract.** Ask about days, people and what's on the plate before values and goals. People describe their days well and their goals badly. You infer the values, they correct you.
- **Reflect before you write.** At the end of each round: "Here's what I heard: …" Let them correct it, then propose the file. Don't restate every single answer; if the owner says they don't want things repeated back, reflect only at the end of a round.
- **"Skip" is always fine.** Never push for numbers, names or anything sensitive.
- **Their words, not yours.** Don't polish answers into corporate language. Keep their phrasing, typos aside.
- **Pull before you ask.** Once the owner has named their tools (Sources, below), read the connected ones and ask only to confirm or correct.
- **Options on request.** If the owner asks for options or gets stuck on an open question, offer 3–4 answers built from what you already know.
- **Follow the Never-store list in AGENTS.md.**

## Before you start

1. Read `AGENTS.md`, `me.md`, `now.md` and `areas/README.md`.
2. If `me.md` already has `status: active` and there is no `## Setup progress` section in `now.md`, ask: "Update what's there, or start over?" Default to update and switch to `context-refresh`.
3. If `now.md` has a `## Setup progress` section, an earlier interview was interrupted. Say in one line where it stopped and continue from there. Don't re-ask anything already saved in `me.md` or listed in the note.
4. Tell the owner in one short sentence that they don't need to share ID codes, PINs, passwords, account numbers or their street address, and if they do, you'll use them only in this chat and won't save them.
5. Ask which path they want. `[options: Full setup (~20 min, starts with your normal week) · Quick start (~5 min, then straight into one area)]`
   - **Full setup:** say there are four short rounds, files get saved after rounds 2, 3 and 4, and they can stop any time. Do **Sources** (below), then Round 1.
   - **Quick start:** do **Sources** (below), then the **Quick start** section.
6. If you don't know today's date, ask for it; `now.md` needs it.

## Sources — where your data lives (both paths)

Two questions, one per message (`references/core-questions.md` § Sources). They decide whether the repo holds the numbers or only the context.

1. Which tools hold their data, and should you read them? For each one they pick, check whether it is connected in your tool. If it isn't, say in one line where they connect it (in Claude: Settings → Connectors; a cloud session needs a new session afterwards) and carry on. Never block the interview on a missing connection.
2. Where tasks and numbers should live: in the repo, or in those tools with the repo keeping only the context.

Keep the answers for `me.md` → *Where my data lives*; they are saved with the `me.md` draft. From here on, read the connected tools before asking: the calendar for dates, the task board and email for open loops, a portfolio tracker or training app inside the areas.

## Quick start (about 5 minutes)

For owners who came for one thing (for example investing) and want results now.

1. Ask, one per message, the questions marked **(quick)** in `references/core-questions.md`: what to call you, language, length, when to push back, and AI habits that annoy them.
2. Draft `me.md`: fill `Call me`, the **How I want you to talk to me** section and **Where my data lives**; leave the other sections with their template comments. Frontmatter: `status: active`, `setup: quick`, `last_updated`. Show it; save on yes.
3. Ask which area to start with. `[options: the areas from areas/README.md and the ready question banks, plus "something else"]`. Update `areas/README.md` (status `planned`, or `empty` if the folder exists, and the `Set up next:` line). Show it; save on yes.
4. Draft `now.md` with only a `## Setup progress` section at the top: "Quick start done on YYYY-MM-DD. Still to do: Round 1 (a normal week), rest of Round 2 (how I decide, blind spots), Round 3 (this month)." Show it; save on yes.
5. Ask separately whether to start the area interview now. `[options: Start now · Later]`

When the owner later says "let's finish my setup" (or you notice the progress note at a natural moment, not in the middle of another task), continue with the full setup from Round 1, skipping what `me.md` already has. Remove `setup: quick` from `me.md` when it's done.

## Round 1 — A normal week (no writing yet)

Use `references/core-questions.md` § Round 1. Aim for 4–6 questions, one per message. Listen for: what fills their time, who matters, what drains them, what they look forward to.

End the round with a reflection: "From that, it sounds like what matters to you is A, B and C. Close?" Let them correct it.

## Round 2 — How to talk to me → write `me.md`

Use § Round 2. Cover the Snapshot, how they want you to talk to them, how they decide, and their blind spots.

Then draft `me.md` (including *Where my data lives* from the Sources step) using the template headings and field labels (in English; the content in the owner's language). Show the whole draft. Save on yes. Set `status: active` and `last_updated`.

If something the owner said belongs to a specific area rather than to `me.md` (for example "always ask before touching my portfolio"), keep it in mind for Round 4.

## Round 3 — What's on the plate → write `now.md`

Use § Round 3. Get up to three focus items, open loops, and dated things coming up in the next 30 days. If a calendar, task board or email is connected, propose the dates and open loops from them first and let the owner confirm, drop or add. Keep small to-dos in their task tool, not in `now.md`.

Draft `now.md`. Show it. Save on yes.

## Round 4 — Choose areas

1. Based on what you heard, suggest 2–4 areas in one line (for example: investing, health, career, home and family, learning, personal finance, or something custom like "the house renovation"). Do this even if the owner already named one.
2. Ask which areas they want, then which one first (§ Round 4 has the options).
3. **Always update `areas/README.md` in this round.** Show the exact table rows for the areas they agreed to (and only those): status `planned`, or `empty` if the folder already exists, like `investing/`. Fill the `Set up next:` line under the table with the first area. Save on yes.
4. If you already heard things for an area they'll set up later (from Round 4 or earlier), offer to keep them in `inbox/<area-slug>-setup.md` in the owner's words, so the area interview doesn't have to ask again. Save on yes.
5. Do the **Finish** steps below.
6. Then, as a separate question, ask whether to start the `area-interview` for the first area now or later. `[options: Start now · Later]` Never bundle this with a save approval.

## Saving and resuming

- Show every file before saving. Save only on a yes. If you have git access, commit after each save: `core: interview round <n>`.
- **If the owner stops before the end, always offer a progress note**, even if they asked you not to save their answers. Put a `## Setup progress` section at the very top of `now.md`, right after the frontmatter, with: rounds done and the next question. When you show the note, ask whether to also keep the answers heard but not yet saved; add them only on yes, and never anything from the Never-store list. Save on yes.
- Remove the `## Setup progress` section in the same edit that finishes Round 4.

## Finish

When `me.md` and `now.md` are active and `areas/README.md` is updated:

1. Answer "What can you do for me?" yourself: offer three concrete things you can now do, each tied to something they told you.
2. Suggest two habits: say **"wrap up"** before closing a chat that mattered, and **"refresh"** every two weeks or so.
