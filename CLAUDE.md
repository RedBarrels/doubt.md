# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

doubt.md is a 7-gate self-interrogation framework for evaluating engineering projects before building them. It is pure markdown — no build system, no dependencies, no runtime.

## Architecture

- **DOUBT.md** — Index file linking all 7 gates
- **01-07 gate files** — Each gate has checklists, critical questions, traps to avoid, and PASS/CONDITIONAL/FAIL scoring criteria
- **templates/DOUBT-SESSION.md** — Fill-in template users copy per project
- **examples/** — Completed doubt sessions for reference
- **.claude/skills/doubt/** — Self-contained Claude Code skill (`/doubt`) that runs the full framework as an interactive session

The 7 gates in order: Originality → Necessity → Effectiveness → Engineering → Security → Cost → Approach.

## The `/doubt` Skill

The skill at `.claude/skills/doubt/` is self-contained (SKILL.md + gates.md + template.md) so it can be copied to `~/.claude/skills/doubt/` and used from any project. When editing the skill, keep it independent of the repo file structure — it must not reference files outside its own directory.

## Conventions

- Gate files use Obsidian `[[wikilinks]]` for cross-linking
- Scoring is always PASS / CONDITIONAL / FAIL — no other values
- 2+ FAILs = NO-GO verdict on a session
- "Do nothing" must always appear as an alternative in Gate 7
- Tone is direct and skeptical, not cruel — the framework challenges ideas, not people
