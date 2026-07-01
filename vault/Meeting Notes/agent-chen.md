# Agent — Chen (Research)

## Overview
`.claude/agents/chen.md` defines Chen, the team's web researcher. Tools: WebSearch, WebFetch, Read, Write, Edit, Glob, Grep — no Bash, so she can't call external APIs directly. Her workflow: receive a topic from Reuven → check [[chen-search-log]] for a duplicate search in the last 30 days → search and filter sources by her quality criteria (primary sources, reputable publications, recent dates, Hebrew preferred when relevant) → save the chosen content to `Content/<YYYY-MM-DD>-<slug>.md` → log the search → report back to Reuven with filename, summary, and source link. Architecturally she never invokes Yael directly — Reuven decides whether to chain into a rewrite.

## Open Questions
- none

## Session Log

### 2026-06-30 — split file-by-file map into per-file vault notes [shipped]
- **What was done:** Pulled Chen's agent-definition documentation out of the consolidated `codebase-file-map.md` into its own topic note.
- **Decisions:** Linked directly to [[chen-search-log]] (her memory file) and [[content-folder]] (where her output lands) rather than re-describing them here, to keep this note focused on the agent definition itself.
- **Notes / Caveats:** none.
- **Related:** [[codebase-file-map]], [[chen-search-log]], [[content-folder]], [[claude-md-root-config]]
