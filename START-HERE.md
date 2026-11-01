# Start here

Pick the path that matches how you use AI. All three end the same way: the assistant interviews you and fills in your files. You choose between a full setup (about 20 minutes, starting with your normal week) and a quick start (about 5 minutes, then straight into one area such as investing; finish the rest later).

## Step 0 — Make your own private copy

1. On this template's GitHub page, click **Use this template** → **Create a new repository**. **Don't use Fork:** a fork of a public repo can't be made private. (On a phone the button may be hidden; use a computer for this one step.)
2. Name it, for example, `firstname-digimina`.
3. Choose **Private**. Click **Create repository**.

## Optional — connect your tools first

The interview asks which tools hold your data (calendar, email, a task board, a portfolio tracker, a training app) and whether the numbers should live in this repo or stay in those tools. If they're connected in your assistant before you start (in Claude: **Settings → Connectors**), the assistant reads them and asks you only to confirm, which makes the interview shorter. You can also connect them later.

## Path A — Claude Code, Codex or another agent with file access

The smoothest path: the assistant reads and saves files itself, and every change lands in git history.

1. Clone your new repo and open the folder in the agent.
2. Say: **"Read AGENTS.md and interview me."**

Claude Code reads `CLAUDE.md`, which points to `AGENTS.md`. That's enough: AGENTS.md tells the assistant to open the skill files directly.

*Optional:* to make the skills show up as Claude Code skills, copy them into place:

```
mkdir -p .claude && cp -r skills .claude/skills
```

If you do this, repeat the copy when you update a skill.

## Path B — Claude or ChatGPT in the app, with a Project

Works on any device. The catch: **the app can read your repo but can't save to it.** The assistant shows you each change, and you paste it into GitHub yourself.

1. Create a Project in Claude or ChatGPT.
2. Add your repo to the Project's files through the app's GitHub connection.
3. Copy the block in [PROJECT-INSTRUCTIONS.md](PROJECT-INSTRUCTIONS.md) into the Project's instructions.
4. Start a chat in the Project and paste the prompt below.
5. When the assistant shows a change:
   1. Open that file on github.com and click the pencil icon (**Edit**).
   2. Paste the change and click **Commit changes**.
   3. Back in the Project, re-sync the GitHub files (in Claude: **Sync now**) so the next chat sees the update.

Tip: let the assistant collect several changes and paste them in one go at the end ("wrap up").

## Path C — No GitHub at all

1. Download the template as a ZIP (**Code** → **Download ZIP**), unzip it, and keep the folder somewhere you back up.
2. Create a Project in Claude or ChatGPT and upload **every `.md` file** from the folder to the Project's files (the skills need their question banks).
3. Copy the block in [PROJECT-INSTRUCTIONS.md](PROJECT-INSTRUCTIONS.md) into the Project's instructions, start a chat, and paste the prompt below.
4. When the assistant shows a change, paste it into the file on your computer, then upload the updated file to the Project again (replacing the old one).

You lose the automatic history, but everything else works the same.

## The prompt to paste

```
This chat has access to my personal context repository.
1. Read AGENTS.md and follow it.
2. If me.md is still empty, run the context-interview skill
   (skills/context-interview/SKILL.md) with me now.
3. Ask one question at a time and tell me what kind of answer you want.
4. Show me every change before you save it. If you can't save
   files yourself, give me the full text to paste and say which file.
```

## After setup

- New topic, new chat. The assistant reads your files each time, so nothing is lost.
- Say **"wrap up"** before you close a chat that had something worth keeping.
- Every two weeks (at least monthly), say **"refresh"**.
- Keep personal rules in `me.md` or an area's `rules.md`, not in `AGENTS.md`. Then template updates can replace AGENTS.md without touching your data (see README, *Updating*).
