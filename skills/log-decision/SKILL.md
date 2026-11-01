---
name: log-decision
description: Record a decision in decisions.md (and the area's journal), checking it first against the owner's own goals and rules and setting a review date. Use when the owner says "I decided…", "log this decision", "should I…?" about a real choice, or before an irreversible action in any area.
---

# Log a decision

**Goal:** every meaningful decision gets checked against the owner's own rules and written down with a review date, so later they can learn from what actually happened instead of what they remember.

## 1. Understand the decision

Ask only what you can't infer:

- What exactly are you deciding (or did you decide)?
- What were the other options, including doing nothing?
- Which area is it in?

## 2. Check it against the files

Read the area's `goals.md` and `rules.md`, and the latest 20 entries of its `journal.md` and of `decisions.md`, looking for anything similar.

Tell the owner, in at most five lines:

- **Serves:** which goal this helps.
- **Rule check:** which rules it follows, and which it bends or breaks. Quote the rule.
- **Seen before:** a similar past decision and how it turned out, if any.
- **Reversibility:** easy to undo, or not.

Do not tell them what to decide, even if they ask you to. If a rule is broken, say so once, plainly, and end your message with one question: `[options: Go ahead anyway · Change the decision · Change the rule]` Wait for the answer before asking for any entry fields.

If the decision is still open and they want help thinking, offer the `prompts/devils-advocate.md` prompt first.

## 3. Write the entry

Draft an entry in the format at the top of `decisions.md`. Ask for the fields people skip, one per message:

1. "How will you know it worked?"
2. "When should we look at it again?" Suggest dates: about a month for small decisions, three to six months for bigger ones. `[options: <date in 1 month> · <date in 3 months> · <date in 6 months>]`
3. "How confident are you?" `[options: 1 · 2 · 3 · 4 · 5]`, then "How are you feeling about it?" `[options: Calm · Excited · Anxious · FOMO · Other]`. Mood matters: it's what pattern-spotting runs on.

Leave the `Outcome:` line empty; it is filled in at review. Show the entry. On yes, add it at the top of the entries in `decisions.md` and set its `last_updated`. If you don't know today's date, ask.

## 4. Area-specific follow-ups

- **Investing:** also add an entry to `areas/investing/journal.md` in its format. If it changes a holding, offer to update `status.md` now (or, if the trade hasn't happened yet, add an open loop to `now.md` to update it). If it's a new position, offer to create a thesis from `theses/_thesis-template.md`; if it adds to, trims or sells an existing position, add a dated line to that thesis's review log.
- **Any area:** if the decision changes a goal or a rule, offer to update that file too. If it answers a focus item in `now.md`, offer to update `now.md`.

Each of these is a separate change: show it and save on yes.

## 5. Close

- If you have git access: commit `decision: <one-line summary>`.
- One line back: what was logged and the review date.
