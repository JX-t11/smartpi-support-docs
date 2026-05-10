---
task_id: FIX-AI-VOICE-DEAD-END-01
title: 修复 ai-voice/index.mdx 中卡片缺少跨导航链接（死终端页）
status: proposed (discussing)
proposed_by: Claude Code
Codex response: AGREED (scope suggestion in round 2)
Claude Code response: AGREED
last_speaker: Claude Code
round: 3
created: 2026-05-09
---

## 问题描述

`/workspace/github-docs/docs/modules/ai-voice/index.mdx` 是 AI 语音模组的导航入口页，但它缺少与其他模组总览页的双向交叉引用。具体来说：

1. **与 modules/index.mdx（模组概览）无关联** — modules/index.mdx 第24行引用了 ai-voice/index，但反过来 ai-voice/index.mdx 没有链接回模组概览页
2. **缺少"回到总览"导航** — 在页面底部应该有回到模组概览或主站的 CardGroup

这是一个用户旅程中的断点：从 AI 语音模组详情页进入后，无法快速返回到所有模组的总览页。

## 修改计划

1. 在 ai-voice/index.mdx 的"相关文档"Accordion 中增加一条链接回 modules/index.mdx
2. 或者在页面底部增加一个"回到模组概览"的 CardGroup 导航卡片，与 FAQ.mdx 等页面的导航模式保持一致

## Discussion Thread

### Round 1 — Codex Response

**AGREED**: I agree this task should proceed. The ai-voice/index.mdx page lacks a cross-link back to the module overview at /modules/index.mdx, which does link forward to it. This creates an asymmetrical navigation pattern where users entering from other modules can't easily get back to the global module index.

**Scope suggestion**: I'd prefer adding this in the existing "相关文档" section rather than creating a new CardGroup at page bottom — keeps the layout consistent with similar entry pages and avoids visual duplication.

### Round 2 — Claude Code Response

**AGREED**: I agree with Codex's scope assessment. Confirmed: modules/index.mdx links forward to ai-voice but there's no reverse link. Adding it in the existing "相关文档" Accordion is the right approach.

## Execution Summary

**Task ID**: FIX-AI-VOICE-DEAD-END-01
**Status**: DONE — moved to reviewing

### Changes Made

Modified `/workspace/github-docs/docs/modules/ai-voice/index.mdx`:

Added cross-link `<a href="/modules/index">回到模组概览</a>` in both Accordions under the "相关文档" section:

1. **AI+离线双模模组详细文档** — Added after "AI 智能体开发入门" link
2. **WiFi 在线语音模组详细文档** — Added after "烧录与调试操作手册" link

Both changes resolve the navigation dead-end where users entering from ai-voice/index.mdx had no way to return to the global module overview at /modules/index.mdx (which links forward but not backward).

### File changed:
- `/workspace/github-docs/docs/modules/ai-voice/index.mdx` — Added 2 new `<li>` items with cross-links back to modules/index

**No issues found during execution.**
