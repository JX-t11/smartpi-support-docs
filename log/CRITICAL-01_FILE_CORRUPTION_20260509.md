---
task_id: CRITICAL-01
title: "common-issues.mdx 文件内容丢失 — awk cleanup command caused data loss"
severity: critical
date: 2026-05-09
status: reported - needs Claude to recover via git
---

## Incident Summary

The file `troubleshooting/platform-and-firmware/common-issues.mdx` has been corrupted with **all content removed** — only newline characters remain (191 bytes, 0 content lines). This happened during the execution of CRITICAL-01 Option B (removing unrecoverable image references).

## Root Cause

A series of sed commands and an awk blank-line cleanup command caused cascading failures:
1. Initial sed attempts to remove image references partially worked but left some duplicates
2. Attempts to add Callout notes inserted duplicate content everywhere in the file  
3. An awk command intended to collapse consecutive blank lines accidentally removed ALL content from the file

## What was lost

The original `common-issues.mdx` contained ~900+ lines of troubleshooting content including:
- Firmware generation issues (固件生成与管理)
- Language settings (语言设置) 
- UART/serial communication debugging (串口通信调试)
- GPIO power-on memory configuration (GPIO 上电记忆功能配置)
- Various other platform and firmware FAQ sections

## Resolution needed

This file MUST be recovered via git:
```bash
git checkout HEAD -- docs/troubleshooting/platform-and-firmware/common-issues.mdx
```

**DO NOT attempt further manual editing of this file until it is restored from git.**

## Files affected by partial edits before data loss

The following image references were successfully removed BEFORE the data loss incident:
- `/images/platform-config/platform-execution-order.jpg` (line ~469)
- `/images/platform-config/platform-firmware-generate-error.jpg` (line ~67)
- `/images/platform-config/platform-gpio-memory.jpg` (line ~576)  
- `/images/platform-config/platform-language-selector.jpg` (line ~438)
- `/images/platform-config/platform-uart1-config.jpg` (line ~468)

After restoration from git, these 5 image references will need to be removed again carefully.

## Prevention note for future operations

When modifying files with sed/awk:
- Always back up the file first (`cp file file.bak`)
- Test complex sed patterns on a copy before applying in-place
- Avoid chained commands that modify the same file multiple times in one session
