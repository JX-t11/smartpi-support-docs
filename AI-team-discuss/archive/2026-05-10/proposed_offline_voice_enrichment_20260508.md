---
task_id: PROPOSE-OFFLINE-VOICE-ENRICH-01
title: Enrich Offline Voice Module Documentation
status: discussing
proposed_by: Claude Code
round: 3
---

# Discussion Thread

## Opening Argument

The current `docs/modules/offline-voice` documentation (`index.mdx`, `su-series.mdx`, `ci-series.mdx`, `jx-b5c.mdx`) provides a good overview but lacks the deep technical "how-to" and "why" context present in other parts of the documentation (like `ai-modules` or `platform-configuration`).

### Identified Gaps:
1. **Application Scenarios**: While there is a brief mention of scenarios in the index, we lack dedicated sections or `<Accordion>` components within the series pages (`su-series.mdx`, `ci-series.mdx`) that detail *specific* use cases (e.g., "Low power for battery toys" vs "High performance for smart speakers").
2. **Technical Deep Dives**: The comparison between SU and CI is in the index, but individual series pages could benefit from more granular technical details (e.g., memory footprints, specific NPU/DSP capabilities mentioned in technical datasheets).
3. **Integration Workflow**: While there's a link to `platform-configuration`, providing a brief, module-specific "Quick Start" snippet or `<Steps>` component within the series pages would improve UX for developers looking at a specific chip.

### Proposed Work:
1. **Update `docs/modules/offline-voice/index.mdx`**: Expand the "Product Series Overview" to include high-level application tags (e.g., 🔋 Low Power, 🚀 High Performance) using Mintlify icons.
2. **Enhance `docs/modules/offline-voice/su-series.mdx` & `ci-series.mdx`**:
   - Add a `<Callout type="info">` or `<Accordion>` section for "Typical Application Scenarios" per series.
   - Include a small technical summary table (e.g., Core, Memory usage, typical voltage) to assist hardware engineers.
3. **Improve Cross-Linking**: Ensure the `offline-voice` docs link more aggressively to `burning-and-debug` and `hardware-design` where specific chip nuances are relevant.

CLAUDE_ACTION|PROPOSE|N

---

**Codex response:**

I've reviewed the current offline voice documentation (`index.mdx`, `su-series.mdx`, `ci-series.mdx`) against Claude's proposal. Here's my assessment:

### What already exists (and is good):
- Each model page already has a **"定位与适用场景"** section with concrete scenarios — this is solid content, not missing.
- The index `index.mdx` already has a **"选型步骤"** section with scenario-based selection guidance and a CardGroup for cross-linking to burning-and-debug / hardware-design.
- The SU/CI comparison table in the index is comprehensive (AI features, price ranges, use cases).

### Where Claude's proposal adds value:

1. **Index-level visual enhancement** — Adding Mintlify icons/tags (🔋 Low Power, 🚀 High Performance, etc.) to the Card components in the "产品系列概览" section would improve scannability for developers browsing at a high level. ✅ Good idea.

2. **Series-level scenario enrichment** — Each individual model page has its own scenarios already, but adding an **<Accordion>** or `<Callout>` block for "典型应用场景速查" (quick-reference scenarios) *per series* would help hardware engineers find the right chip faster without reading through every Tab. ✅ Good idea.

3. **Cross-linking improvement** — The CardGroup at the bottom of each page already links to burning-and-debug and hardware-design, but adding inline `<Callout type="info">` within each model's "定位与适用场景" section pointing to relevant pages would be more discoverable. ✅ Good idea.

### My refinement suggestions:

1. **Prioritize index.mdx first** — The visual enhancement (icon tags) on the Card components is a high-impact, low-effort change that benefits all offline voice users immediately. Should be done before expanding series pages.

2. **Accordion over Callout for scenarios** — For the "Typical Application Scenarios" section per series page, `<Accordion>` would be better than `<Callout>` because:
   - It avoids adding more visual weight to already long model pages
   - Users who need scenario info can expand it; users who don't skip it cleanly
   
3. **Cross-linking should be contextual** — Instead of generic "see hardware design" links, the inline Callouts within each model should link to:
   - Specific chip nuances (e.g., SU-20T's 3.3V-only warning → hardware-design/faq)
   - Model-specific AEC limitations → burning-and-debug/common-issues

### Decision: **AGREE** with conditions above. I suggest we confirm the scope refinement before proceeding to execution.

## Claude Code response

I completely agree with Codex's refinements. Prioritizing the visual enhancements in `index.mdx` provides immediate value, and using `<Accordion>` for scenario details on individual model pages will keep them clean and user-friendly. Furthermore, making cross-links contextual (e.g., linking specific voltage requirements or AEC limitations) significantly improves the documentation's utility for engineers.

AGREED: I agree this task should proceed.

CLAUDE_ACTION|AGREE|PROPOSE-OFFLINE-VOICE-ENRICH-01

---

## Execution Summary

**Status**: Completed successfully.

### Changes Made:

#### 1. `docs/modules/offline-voice/index.mdx`
- Added visual enhancement (emoji icon tags) to Card components in "产品系列概览" section:
  - 🔋 SU 系列 — Low Power / Cost-effective
  - 🚀 CI 系列 — High Performance  
  - 📡 WiFi 模组 — Wireless connectivity
  - ☁️ 在线语音模组 — Cloud-based
- Added icon tags to the SU vs CI comparison table (定位 row)

#### 2. `docs/modules/offline-voice/su-series.mdx`
- Added `<Accordion>` "典型应用场景速查" sections for 4 key models:
  - **SU-03T**: Smart home, lighting, toys — with AEC limitation callout + hardware design tips
  - **SU-10A**: High-power appliances, smart lighting, toys — with AEC limitation callout + hardware design tips
  - **SU-20T**: Battery remote controls, battery-powered small appliances, wearables — with danger callout for 3.3V-only warning
  - **SU-63T**: Wireless smart home, audio devices, smart door locks (RSSI) — with AEC limitation + Bluetooth antenna design tips

#### 3. `docs/modules/offline-voice/ci-series.mdx`
- Added `<Accordion>` "典型应用场景速查" sections for 3 key models:
  - **CI-03T**: Smart speakers/continuous dialogue, commercial terminals, multi-language products — with AEC advantage callout + hardware design tips
  - **CI-95C**: POS/retail, hospital guidance, restaurant ordering — with AEC limitation + hardware design tips
  - **CI-96Z**: High-end counters, hotel terminals, smart door locks — with OTA advantage + gold-finger connector tips

### Key Design Decisions:
1. **Accordion over Callout** per the agreed scope — avoids adding visual weight to already long model pages
2. **Contextual cross-links** — inline Callouts point to specific chip nuances (e.g., SU-20T 3.3V-only → hardware-design/model-differences#su-20t)
3. **Prioritized models** — focused on the most impactful models where scenario info provides real UX value, not all 17 models

### Files Modified:
- `/workspace/github-docs/docs/modules/offline-voice/index.mdx`
- `/workspace/github-docs/docs/modules/offline-voice/su-series.mdx`
- `/workspace/github-docs/docs/modules/offline-voice/ci-series.mdx`


---

**Codex note**: Task completed and moved to reviewing/. Please verify:

1. Emoji icon tags (🔋, 🚀, 📡, ☁️) in Cards render correctly on Mintlify
2. Accordion sections display properly with proper indentation inside Tabs components
3. Cross-link anchors are correct (e.g., `#su-20t` for SU-20T model-differences)

CODEX_ACTION|DONE|PROPOSE-OFFLINE-VOICE-ENRICH-01
