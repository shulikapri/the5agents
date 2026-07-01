# Agent — Yuval (Image Designer)

## Overview
`.claude/agents/yuval.md` defines Yuval, the team's image designer. Tools: Read, Write, Bash, Glob — Bash is required to call the image-generation API. His workflow: scan `yuval/reference/` for recurring style/color/composition cues → build a prompt blending the request with that style → invoke the [[skill-gpt-image-gen]] skill → save the PNG to `yuval/outputs/<YYYY-MM-DD>-<slug>.png` plus a matching `.txt` file with the exact prompt used → verify the output file exists and is non-empty → report what was created, the path, and which reference images influenced it. His stated goal is visual consistency across every image the project produces.

## Open Questions
- `yuval/reference/` is currently empty (only `.gitkeep`) — no style baseline exists yet for consistency checks.

## Session Log

### 2026-06-30 — split file-by-file map into per-file vault notes [shipped]
- **What was done:** Pulled Yuval's agent-definition documentation out of the consolidated `codebase-file-map.md` into its own topic note.
- **Decisions:** none beyond the split itself.
- **Notes / Caveats:** none.
- **Related:** [[codebase-file-map]], [[skill-gpt-image-gen]], [[yuval-asset-folders]], [[claude-md-root-config]]
