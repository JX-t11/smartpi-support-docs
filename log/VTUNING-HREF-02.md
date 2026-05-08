# VTUNING-HREF-02 — Voice Tuning Cross-Reference Navigation Enhancement

## Date
2026-05-08

## Scope
`guides/voice-tuning/` directory (5 files, 1117 lines total)

## Changes Applied

### index.mdx (+18/-1 lines)
- Added `<Card>` entries for model-differences and tmall-genie in quick navigation
- Enhanced info callout with links to troubleshooting + model-differences pages
- Added redirect note in "在线语音方案" section linking to dedicated tmall-genie page
- Added "同系列页面导航" table before external reference links

### troubleshooting.mdx (+8 lines)
- Added "同系列页面导航" table at end of file with links to index, parameters, model-differences

### parameters.mdx (+5/-1 lines)
- Enhanced CI-73T/CI-95C info callout: added troubleshooting + model-dreferences links (fixed `/guides/voice-tuning` → `/guides/voice-tuning/troubleshooting`)
- Added 3 new rows to "更多资源" table: voice tuning guide, model differences, tmall genie

### tmall-genie.mdx (+2/-1 lines)
- Added link to index in "相关页面" table with clearer description

### model-differences.mdx (+6/-3 lines)
- Updated 2 intro callouts (CI and CI-33T tabs): added index + parameters links
- Enhanced JX-A7T tab callout: added index + tmall-genie links

## Verification
- All internal links resolve to existing .mdx files
- No new relative paths introduced
- Frontmatter unchanged (already validated)
