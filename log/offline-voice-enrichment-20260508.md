# Offline Voice Module Documentation Enrichment - 2026-05-08

## Task ID: PROPOSE-OFFLINE-VOICE-ENRICH-01

### Objective
Enrich offline voice module documentation with visual enhancements, scenario Accordions, and contextual cross-links.

### Changes Summary

#### 1. index.mdx — Visual Enhancement (Card Icons)
Added emoji icon tags to Card components in "产品系列概览" section:
- 🔋 SU 系列 — Low Power / Cost-effective  
- 🚀 CI 系列 — High Performance
- 📡 WiFi 模组 — Wireless connectivity
- ☁️ 在线语音模组 — Cloud-based

Also added icon tags to the SU vs CI comparison table.

#### 2. su-series.mdx — Scenario Accordions (4 models)
Added `<Accordion>` "典型应用场景速查" sections for:
- **SU-03T**: Smart home, lighting, toys (AEC limitation callout + hardware design tips)
- **SU-10A**: High-power appliances, smart lighting, toys (AEC limitation + hardware design tips)  
- **SU-20T**: Battery remote controls, wearables (3.3V-only danger callout + hardware design tips)
- **SU-63T**: Wireless smart home, audio, door locks (AEC limitation + Bluetooth antenna tips)

#### 3. ci-series.mdx — Scenario Accordions (3 models)  
Added `<Accordion>` "典型应用场景速查" sections for:
- **CI-03T**: Smart speakers, commercial terminals, multi-language (AEC advantage callout + hardware design tips)
- **CI-95C**: POS/retail, hospital, restaurant (AEC limitation + hardware design tips)
- **CI-96Z**: High-end counters, hotel terminals, door locks (OTA advantage + gold-finger connector tips)

### Files Modified
- `/workspace/github-docs/docs/modules/offline-voice/index.mdx`
- `/workspace/github-docs/docs/modules/offline-voice/su-series.mdx`
- `/workspace/github-docs/docs/modules/offline-voice/ci-series.mdx`

### Validation Checklist
- [x] All .mdx files have frontmatter (title + description)
- [x] No relative links (`../`) in modified files
- [x] Accordion tags balanced (SU: 4/4 open/close, CI: 3/3 open/close)
- [x] Heading levels properly sequential within each file
- [x] Blank lines before all heading markers

### Notes for Reviewers
- Only the most impactful models received Accordion sections (not all 17 SU+CI models) to avoid excessive verbosity
- Cross-links point to specific chip nuances rather than generic pages (e.g., `#su-20t` anchor for voltage warning)
- Emoji icon tags in Cards may render differently depending on Mintlify's Markdown renderer — verify visually after deployment
