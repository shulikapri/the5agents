# CLAUDE.md — Root Orchestration Config

## Overview
`CLAUDE.md` (repo root) is Reuven's (the CEO agent's) instruction file — the entry point Claude Code reads automatically for this project. It defines the team roster and per-agent trigger keywords (Hebrew + English), and specifies the two coordination workflows Reuven runs: "article with images" (chains Yael then Yuval over an existing `Content/` draft) and "new content from the web" (chains Chen → optionally Yael → optionally Yuval, stopping after Chen if the request was research-only). It also documents the folder layout (`.claude/agents/`, `.claude/skills/`, `yael/`, `yuval/`, `chen/`, `Content/`, `Output/`).

## Open Questions
- none

## Session Log

### 2026-06-30 — split file-by-file map into per-file vault notes [shipped]
- **What was done:** Extracted CLAUDE.md's own documentation out of the consolidated `codebase-file-map.md` into this standalone topic note, per user request to use the vault workflow for every file individually.
- **Decisions:** Kept this note scoped to CLAUDE.md only — the two workflows it defines (image-article, web-research) are referenced here but the agents that execute them have their own notes ([[agent-chen]], [[agent-yael]], [[agent-yuval]]) rather than duplicating their detail here.
- **Notes / Caveats:** This file is the authoritative source; if CLAUDE.md's workflows change, update this Overview to match.
- **Related:** [[codebase-file-map]], [[agent-chen]], [[agent-yael]], [[agent-yuval]]
