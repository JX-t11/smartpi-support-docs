# Emoji 清理日志 — 2026-05-07

## 概述
全面移除所有 .mdx 文件中的装饰性 emoji，以符合 AGENTS.md 写作风格规范（"禁止使用 emoji"）。

## 处理范围
- **修改文件数**: 44 个 .mdx 文件
- **变更行数**: 323 insertions, 323 deletions (balanced — pure character replacement)

## 技术细节
1. **Emoji 移除策略**: 
   - 使用 Unicode 码点范围 U+1F000–U+1FFFF 和 U+2600–U+27BF 匹配装饰性 emoji
   - 正确处理 UTF-16 代理对（如 💰💡🏷 等多字节 emoji）
   - 保留变体选择器 U+FE0F、零宽连接符 U+200D

2. **保留的字符** (表格数据标记):
   - ✅ U+2705 (白色勾号)
   - ❌ U+274C (叉号)  
   - ✓ U+2713 (勾)
   - ✗ U+2717 (叉)
   - ✔ U+2714 (粗勾)
   - ✖ U+2716 (粗叉)

3. **修复的遗留问题**:
   - heading 双空格: "## 📋 Title" → "# Title" (emoji移除后留下额外空格)
   - Card 体前导空格: ">📋 Text" → ">Text" 
   - 变体选择器残留: ⚙️(U+2699+U+FE0F) → ⚙ (仅保留基本字符，再移除)

## 受影响的模块
- modules/ (模组概览、SU/CI/JX系列、选型指南)
- guides/platform-configuration/* (全部9个文件)
- troubleshooting/application-scenarios/* 
- examples/, getting-started/, reference/*, tags.mdx
