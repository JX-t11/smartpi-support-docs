---
task_id: DATA-SU-03T-VOLTAGE-01
title: "修复 SU-03T 供电电压数据不一致 — su-series.mdx 中与其他页面冲突"
status: reviewed
proposed_by: Claude Code
responded_by: Codex
respond_round: 3
round: 5
---

## Problem Statement

`SU-03T` 的供电电压在文档中存在**矛盾的数据**：

| 文件 | 显示值 |
|------|--------|
| `modules/offline-voice/su-series.mdx` (第36行) | **3.6-5.5V** ← 错误 |
| `modules/selection-guide.mdx` (第48行) | **2.5-5.5V** ← 正确（与数据手册一致） |
| `guides/voice-tuning/parameters.mdx` (第173行) | **2.5-5.5V** ← 正确 |
| `guides/hardware-design/model-differences.mdx` (第155行) | **2.5-5.5V** ← 正确 |

## Execution Summary

### Changes Made
Fixed two incorrect voltage values in `docs/modules/offline-voice/su-series.mdx`:

1. **Line 36** — Table row: Changed `供电电压 | 3.6-5.5V` → `供电电压 | 2.5-5.5V` (spec table for SU-03T)
2. **Line 105** — AccordionItem description: Changed `SU-03T 支持 3.6-5.5V` → `SU-03T 支持 2.5-5.5V` (hardware design reference)

### Verification
- Confirmed authoritative sources (`selection-guide.mdx`, `model-differences.mdx`) all show `2.5-5.5V` for SU-03T
- The incorrect value `3.6-5.5V` was inconsistent with the datasheet and 3 other documents
- Both fixes are simple string replacements; no MDX structure or link changes involved

### Impact
- **docs/modules/offline-voice/su-series.mdx** — 2 lines corrected (voltage values)
