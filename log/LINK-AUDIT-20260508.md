# Link Audit — 2026-05-08

## Scope
全量内部链接审计：163 个内部链接，跨越全部 58 个 .mdx 文件。

## Findings

| 类别 | 数量 | 详情 |
|------|-----|------|
| ✅ 有效页面内锚点 | 1 | `guides/tutorials/index.mdx` — `[案例移植指南](#案例移植建议)` 指向同文件 H2，功能正常 |
| ✅ 目录级链接 | ~50+ | `/troubleshooting/burning-and-debug/`, `/guides/platform-configuration/` 等 → index.mdx 均存在 |
| ℹ️ mailto 链接 | 1 | `reference/disclaimer.mdx` — `mailto:limingliang@aimachip.com`，属外部联系方式 |
| ❌ 无效/缺失目标 | 0 | 无断链 |

## Verdict
所有内部链接有效。`mintlify validate` ✅ PASS（docs.json 58 页 ↔ 磁盘 58 文件完全一致）。

无需代码变更。
