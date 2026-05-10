---
task_id: "AI-INDEX-CARD-DUP-01"
title: "修复 ai-agents/index 页面卡片重复 — '智能体开发'链接指向自身而非快速开始页"
status: reviewed
proposed_by: Claude Code
responded_by: Codex
respond_round: 3
round: 5
---

## Problem Statement

`docs/guides/ai-agents/index.mdx`（第104-111行）的 <CardGroup cols={6}> 中，'AI 开发'卡片链接指向自身：

```
<Card title="AI 智能体开发" description="将模组接入 AI 平台实现智能对话与知识库问答" href="/guides/ai-agents/get-started">AI 开发</Card>
```

实际上这个href是正确的（`get-started`），问题在于第71-84行的 <CardGroup cols={4}> 中，同样存在：

```
<Card title="快速开始" icon="rocket_launch" href="/guides/ai-agents/get-started">...<Card>
```

两张卡片都指向 `/guides/ai-agents/get-started`，内容高度重复（一个标题是"快速开始"另一个是"AI 智能体开发"），对用户造成困惑：应该点哪个？

## Execution Summary

### Changes Made
Removed the duplicate card from `docs/guides/ai-agents/index.mdx`:

1. **Line 106** — Removed: `<Card title="AI智能体开发" description="将模组接入 AI 平台实现智能对话与知识库问答" href="/guides/ai-agents/get-started">AI 开发</Card>`
2. **Line 104** — Updated: `cols={6}` → `cols={5}` (since one card was removed)

### Remaining Cards in CardGroup (after fix)
| Card | Title | href |
|------|-------|------|
| 1 | 模组选型指南 | /modules/selection-guide |
| 2 | 天猫精灵在线方案 | /guides/voice-tuning/tmall-genie |
| 3 | 硬件设计指南 | /guides/hardware-design/index |
| 4 | 平台配置工作流 | /guides/platform-configuration/workflow |
| 5 | 烧录与调试 | /troubleshooting/burning-and-debug/index |

### Impact
- **docs/guides/ai-agents/index.mdx** — Removed 1 duplicate Card (line 106), updated cols from 6 to 5
