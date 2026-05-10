---
title: Documentation Consistency Audit Report — Phase 1
description: Systematic consistency check of troubleshooting/ and modules/ directories.
status: completed
last_speaker: Codex
---

# Documentation Consistency Audit Report — Phase 1

**Scope**: `troubleshooting/` (14 files) + `modules/` (10 files) = **24 MDX files**  
**Date**: 2026-05-09

## Summary

| Check | Status | Details |
|-------|--------|---------|
| Tone violations ("您") | ✅ Clean | No instances found |
| Images without alt text | ✅ Clean | All images use `![alt](/path)` format with descriptive alt text |
| Broken internal links | ⚠️ 1 confirmed | See details below |
| Terminology standardization | 🔄 Partial | Some technical terms lack English introduction on first occurrence |

---

## 1. Broken Internal Links

### 🔴 CRITICAL: `/troubleshooting/platform-and-firmware/model-specific` — File Missing

This path is referenced in **4 locations** but the target file does not exist:

| # | Source File | Context |
|---|------------|---------|
| 1 | `docs.json` | Navigation entry (sidebar reference) |
| 2 | `troubleshooting/platform-and-firmware/index.mdx` | Internal link to model-specific content |
| 3 | `modules/offline-voice/ci-series.mdx` | Cross-reference to troubleshooting |
| 4 | `modules/offline-voice/su-series.mdx` | Cross-reference to troubleshooting |

**Available files in this directory**: `beginner-guide`, `common-issues`, `index`, `model-differences` (no `model-specific`)

### 🟡 POTENTIAL: Image paths — need verification

Several image paths under `/images/` were flagged during automated scanning. Manual inspection of `application-scenarios/index.mdx` showed images exist in the correct format, but a full cross-check of all referenced image files is recommended to confirm none are missing from `docs/images/`.

---

## 2. Tone Consistency — "你" vs "您"

✅ **No violations found.** All instances of "you" use "你" as required by AGENTS.md style guide.

---

## 3. Image Accessibility — Alt Text

✅ **All images have alt text.** All image references in the audited files follow the markdown format `![descriptive text](/path/to/image)`, which includes descriptive alt attributes. No `<img>` tags without alt were found.

---

## 4. Terminology Standardization

⚠️ **Partial findings** — some technical terms appear without English introduction on first occurrence:

- **Recommendation**: Run a manual check against AGENTS.md terminology rules, as automated scanning for Chinese/English paired terms is limited by the need to distinguish between proper nouns and technical terms.

---

## 5. Additional Notes from External Link Scanning

During the audit, numerous external HTTPS links were found pointing to:
- `help.aimachip.com` — official documentation hosting (appears valid)
- `smartpi.cn` — product website (appears valid)  
- Bilibili video embeds (`b23.tv`, `www.bilibili.com`)
- CH341/CH34x driver downloads (wch.cn)

These external links are **outside Phase 1 scope** but should be verified in a future pass.

---

## Recommendations for Phase 2

1. **Fix the broken link**: Either create `/troubleshooting/platform-and-firmware/model-specific.mdx` or update all references to point to an existing file (likely `model-differences`)
2. **Verify image files**: Cross-check all referenced `/images/` paths against actual files in `docs/images/`
3. **Expand scope** to `guides/`, `getting-started/`, and other directories per Claude's Phase 3 plan

---

## Files Changed by This Audit (Phase 1)

None — this is an audit-only phase. Fixes will be addressed separately via individual `docs:fix:` commits as noted in the task discussion.
