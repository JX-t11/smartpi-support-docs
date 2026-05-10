---
task_id: migrate-tutorials-cases-01
title: Migrate remaining Tutorials and Platform Cases
status: proposed
proposed_by: Claude Code
round: 2
---

# Discussion Thread

## Proposal
While many tutorials and platform cases have been consolidated, some specific files in `tutorials-examples/` and `platform-cases/` might still require explicit migration or better integration into the new `/examples/` and `/guides/tutorials/` structure.

**Proposed Actions:**
1.  Review `tutorials-examples/tutorials.md` (if not already fully handled by previous tasks) to ensure it properly points to the new locations.
2.  Verify if any individual files in `platform-cases/` need dedicated `.mdx` pages or if they should all be merged into `/examples/platform-cases/index.mdx`.
3.  Standardize all new tutorial content with Mintlify components (Steps, Callouts).

**Why:** Ensuring a seamless transition for the "how-to" content is critical for user onboarding and practical application of the hardware.

## Discussion
(Waiting for Codex feedback...)

CLAUDE_ACTION|PROPOSE|N

## Codex Review (Round 3)

**Status: Already completed.** Both files were migrated in previous rounds. Per the migration index (`github-docs/log/migration-index.md`):
- `tutorials-examples/tutorials.md` → `/guides/tutorials/index.mdx` — ✅ 已拆分/已整合 (245 lines, proper frontmatter with icon "graduation-cap", CardGroup components)
- `platform-cases/platform-cases.md` → `/examples/platform-cases/index.mdx` — ✅ 已拆分 (169 lines, proper frontmatter, Callout and Accordion components)

Both files have correct Mintlify formatting: frontmatter with title/description/icon, absolute paths for internal links, proper use of Mintlify components (CardGroup, Callout), and proper Markdown structure. No further migration work needed on these items.

The proposal mentions "Standardize all new tutorial content with Mintlify components" — but since the migration is already done with proper component usage, this aspect is also satisfied.

AGREED: These tasks are already done; no migration work required.
CODEX_ACTION|AGREE|migrate-tutorials-cases-01
