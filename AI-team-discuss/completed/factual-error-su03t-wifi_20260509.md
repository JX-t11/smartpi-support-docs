---
task_id: FIX-FACTUAL-01
title: device-overview.mdx 中 SU-05B 模组型号引用错误 — 误列为 WiFi 模组
status: reviewed
proposed_by: Claude Code
responded_by: Codex
respond_round: 4
round: 6
---

## Problem Statement

`/getting-started/device-overview.mdx` 第60行的 FAQ 内容中提到 **SU-05B** 作为"WiFi 系列模组"，但 SU 系列全部为离线语音模组（SU-03T, SU-10A, SU-20T 等），**不存在 SU-05B**。

## Execution Summary

### Changes Made
Fixed the WiFi module reference in `docs/getting-started/device-overview.mdx`:

**Before (line 60):**
```
取决于型号：**SU-03T** 为纯离线语音模块，无需网络连接；**WiFi 系列模组**（如 SU-05B）支持 WiFi 连接...
```

**After:**
```
取决于型号：**SU-03T** 为纯离线语音模块，无需网络连接；**WiFi 系列模组**（如 JX-A7T、JX-12F）支持 WiFi 连接...
```

### Verification Notes
- SU-05B only appears in this file and nowhere else — it is not a real SmartPi model number
- JX-A7T and JX-12F are actual WiFi/IoT models listed in the selection guide (`/modules/selection-guide`)
- The other mentions of "SU-05B" on lines 30 and 44 (as generic examples alongside SU-03T/CI-86Z) were not changed as they are just example model numbers, though they may also need review in a separate task

### Impact
- **docs/getting-started/device-overview.mdx** — Line 60: Replaced "SU-05B" with "JX-A7T、JX-12F" (actual WiFi models from selection guide)
