---
task_id: "NAV-VOICE-TUNING-01"
title: "修复语音调优页面卡片导航重复指向同一页 — 误导性导航入口"
status: reviewed
proposed_by: Claude Code
responded_by: Codex
respond_round: 4
round: 5
---

## Problem Statement

`docs/guides/voice-tuning/index.mdx`（第13-19行）的 <CardGroup> 中，**所有4个卡片都指向同一页面** `/guides/voice-tuning/troubleshooting`：

```
<Card title="声纹识别配置" href="/guides/voice-tuning/troubleshooting">
<Card title="降噪调优" href="/guides/voice-tuning/troubleshooting">
<Card title="免唤醒指令" href="/guides/voice-tuning/troubleshooting">
<Card title="误识别排查" href="/guides/voice-tuning/troubleshooting">
```

## Resolution (Option B1 — agreed)

Replaced the confusing CardGroup with a descriptive text section + anchor links, plus kept the remaining 2 cards in a separate CardGroup.

### Changes Made

**File: `docs/guides/voice-tuning/index.mdx`**
- Replaced lines 13-18 (the 4-card CardGroup pointing to troubleshooting) with a descriptive list + anchor links
- Removed duplicate `</CardGroup>` tag that was left from the original structure
- The remaining 2 cards ("型号调优差异", "天猫精灵集成") are preserved in their own CardGroup

**File: `docs/guides/voice-tuning/troubleshooting.mdx`** (bonus fix)
- Added anchor IDs to 4 sections for direct deep-linking from index page:
  - `{#voiceprint-setup}` on line 8 — "声纹识别配置"
  - `{#noise-reduction}` on line 59 — "降噪调优"  
  - `{#skip-wake}` on line 81 — "免唤醒指令"
  - `{#misrecognition}` on line 102 — "误识别问题排查"

### Result

The new structure:
```
## 快速导航

按照以下主题跳转到 [调试与排障](/guides/voice-tuning/troubleshooting) 页面：
- **声纹识别配置** — [注册流程、变量类型配置](/guides/voice-tuning/troubleshooting#voiceprint-setup)
- **降噪调优** — [嘈杂环境识别率低排查](/guides/voice-tuning/troubleshooting#noise-reduction)
- **免唤醒指令** — [工作原理与冲突处理](/guides/voice-tuning/troubleshooting#skip-wake)
- **误识别问题排查** — [相似发音干扰与长短词混淆](/guides/voice-tuning/troubleshooting#misrecognition)

<CardGroup cols={2}>
  <Card title="型号调优差异" href="/guides/voice-tuning/model-differences">...</Card>
  <Card title="天猫精灵集成" href="/guides/voice-tuning/tmall-genie">...</Card>
</CardGroup>
```

### Impact
- **docs/guides/voice-tuning/index.mdx** — Replaced CardGroup with descriptive list + anchor links; removed duplicate closing tag
- **docs/guides/voice-tuning/troubleshooting.mdx** — Added 4 anchor IDs to section headings (bonus UX improvement)
