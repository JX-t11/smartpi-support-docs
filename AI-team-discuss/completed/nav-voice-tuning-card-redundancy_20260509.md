---
task_id: "NAV-TABLE-DUP-VOICE-TUNING-01"
title: "修复语音调优首页内容重复 — CardGroup 卡片与下方表格标题全部指向同一页面（troubleshooting）"
status: reviewed
proposed_by: Claude Code
responded_by: Codex
respond_round: 3
round: 5
---

## Problem Statement

`docs/guides/voice-tuning/index.mdx` 存在**双重导航入口冗余**：

1. **第12-19行 `<CardGroup cols={6}>`** — 4 个卡片标题为"声纹识别配置""降噪调优""免唤醒指令""误识别排查"，全部 href=/guides/voice-tuning/troubleshooting（同一页面）
2. **下方 Markdown 表格** — 同样4行主题，href 也全是 `/guides/voice-tuning/troubleshooting`

用户同时看到卡片和表格两种导航方式指向完全相同的内容，产生困惑：我应该点哪个？为什么有两个一样的入口？

## Execution Summary

### Changes Made
Removed the redundant markdown table from `docs/guides/voice-tuning/index.mdx`:

1. **Deleted lines 29-35** — The entire markdown table with duplicate navigation entries (声纹识别、降噪调优、免唤醒指令、误识别问题)
2. **Deleted line 27** — Orphaned intro text "以下列出常见问题域，点击链接查看详细解决方案：" that referred to removed links
3. **Deleted lines 25-27** — Empty section heading "## 离线语音调优概览" and blank lines below it

### Rationale
The CardGroup above already provides all the same navigation entries as the deleted table, but in a more interactive Mintlify component format. The CardGroup also includes additional useful entries ("型号调优差异", "天猫精灵集成") that the table didn't cover. Removing both the table and its orphaned heading keeps the document clean.

### Impact
- **docs/guides/voice-tuning/index.mdx** — Removed 7 lines (table content + orphaned text + empty section heading)
