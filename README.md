# Project scaffold

Sets up a new project folder so every future Claude or Codex session starts with the goal, the rules and the current state.

**Type:** Claude Code skill · **Area:** General skills

## What it does

- Asks five short questions: the goal, the dates, what Claude must never do, sensitive facts and how they may be used, and the working rhythm.
- Creates CLAUDE.md (goal, standing rules, sensitive-data rules, current context, related projects), an AGENTS.md pointer for Codex, a newest-first memory.md, and a live checklist or master prompt.
- Wires scheduled tasks to read CLAUDE.md first, and keeps stable rules in CLAUDE.md and the dated log in memory.md.

## Guardrails

- Asks before creating anything; never overwrites or deletes an existing file.
- Never copies sensitive personal facts into project files; points to where they live instead.

## When it triggers

> Set up a new project folder so every future Claude or Codex session starts with the right context - a CLAUDE.md with the goal, standing rules and sensitive-data rules, a newest-first memory.md, a live checklist or master prompt, an AGENTS.md pointer for Codex, and a "start every session by reading X" line. Use when the user starts a new long-running project, says "make a project for this", or a piece of work has outgrown one chat.

## What's in this repo

- `SKILL.md`: the skill itself, the file Claude or Codex reads.
- Written to be generic: where the skill relies on the user's own files, it names them by role, not by content.

## Install

```bash
mkdir -p ~/.claude/skills/project-scaffold
curl -fsSL https://raw.githubusercontent.com/adiyt4soni/project-scaffold/main/SKILL.md -o ~/.claude/skills/project-scaffold/SKILL.md
```
