# BLOCKQUOTE-FIX-02 — 残留 `>` blockquote → `<Callout type="note">` 转换（2026-05-08）

## 问题描述
质量扫描发现 4 个 `.mdx` 文件中仍有 6 处 MkDocs 风格的 `>` blockquote 语法残留，未转换为 Mintlify `<Callout>` 组件。这些遗漏是此前 BLOCKQUOTE-FIX-01（覆盖14个文件）的补充修复。

## 变更明细

| # | 文件 | 行号 | 内容摘要 |
|---|------|------|---------|
| 1 | `guides/ai-agents/get-started.mdx` | 53 | 系统提示词示例 → `<Callout type="note">` |
| 2 | `guides/platform-configuration/device-behavior-id.mdx` | 121 | Accordion 内 ID 拼写错误说明 → `<Callout type="note">` |
| 3 | `guides/platform-configuration/parameters.mlx` | 266 | JSON 参数名转换说明 → `<Callout type="note">` |
| 4 | `guides/platform-configuration/parameters.mdx` | 277 | 变量重复读取问题说明 → `<Callout type="note">` |
| 5 | `guides/platform-configuration/variable-control-setup.mlx` | 315 | 串口参数赋值提醒 → `<Callout type="note">` |
| 6 | `guides/platform-configuration/variable-control-setup.mdx` | 359 | 变量用途说明 → `<Callout type="note">` |

## 提交记录
- **docs submodule**: `8a01658` — 4 files, 6 insertions(+), 6 deletions(-)
- **main repo**: `af86458` — docs submodule pointer update + tracking files (`8971d0a`)

## 验证
```bash
find . -name '*.mdx' -exec grep -l '^ >' {} + → 0 matches ✓
mintlify validate → 待 CI 确认
