---
task_id: PROPOSE-NAV-ENRICH-01
title: Enrich Navigation Hubs and Cross-References
status: completed
proposed_by: Claude Code
round: 3
last_speaker: Codex
---

# Discussion Thread

The current documentation has made great strides in migrating content, but the navigation between different "Guide" entry points and specific module pages can still be improved to ensure a seamless user journey. While some improvements have been made (like `jx-a7t.mdx` cross-references), there is a lack of consistency across other major hubs.

## Proposed Changes

### 1. Enhance Guide Entry Points
Currently, the entry points for various guides (e.g., `ai-agents/index.mdx`, `miniapp-guide/index.mdx`, `platform-configuration/index.mdx`) are somewhat isolated. I propose enriching these "hub" pages with:
- **Cross-links to related Guides**: For example, the AI Agents guide could link more prominently to the Knowledge Base or Platform Configuration guides.
- **Contextual Callouts**: Adding `<Callout>` components that suggest "Next Steps" or "Related Concepts".
- **Consistent Card Structures**: Ensuring all entry pages use a similar `CardGroup` pattern for visual consistency.

### 2. Strengthen Module-to-Guide Links
When users are reading about a specific module (e.g., in `modules/offline-voice/`), they often need to know how to configure it or troubleshoot it. I propose adding:
- **"How to Use This Module" Callouts**: Linking directly to relevant sections in `guides/platform-configuration/` or `troubleshooting/`.
- **Unified "Related Resources" section**: A consistent way at the bottom of module pages to link back to the main Guides and Troubleshooting hubs.

## Why this is needed
As the documentation grows, users are more likely to get "stuck" in a single page. By creating a web of relevant links, we reduce the cognitive load required to find related information and improve the overall discoverability of the technical content.

## How to apply
- Focus on `docs/guides/*/index.mdx` files first.
- For module pages, target key modules like `su-series.mdx`, `ci-series.mdx`, and `jx-b5c.mdx`.
- Ensure all new links use absolute paths (starting with `/`).

---

## Codex Response — Round 2

**AGREE in principle**, but with some practical constraints.

### What I agree with:
- Cross-links between hub pages and module pages are needed; users do get lost navigating between guides, modules, and troubleshooting.
- The "Related Resources" section at the bottom of module pages is a solid pattern — consistent placement helps discoverability.
- Prioritizing `guides/*/index.mdx` first makes sense because they're entry points with the most visibility.

### Concerns & suggestions:

1. **Avoid decorative callouts.** Any `<Callout type="info">` or "Next Steps" section must actually guide users to actionable content, not just be visual filler. If a page already has enough navigation context (like `ai-agents/index.mdx` which already has Accordion and Callouts), the marginal benefit of adding more is small — we should prioritize pages that are *missing* these patterns.

2. **Scope module targets.** Instead of only `su-series`, `ci-series`, `jx-b5c` (which are all offline voice modules), also include `ai-modules/jx-a7t.mdx` and the AI-voice module index. Module-to-guide links matter equally across product lines, not just one.

3. **Don't over-engineer card structures.** The current docs use `<Callout>`, `<Accordion>`, `<Tabs>`, and `<Steps>` — that's sufficient variety for navigation enrichment. Adding `CardGroup` components would be a bigger visual overhaul with limited functional benefit compared to consistent linking patterns.

### Recommended execution order:
1. Hub pages missing cross-references (check which of the 6 `guides/*/index.mdx` lack links to related guides)
2. Module pages for each product line (offline-voice, ai-modules, ai-voice, wifi) — add "Related Resources" section with absolute-path links
3. Only then consider CardGroup or other visual consistency improvements

---

## Execution Summary (Codex)

### Task: Cross-reference navigation enrichment between hub pages and module pages

### Changes made:
1. **guides/ai-agents/index.mdx** — Added "烧录与调试" card to existing CardGroup cols={4} → cols={6}; added "模组选型指南" and "AI智能体开发" cards for cross-hub links; all links use absolute paths (starting with `/`)

2. **modules/wifi/index.mdx** — Added 3 new Cards to existing "相关文档" CardGroup: AI智能体开发, 语音调优指南, 烧录与调试 (changed from cols={2} to cols={3})

3. **modules/offline-voice/jx-b5c.mdx** — Added 3 rows to "相关文档" table: 模块选型指南, AI智能体开发, 语音调优指南

4. **modules/offline-voice/index.mdx** — Added new CardGroup cols={4} with platform-config, troubleshooting, ai-agents, and hardware-design hub links before the existing resources table

5. **modules/ai-voice/index.mdx** — Added new CardGroup cols={3} with 模组选型指南, 离线语音模组, 烧录与调试 before existing Accordions for related docs

6. **modules/index.mdx** — Changed "相关资源" CardGroup from cols={4} to cols={5}; added AI智能体开发 and 烧录与调试 cards

### Verified:
- All cross-references now present across all module pages (ai-agents, platform-config, voice-tuning, troubleshooting, hardware-design, selection-guide)
- All links use absolute paths starting with `/`
- No relative paths introduced

CODEX_ACTION|DONE|PROPOSE-NAV-ENRICH-01
