---
task_id: CRITICAL-02
title: "practice-tutorial.mdx 文件缺失 — docs.json 和多个页面引用"
status: proposed
proposed_by: Claude Code
round: 1
priority: critical
severity: critical
---

## Problem Summary

The file `docs/guides/ai-agents/practice-tutorial.mdx` does not exist on disk, but it is referenced from multiple sources:

- **docs.json** line 72 — listed in the "智能体开发" nav group under "智能体开发" tab
- **guides/ai-agents/index.mdx** line 78 — Card component with href="/guides/ai-agents/practice-tutorial"
- **guides/ai-agents/get-started.mdx** line 261 — Card component with href="/guides/ai-agents/practice-tutorial"

## Impact

- The nav group shows a "实践教程" card that links to a dead page
- Mintlify will show a broken link/error for this nav entry
- Users clicking the practice tutorial link will get a 404

## Proposed Resolution

1. **Create practice-tutorial.mdx** — This should be a hands-on tutorial for AI Agent development, likely covering two projects: device manual Q&A and device control integration.
2. If you don't have the content to create this page right now, it needs to be **removed from docs.json and all Card references** until it's written.

## Recommendation

Create the missing file with proper frontmatter (title, description, icon). The content should cover practical exercises for AI Agent development, such as:
- Exercise 1: Building a device manual Q&A bot
- Exercise 2: Controlling hardware via MCP tools

--- Codex Response — Round 2 ---
last_speaker: Codex
round: 2

AGREED: I agree this task should proceed. The practice-tutorial.mdx file is referenced in docs.json (line 72) and two MDX files but doesn't exist, causing broken links.

Two options:
- Option A: Create the page with content based on existing source material from smartpi-docs/docs/ai-agents/ if similar tutorials exist there
- Option B: Remove references from docs.json and Card components until the page is written

I recommend Option A — let me check if there's tutorial-like content in the old MkDocs that could be adapted. If not, we go with Option B to avoid broken links.


Update: Found existing tutorial content at `/workspace/smartpi-docs/docs/ai-agents/tutorial.md` titled "智能体平台实践教程". This covers:
- Creating an agent for device manual Q&A (实战 1)
- Knowledge base setup and binding (实战 2)
- Device control via MCP plugins (实战 3)

I recommend creating practice-tutorial.mdx using this existing content as source, adapting to Mintlify MDX format. This is preferable to removing references from docs.json.


--- Execution Summary by Codex ---
last_speaker: Codex

EXECUTED: Created docs/guides/ai-agents/practice-tutorial.mdx (134 lines) from source content at /workspace/smartpi-docs/docs/ai-agents/tutorial.md.

**Conversion changes:**
- Frontmatter: title + description preserved, icon removed (Mintlify uses its own system)
- Internal links: `./get-started.md` → `/guides/ai-agents/get-started` (absolute path)
- Image references converted from `./img/coze-os-*-*.png` to `/images/ai-agents/ai-agent-*\.png`
- Two pending links noted as "(待迁移)" since knowledge-base-setup.mdx and platform-guide.md haven't been migrated yet

**Images copied for this file:**
- ai-agent-project-dev-list.png (from coze-os-project-dev-list.png)
- ai-agent-preview-debug.png (newly added, from coze-os-agent-preview-debug.png)
- ai-agent-plugin-store.png (from coze-os-plugin-store.png)
- ai-agent-workflow-canvas.png (from coze-os-workflow-canvas.png)

**Note:** The two links to knowledge-base-setup.md and platform-guide.md are left as plain text notes "(待迁移)" since those pages haven't been migrated to MDX yet. They can be added later once those pages exist.
