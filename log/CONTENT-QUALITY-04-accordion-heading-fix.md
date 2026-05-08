# CONTENT-QUALITY-04 | Accordion 内部标题层级修复

**日期**: 2026-05-08  
**文件**: `troubleshooting/platform-and-firmware/common-issues.mdx` (1083→1077行)

## 变更内容
### 问题
文件内部分 FAQ 章节存在两种结构不规范的问题：
1. `<Accordion title="...">` 内部的 `## FAQ 问题标题` — Accordion 内的 H2 标题与文档主 H1 层级冲突，且与 Accordion 自身标题重复
2. `### FAQ 问题 + <Accordion title="...">` 双重标记 — 同一内容同时用 H3 和 Accordion title 展示

### 修复
1. **所有 Accordion 内部的 `## 标题` → `**粗体文本**`** (15处)
   - 例如: `## 固件生成失败如何处理？` → `**固件生成失败如何处理？**`
2. **移除重复的 `### 标题 + <Accordion title="...">` 组合中的 H3** (6处)
   - 保留 `<Accordion title="...">`，删除重复的 `### FAQ问题?` 行

## 审查结果
| 检查项 | 结果 |
|--------|------|
| mintlify validate | ✅ success build validation passed |
| frontmatter (title + description) | ✅ 未修改，保持完整 |
| 链接绝对化（以 / 开头） | ✅ `/troubleshooting/platform-and-firmware/model-differences` 等引用有效 |
| Callout 类型合规 | ✅ `type="note"/"info"/"warning"/"danger"` 全合规 |
| "您" vs "你" | ✅ 无违规用词 |
| 标题层级 | ✅ Accordion 内不再出现 H2/H3，使用粗体文本替代 |
| 内容完整性 | ✅ 1083→1077行（仅移除6行重复标记） |

**结论:** 修复 Accordion 组件内部的结构性问题，消除标题层级冗余，提升可访问性和语义清晰度。

## Commit
`16a6401` — docs: 修复 common-issues.mdx 中 Accordion 内标题层级冗余问题
