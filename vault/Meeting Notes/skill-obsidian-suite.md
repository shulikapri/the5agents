# Skills — Obsidian Suite (bases, markdown, vault-workflow)

## Overview
Three skills pulled from [ZeremItay/the-5-agents-obsidian](https://github.com/ZeremItay/the-5-agents-obsidian) into `.claude/skills/`, giving the project Obsidian-vault capabilities:

- **obsidian-bases** — creates/edits Obsidian `.base` database views (filters, formulas, summaries). Not yet used in this project's `vault/`.
- **obsidian-markdown** — Obsidian-flavored Markdown syntax reference (wikilinks, embeds, callouts, properties, frontmatter).
- **obsidian-vault-workflow** — the mandatory read/write protocol that governs everything under `vault/`: one Markdown file per topic, each with an Overview, an Open Questions block, and an append-only dated Session Log, cross-linked via `[[wikilinks]]` and indexed per-folder via `_index.md`. This is the skill that produced every note in this vault, including this one.

## Open Questions
- none

## Session Log

### 2026-06-30 — installed from external repo [shipped]
- **What was done:** Cloned the source repo and copied all three skill folders into `.claude/skills/`.
- **Decisions:** Installed as-is, matching this project's existing flat `.claude/skills/<name>/SKILL.md` convention.
- **Notes / Caveats:** Repo isn't connected via the GitHub app integration for this account (404 on `add_repo`); cloned via plain `git clone` over a public HTTPS URL instead.
- **Related:** none (first entry on this topic)

### 2026-06-30 — split file-by-file map into per-file vault notes [shipped]
- **What was done:** Pulled the Obsidian-suite documentation out of the consolidated `codebase-file-map.md` into this standalone topic note; also began applying obsidian-vault-workflow per-file across the whole repo per explicit user instruction.
- **Decisions:** Kept all three Obsidian skills as one note rather than three, since they were installed together as a set and obsidian-bases/obsidian-markdown have no independent activity yet — will split if either grows its own session history.
- **Notes / Caveats:** User has asked for `obsidian-vault-workflow` to be invoked at the start of every session/command in this project going forward (saved as a standing memory outside this vault).
- **Related:** [[codebase-file-map]], [[claude-md-root-config]]
