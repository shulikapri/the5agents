# Agent — Yael (Content Writer)

## Overview
`.claude/agents/yael.md` defines Yael, the team's content writer. Tools: Read, Write, Edit, Glob, Grep — no Bash/WebSearch/API access. Her workflow: pull a raw article from `Content/` → read [[yael-style-guide]] (and `yael/reference/` examples, if present) → rewrite it in house style, inserting `{{IMAGE_NEEDED: "..."}}` placeholders at points that need an image → save both `<name>.md` and `<name>.html` to `Output/` → report back to Reuven with a summary and the list of image placeholders so he can dispatch Yuval. Hard rule: she must strip any CTAs/links to the original author's blog/newsletter, but in-story brand mentions (e.g. "I use Notion") stay as-is.

## Open Questions
- `yael/reference/` is referenced in her workflow but doesn't exist yet in the repo — create with starter examples, or leave until she needs it?

## Session Log

### 2026-06-30 — split file-by-file map into per-file vault notes [shipped]
- **What was done:** Pulled Yael's agent-definition documentation out of the consolidated `codebase-file-map.md` into its own topic note.
- **Decisions:** Carried forward the open question about the missing `yael/reference/` folder from the original map rather than resolving it unilaterally.
- **Notes / Caveats:** none.
- **Related:** [[codebase-file-map]], [[yael-style-guide]], [[content-folder]], [[output-folder]], [[claude-md-root-config]]
