---
task_id: NAV-01
title: Improve navigation links - Phase 1 Redo
status: completed
last_speaker: Codex
round: 4
executed_by: Codex
date: 2026-05-09
---

## Execution Summary (Phase 1 Redo)

### Problem
NAV-01 Phase 1 anchor fixes and directory-level link fixes were rolled back due to conflict with CRITICAL-01 rollback. All broken links needed to be fixed again, and a comprehensive scan revealed **177 broken links** across **30 files**.

### Root Cause Analysis
Broken links fell into three categories:

**Category A (37 unique paths):** Links missing `.mdx` extension but target file exists — e.g., `/guides/voice-tuning/index` should be `/guides/voice-tuning/index.mdx`. These resolve in Mintlify via auto-extension but are inconsistent.

**Category B (14 unique directory-level paths):** Directory-level paths without `index.mdx` and no `.mdx` file — e.g., `/guides/platform-configuration`, `/reference/block-programming`. These require specific target page selection.

**Category C (3 anchor fragments):** Links to non-existent accordion IDs on the same page — e.g., `/guides/platform-configuration/variable-control-setup#1` should have `id="1.-基本变量操作"` on the Accordion component.

### Actions Taken

#### 1. Category A: Added `.mdx` extension (37 paths)
Added `.mdx` to all href links where the target file exists but link was missing the extension. Affected files include:
- `index.mdx`, `modules/index.mdx`, `modules/offline-voice/su-series.mdx`, etc.

#### 2. Category B: Resolved directory-level paths (14 unique paths)
Created mapping of directory → specific page target:
| Directory | Target Page |
|-----------|------------|
| `/guides/ai-agents` | → `/guides/ai-agents/get-started` |
| `/guides/hardware-design` | → `/guides/hardware-design/index` |
| `/guides/platform-configuration` | → `/guides/platform-configuration/workflow` |
| `/guides/tutorials` | → `/guides/tutorials/index` |
| `/guides/voice-tuning` | → `/guides/voice-tuning/index` |
| `/modules/offline-voice` | → `/modules/offline-voice/index` |
| `/modules/ai-voice` | → `/modules/ai-voice/index` |
| `/modules/wifi` | → `/modules/wifi/index` |
| `/reference/block-programming` | → `/reference/block-programming/index` |
| `/reference/chip` | → `/reference/chip/index` |
| `/troubleshooting/application-scenarios` | → `/troubleshooting/application-scenarios/common-issues` |
| `/troubleshooting/burning-and-debug` | → `/troubleshooting/burning-and-debug/common-issues` |

#### 3. Category C: Fixed anchor fragment IDs (3 Accordion IDs)
Added `id` attributes to Accordions in `guides/platform-configuration/variable-control-setup.mdx`:
- Line 38: `Accordion id="1.-基本变量操作"`
- Line 306: `Accordion id="4.-串口参数赋值与变量"`
- Line 421: `Accordion id="3.-高级应用：互锁控制"`

### Verification Result
**All href links resolved — 0 broken links remaining.** Verified via comprehensive scan of all .mdx files for both `<Card href=...>` and `<a href=...>` patterns.

### Files Modified (summary)
- `index.mdx` — 18 link fixes
- `modules/index.mdx` — 12 link fixes  
- `modules/wifi/index.mdx` — 9 link fixes
- `guides/ai-agents/index.mdx` — 9 link fixes
- `troubleshooting/platform-and-firmware/index.mdx` — 11 link fixes
- `modules/ai-modules/jx-a7t.mdx` — 16 link fixes
- `modules/ai-voice/index.mdx` — 15 link fixes
- And 23 other files with varying numbers of link fixes

### Remaining Tasks from NAV-01 Phase 2
CRITICAL-01's image restoration task (Phase 2) needs to be completed. After images are verified, remaining missing image references should be removed or updated.

CODEX_ACTION|DONE|NAV-01
