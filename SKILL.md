---
name: project-scaffold
description: Set up a new project folder so every future Claude or Codex session starts with the right context - a CLAUDE.md with the goal, standing rules and sensitive-data rules, a newest-first memory.md, a live checklist or master prompt, an AGENTS.md pointer for Codex, and a "start every session by reading X" line. Use when the user starts a new long-running project, says "make a project for this", or a piece of work has outgrown one chat.
---

# Project scaffold

The point is that a session starting cold reads two files and
knows the goal, the rules and where things stand.

## 0. Rules
- Ask before creating anything. Show the folder name and the file list first.
- Never copy sensitive personal facts into the project files. Point to where they live instead, and write handling
  rules for them.
- Never delete or overwrite an existing file; if the folder exists, add only what is missing.

## 1. Ask (one short batch)
1. The goal in one or two sentences, and what "done" looks like.
2. Deadlines or dates that matter.
3. What Claude must never do in this project (send, submit, buy, sign up, delete, give medical or financial advice...).
4. Sensitive facts involved and how they may be used.
5. The working rhythm: one-off, daily, scheduled tasks?

## 2. Create
```
<project>/
  CLAUDE.md        goal, standing rules, sensitive-data rules, current context, related projects
  AGENTS.md        one-line pointer to CLAUDE.md, plus Codex-only notes
  memory.md        dated session log, newest first
  <checklist>.md   the live checklist (or MASTER-PROMPT.md for repeated runs)
```

### CLAUDE.md
```markdown
# CLAUDE.md: <project>

<Goal in two sentences. Who it is for and what done looks like.>

**Start every session by reading `<checklist>.md` and the top of `memory.md`.**

## Standing rules
- <Who does sign-ups, sends and submissions: the user, never Claude.>
- Primary sources only for official steps; stamp each with the page and the date checked.
- Status on every item: OPEN / IN PROGRESS / DONE / BLOCKED, with a date and an owner. Mark items done; never delete.
- If anything unexpected happens, stop and report.

## Sensitive facts: handling rules
- <Where they live (outside this folder), and which may appear in drafts or forms.>

## Current context (update as it changes)
- <Dated facts that change: where things stand, what is waiting on whom.>

## Related
- <Sibling projects and the files that connect them.>
```

### memory.md
```markdown
# memory.md: <project> (newest first)

## YYYY-MM-DD: <one-line headline> (<which assistant>)
- What happened and what was decided.
- **OPEN (owner, YYYY-MM-DD):** anything left.
```

### Checklist or master prompt
- **Checklist** for admin-style projects: one row per item with status, owner, date and the primary source.
- **Master prompt** for projects with repeated runs: parameters, absolute rules, method step by step, output files,
  and a status block at the top that is updated each run.

## 3. Wire it up
- If the user runs scheduled tasks, each task prompt starts with the project folder path and "read CLAUDE.md first".
- At the end of every meaningful session, append a dated entry to `memory.md`. Stable rules go in CLAUDE.md, not
  the log.
- When a fact changes, update its canonical file first, then any copy, in the same pass.

## 4. Check
List the created files with `ls -la`, show the first lines of CLAUDE.md, and confirm nothing was overwritten.
