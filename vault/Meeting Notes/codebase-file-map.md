# Codebase File Map

## Overview

This topic is the master **index** for every file in the the5agents repo. Each file/component now has its own dedicated topic note (split out 2026-06-30 per explicit user request to apply the vault workflow to every file individually); this note just summarizes the pipeline shape and points to the detail notes. The project is a multi-agent content team orchestrated by Reuven (the root [[claude-md-root-config]]), with three specialist sub-agents — Chen (research), Yael (writing), Yuval (images) — each owning a working folder and an agent definition. Data flows one-directional: Chen's research → `Content/` raw drafts → Yael's rewrite → `Output/` final MD+HTML, with Yuval's images optionally embedded along the way.

### File index

- Root/orchestration: [[claude-md-root-config]], [[project-config-files]]
- Chen: [[agent-chen]], [[chen-search-log]]
- Yael: [[agent-yael]], [[yael-style-guide]] (Brand Guidelines)
- Yuval: [[agent-yuval]], [[skill-gpt-image-gen]], [[yuval-asset-folders]]
- Pipeline data: [[content-folder]], [[output-folder]]
- Skills: [[skill-gpt-image-gen]], [[skill-obsidian-suite]]

### Vault (`vault/`)

- **vault/Meeting Notes/** and **vault/Brand Guidelines/** — this vault itself; see each folder's `_index.md` for the full topic list.
- **.obsidian/** — Obsidian app's own config folder for browsing this vault (untracked, editor-local, not project logic).

## Open Questions

- `yael/reference/` is mentioned in Yael's agent file but doesn't exist yet in the repo — should it be created with starter examples, or left until Yael actually needs it?
- Should `Content/article1.txt` / `Output/article1.*` (the pre-Chen-convention sample files) be kept as a fixture, renamed to match the dated-slug convention, or removed?
- `.claude/settings.local.json` and `.obsidian/` are untracked — confirm whether they should stay gitignored (machine-local) or if any of their contents need to be shared via git.

## Session Log

### 2026-06-30 — initial full-repo file map [shipped]
- **What was done:** Read every tracked and untracked file in the repo (CLAUDE.md, all three agent defs, all skill defs, style guide, search log, env/gitignore) and produced this single reference topic documenting what each file does, which agent owns it, and how files connect across the Chen → Content/ → Yael → Output/ pipeline (with Yuval's images/`yuval/` folder feeding in separately).
- **Decisions:** Used one consolidated topic file rather than one file per repo file — the repo is small enough (≈20 files) that a single map is more useful for orientation than 20 tiny stubs would be; per-file detail is captured as subsections instead. Placed it under `vault/Meeting Notes/` since this is an architecture/structure documentation task. Per explicit user instruction, the `obsidian-vault-workflow` skill is now to be invoked at the start of every session/command going forward, not just for this task.
- **Notes / Caveats:** This map reflects repo state as of 2026-06-30; some files (yuval outputs, mondial Output files, `.claude/skills/obsidian-*`) are currently untracked in git. If files are added/renamed/removed, this map should be refreshed rather than left stale.
- **Related:** none (first entry on this topic)

### 2026-06-30 — split into one topic note per file [shipped]
- **What was done:** Per explicit user request ("use the obsidian-vault-workflow skill for all the files in the project"), split this consolidated map into a dedicated topic note per file/component: [[claude-md-root-config]], [[agent-chen]], [[agent-yael]], [[agent-yuval]], [[skill-gpt-image-gen]], [[skill-obsidian-suite]], [[chen-search-log]], [[content-folder]], [[output-folder]], [[yuval-asset-folders]], [[project-config-files]], and [[yael-style-guide]] (filed under Brand Guidelines). This note is now an index only.
- **Decisions:** Grouped trivially small/related files into one note where a standalone note would add no value (e.g. `.env.example`+`.gitignore`+`settings.local.json` → one [[project-config-files]] note; the three Obsidian skills → one [[skill-obsidian-suite]] note; Yuval's `reference/`+`outputs/` folders → one [[yuval-asset-folders]] note), rather than literally one file per filesystem entry.
- **Notes / Caveats:** Open Questions that were specific to a sub-area were moved to that area's own note (see [[agent-yael]], [[content-folder]], [[project-config-files]], [[yuval-asset-folders]], [[yael-style-guide]]) rather than staying duplicated here.
- **Related:** [[claude-md-root-config]], [[agent-chen]], [[agent-yael]], [[agent-yuval]], [[skill-gpt-image-gen]], [[skill-obsidian-suite]], [[chen-search-log]], [[content-folder]], [[output-folder]], [[yuval-asset-folders]], [[project-config-files]], [[yael-style-guide]]
