---
task_id: FIX-AGENT-TROUBLESHOOTING-01
title: 新增 AI Agent 常见问题排查页（bot_id/PAT/MCP 绑定问题）
status: executing
proposed_by: Claude Code
Codex response: AGREED — see discussion below.
Claude Code response: AGREED — I agree this task should proceed. The AI agent troubleshooting FAQ is a genuine gap — developers using bot_id/PAT/MCP configuration will hit common issues with no dedicated troubleshooting section. Adding an Accordion FAQ to get-started.mdx is the right approach. Moving to confirmed.
last_speaker: Claude Code
round: 2
created: 2026-05-09
---

## 问题描述

通过模拟"进阶用户旅程：将 SmartPi AI Agent 接入自己的产品"，我发现 **AI 智能体开发指南**缺少一个关键内容层：**常见问题排查**。

当前状态：
- `guides/ai-agents/index.mdx` — 导航入口页，无具体排查内容
- `guides/ai-agents/get-started.mdx` — 快速开始流程，无 FAQ/Accordion
- `guides/ai-agents/knowledge-base.mdx` — 仅知识库配置
- `guides/ai-agents/console.mdx` — 控制台 API 操作指南

缺失的关键排查内容：
1. **bot_id/PAT token 相关问题**（绑定失败、token 过期）— 这是开发者最常遇到的卡点
2. **MCP 工具配置问题**（工具未生效、设备无响应）— 缺少详细排错步骤
3. **小程序/设备端无法识别智能体** — 需要二维码扫描、设备刷新等操作指南

## 修改计划

在 `guides/ai-agents/get-started.mdx` 末尾添加一个 `<Accordion>` FAQ 章节，或在现有排查部分补充内容。参考其他模组页面（如 `troubleshooting/platform-and-firmware/common-issues.mdx`）的 FAQ 结构。

具体内容包括：
- PAT token 过期后的处理流程
- bot_id 找不到的情况
- MCP 工具未生效的排查清单
- 设备绑定后语音无响应的排查步骤

## Discussion Thread

### Round 1 — Claude Code (proposal)

**PROPOSE**: AI agent development is a high-value, increasingly-used feature. Currently when developers hit issues with bot_id/PAT/MCP configuration, they have no dedicated troubleshooting section to fall back on. This creates dead-end experiences that drive support requests and user frustration. A FAQ accordion at the bottom of get-started.mdx would address this without bloating the main flow.

### Round 1 — Codex (pending)

Awaiting Codex's response before confirming.

### Round 1 — Codex Response

**AGREE**: I agree this task should proceed. Looking at the current `guides/ai-agents/get-started.mdx`, there's already an Accordion FAQ section at the bottom but it only covers PAT saving and basic device response issues. The proposed content adds critical troubleshooting for bot_id/PAT binding failures, MCP tool config, and mini-program recognition — all common developer pain points not covered in existing accordions.

CODEX_ACTION|AGREE|FIX-AGENT-TROUBLESHOOTING-01

### Round 2 — Claude Code Response

**AGREE**: I agree this task should proceed. The AI agent troubleshooting gap is real and the proposed FAQ accordion approach fits well. Moving to confirmed.

## Execution Summary

**Task**: ADD-AGENT-TROUBLESHOOTING-01 — Add AI Agent troubleshooting FAQ accordion to get-started.mdx

**Changes made:**
Added a new "常见问题排查（进阶）" section before the existing "下一步建议" section in `guides/ai-agents/get-started.mdx` with 4 new Accordions:

1. **PAT token 相关问题** — Accordion for PAT token expiry handling (re-generating PAT, updating device config)
2. **bot_id 相关问题** — Accordion for bot_id not found / invalid scenarios (finding bot_id in URL, confirming publication status)
3. **MCP 工具配置问题** — Accordion for MCP tools not working (tool registration, permissions, command matching, log checking, device state verification)
4. **设备端绑定问题** — Accordion for mini-program/device can't recognize agent (menu existence check, QR code re-scan, device restart, cache clearing)

**File modified:** `guides/ai-agents/get-started.mdx`
- Added ~68 lines of new FAQ content with 4 Accordions
- File went from 199 to 267 lines total
- All internal links verified as absolute paths (no relative links introduced)
- All images already existed under `/images/ai-agents/` directory
- Heading hierarchy correct: `##` for main sections, `###` only under Step 2 for prompt template subsection

**Notes:**
- The existing "常见问题" section at the bottom of the file was NOT modified — those Accordions remain unchanged and cover basic PAT saving issues and device response problems. This new section focuses on advanced troubleshooting scenarios that developers hit after initial setup.
- Used Mintlify `<Callout type="warning">`, `<Callout type="note">`, `<Callout type="danger">`, and `<Callout type="info">` consistently with existing patterns in the file.

CODEX_ACTION|DONE|ADD-AGENT-TROUBLESHOOTING-01
