# digimina

*Estonian for "the digital me". A personal context template for AI assistants.*

**A small, private repo that tells any AI who you are.** A short core about you, plus the life areas you add as you go (investing, health, career, home…). You don't fill it in by hand: the AI interviews you and writes the files.

Every AI conversation normally starts from zero. You explain your situation again, and you still get generic answers. This repo fixes that. Your assistant reads a few files at the start of each conversation, and its answers fit your actual life.

## Why this one

There are good context templates out there already (see *Credits*). This one combines four ideas:

1. **Core + areas.** Three core files that are always read, plus any number of life areas. Every area has the same four files (`goals`, `rules`, `status`, `journal`), so the AI navigates all of them the same way and you can add a new area in a minute.
2. **Filled by interview.** Skills in `skills/` tell the AI how to interview you: the core first, then one area at a time, each with its own question bank. Adding a new kind of area means adding one question bank.
3. **Decisions are first-class.** A shared `decisions.md` log with review dates, and an append-only journal per area. Git history keeps an honest record of what you actually thought, not what you remember thinking.
4. **Works with any assistant.** Plain Markdown. `AGENTS.md` is the entry point most AI tools understand; `CLAUDE.md` points to it. No app, no lock-in.

## What's inside

```
digimina/
├── AGENTS.md            ← the AI reads this first: read order, rules, skills
├── CLAUDE.md            ← points Claude Code to AGENTS.md
├── START-HERE.md        ← how to start, with a prompt to paste
├── PROJECT-INSTRUCTIONS.md ← paste into a Claude or ChatGPT Project
├── me.md                ← who you are, how you want to be talked to
├── now.md               ← this month's focus and open loops
├── decisions.md         ← every important decision, with a review date
├── areas/
│   ├── README.md        ← list of your areas
│   ├── _template/       ← the four-file skeleton for a new area
│   └── investing/       ← a ready-made area with theses and a watchlist
├── prompts/             ← reusable prompts (weekly review, daily brief, monthly metrics, devil's advocate…)
├── AUTOMATE.md          ← run prompts on a schedule (brief, review, metrics)
├── skills/              ← interview and upkeep procedures for the AI
│   ├── context-interview/  ← first-time setup of the core
│   ├── area-interview/     ← add and fill any area (+ question banks)
│   ├── context-refresh/    ← find stale files and update them
│   └── log-decision/       ← record a decision and check it against your rules
├── inbox/               ← drop raw notes here; the AI sorts them later
└── private/             ← never committed (see .gitignore)
```

## Get started

See [START-HERE.md](START-HERE.md). In short:

1. Click **Use this template** → **Create a new repository** → choose **Private**. (Not *Fork*: forks of a public repo can't be private.)
2. Connect the repo to your AI assistant (or open it in Claude Code or another agent).
3. Say: **"Read AGENTS.md and interview me."**

Choose a **full setup** (about 20 minutes for the core, then 10–20 minutes per area) or a **quick start** (about 5 minutes, then straight into one area). You can stop any time and continue later. Where your tool supports it (for example Claude Code), simple questions come with clickable options.

## Everyday use

| You say | What happens |
|---|---|
| "What can you do for me?" | Three concrete offers based on your files |
| "Add an area for health" | A short interview creates and fills `areas/health/` |
| "I decided to …" | The decision is checked against your rules and logged |
| "Refresh" (every two weeks or so) | The AI finds files that are out of date and asks what changed |
| "Wrap up" | Before you close the chat: what from this conversation is worth saving |
| "Weekly review", "Daily brief", "Monthly metrics", "Devil's advocate on …" | Runs the matching prompt in `prompts/` |
| "Automate the daily brief" | Sets up a scheduled task, following `AUTOMATE.md` |

The AI always shows you what it wants to change and saves only after you say yes. In the Claude or ChatGPT app it can read your repo but not write to it, so it gives you the text and you paste it in (see START-HERE, Path B).

## Privacy

- Keep the repo **private**. It is your personal data.
- `AGENTS.md` has a **Never store** list: passwords, ID codes, account and card numbers, other people's health details. The AI is told not to write these down.
- Anything you want on disk but never on GitHub goes in `private/`, which git ignores. It is not a vault: real secrets belong in a password manager.
- Git remembers deleted files. Strip account numbers and ID codes before anything is committed.
- Whatever you connect to an AI assistant is shared with that provider. Store percentages instead of balances when that's enough.

## Updating

The template will get new skills and fixes. Files fall into two groups:

| Template files (safe to replace) | Your files (never overwritten) |
|---|---|
| `AGENTS.md`, `CLAUDE.md`, `START-HERE.md`, `PROJECT-INSTRUCTIONS.md`, `README.md`, `AUTOMATE.md`, `skills/`, `prompts/`, `areas/_template/`, `areas/investing/theses/_thesis-template.md` | `me.md`, `now.md`, `decisions.md`, everything else in `areas/`, `inbox/`, `private/` |

Your template version is in the frontmatter of `AGENTS.md`; changes are listed in [CHANGELOG.md](CHANGELOG.md). To update, open your repo in an agent with file access and say:

> Update my template files from https://github.com/ilves/digimina. Compare only the template files, show me the changes, and don't touch my own files.

Keep your personal rules in `me.md` or an area's `rules.md`, not in `AGENTS.md`, so an update never overwrites them.

## Credits

Ideas borrowed with thanks from:

- [Telos](https://github.com/danielmiessler/Telos) and [Personal AI Infrastructure](https://github.com/danielmiessler/Personal_AI_Infrastructure) by Daniel Miessler: deep, structured personal context.
- [ai-context-template](https://github.com/AronCorp/ai-context-template) by AronCorp: let the assistant interview you instead of handing you blank files.
- [ME.md](https://mager.co/blog/2026-03-07-memd-portable-human-context/) and [DOUG.md](https://blog.dougbelshaw.com/doug-md/): one portable file that tells AI who you are.
- The `AGENTS.md` convention for agent instructions.

## License

MIT. See [LICENSE](LICENSE).
