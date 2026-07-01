# Project Config Files (.env.example, .gitignore, .claude/settings.local.json)

## Overview
Three small config files at the repo root / `.claude/`:

- **.env.example** — template for the real `.env`; currently just `OPENAI_API_KEY=`, consumed by [[skill-gpt-image-gen]].
- **.gitignore** — ignores `.env` so the real API key is never committed.
- **.claude/settings.local.json** — local, machine-specific Claude Code permission/settings overrides; untracked.

## Open Questions
- Confirm `.claude/settings.local.json` should stay untracked/gitignored rather than having any shared portion committed.

## Session Log

### 2026-06-30 — split file-by-file map into per-file vault notes [shipped]
- **What was done:** Pulled config-file documentation out of the consolidated `codebase-file-map.md` into its own topic note.
- **Decisions:** Grouped the three small config files into one note rather than three, since each is a few lines with no independent session history.
- **Notes / Caveats:** none.
- **Related:** [[codebase-file-map]], [[skill-gpt-image-gen]]
