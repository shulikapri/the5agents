# Yuval's Asset Folders (yuval/reference/, yuval/outputs/)

## Overview
Two working folders for [[agent-yuval]]:

- **yuval/reference/** — style-reference images Yuval scans before generating, to keep visual consistency across the project. Currently empty (only a `.gitkeep` placeholder) — no baseline style established yet.
- **yuval/outputs/** — generated images land here as `<YYYY-MM-DD>-<slug>.png`, each paired with a `<same-slug>.txt` file containing the exact prompt used (for future iteration). Currently contains `2026-06-30-horse.png` + `2026-06-30-horse.txt`, plus a `.gitkeep` placeholder.

## Open Questions
- `yuval/reference/` has no images yet — first real generation request will have nothing to draw consistency cues from.

## Session Log

### 2026-06-30 — split file-by-file map into per-file vault notes [shipped]
- **What was done:** Pulled Yuval's asset-folder documentation out of the consolidated `codebase-file-map.md` into its own topic note.
- **Decisions:** Grouped `reference/` and `outputs/` into one note rather than one-per-file, since the individual files inside (`.gitkeep`, single PNG/TXT pair) aren't independently meaningful topics on their own.
- **Notes / Caveats:** none.
- **Related:** [[codebase-file-map]], [[agent-yuval]], [[skill-gpt-image-gen]]
