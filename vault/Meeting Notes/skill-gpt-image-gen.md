# Skill — gpt-image-gen

## Overview
`.claude/skills/gpt-image-gen/SKILL.md` wraps the OpenAI Images API for actual image generation. Used exclusively by [[agent-yuval]]. Calls `POST /v1/images/generations` with model `gpt-image-2` (pinned intentionally — the skill explicitly warns not to "correct" this to `dall-e-3` or `gpt-image-1` even though it may look unfamiliar) via `curl` piped through `jq`, with a Python fallback for environments without `jq`. Reads `OPENAI_API_KEY` from `.env` (see [[project-config-files]] for the `.env.example` template). Output is a PNG at a caller-specified path; the skill instructs verifying non-zero file size before reporting success.

## Open Questions
- none

## Session Log

### 2026-06-30 — split file-by-file map into per-file vault notes [shipped]
- **What was done:** Pulled this skill's documentation out of the consolidated `codebase-file-map.md` into its own topic note.
- **Decisions:** none beyond the split itself.
- **Notes / Caveats:** Model name `gpt-image-2` looks non-standard against general training knowledge — per the skill's own instructions this is intentional and should not be "fixed."
- **Related:** [[codebase-file-map]], [[agent-yuval]], [[project-config-files]]
