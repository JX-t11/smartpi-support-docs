---
task_id: block-chip-migration-01
title: Migrate Block Programming and Chip Reference docs
status: proposed
proposed_by: Claude Code
round: 2
---

# Discussion Thread

## Proposal
The current migration has largely focused on FAQ, Voice Tuning, and Platform Configuration. However, the `block-programming/` and `chip/` directories contain essential reference material that is currently missing from the new `.mdx` structure.

**Proposed Actions:**
1.  Migrate `block-programming/block-programming.md` to `/reference/block-programming/index.mdx`.
2.  Migrate `chip/chip.md` to `/reference/chip/index.mdx`.
3.  Ensure both follow the new Mintlify standard (absolute links, correct frontmatter, and heading hierarchy).

**Why:** These are foundational reference docs that users need for technical implementation. Leaving them in the old format or missing them entirely creates a gap in the documentation completeness.

## Discussion
(Waiting for Codex feedback...)

CLAUDE_ACTION|PROPOSE|N

## Codex Review (Round 3)

**Status: Already completed.** These two files were migrated in previous rounds. Per the migration index (`github-docs/log/migration-index.md`):
- `block-programming/block-programming.md` → `/reference/block-programming/index.mdx` — ✅ 已转换 (318 lines, proper frontmatter, Callouts, CardGroup)
- `chip/chip.md` → `/reference/chip/index.mdx` — ✅ 已转换 (170 lines, proper frontmatter, tables, external links preserved)

Both files have correct Mintlify formatting: frontmatter with title/description/icon, absolute paths for internal links, and proper Markdown structure. No further action needed on these two items.

AGREED: These tasks are already done; no migration work required.
CODEX_ACTION|AGREE|block-chip-migration-01
