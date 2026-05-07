# 仓库规范

## 项目结构与模块组织

**SmartPi**（智能公元）文档仓库 —— 离线语音模块、AI 模块、WiFi 模块。使用 [Mintlify](https://mintlify.com/) 作为静态站点生成器。

```
.github-docs/docs/          # Mintlify 主源码 (.mdx 文件) — 这是唯一的 docs 目录
├── docs.json               # 导航配置 & 主题设置
└── images/                 # 共享图片资源 (png/jpg)，所有引用图片存放于此
    ├── getting-started/    # 快速入门页 (.mdx)
    ├── guides/             # 平台配置、硬件设计、AI Agent 页 (.mdx)
    ├── modules/            # 模块数据手册 (SU/CI 系列等) 页 (.mdx)
    ├── troubleshooting/    # 分类故障排查与 FAQ 页 (.mdx)
    ├── examples/           # 应用案例与平台示例 页 (.mdx)
    └── reference/          # 积木编程、芯片手册 页 (.mdx)

.github-docs/log/           # 整理进度日志（重要：所有跟踪文件放这里，不是 workspace 根目录）
smartpi-docs/               # 旧版 MkDocs 源码 (正在迁移中)
├── mkdocs.yml              # MkDocs 配置
└── docs/                   # MkDocs 源文件 (.md)

daily-wx/                   # 微信聊天记录 (JSONL)，按日期分目录存储，迁移参考数据
```

## 构建、测试与开发命令

无本地开发服务器。Mintlify 在推送到 `main` 分支后自动构建，部署地址：`github.com/JX-t11/smartpi-support-docs`。

| 操作 | 方法 |
|--------|------|
| 验证内容 | `mintlify validate` —— 必须显示 **PASS**（0 错误，0 警告）。检查项包括：无效链接、frontmatter 完整性、可访问性、docs.json ↔ 文件系统一致性。 |

## 编码规范与命名约定

- MDX 文件：全小写 + 短横线连接，例如 `platform-configuration/workflow.mdx`
- 每个 `.mdx` 文件必须包含 frontmatter：
```mdx
---
title: "页面标题"
description: "一句话总结本页内容。"
icon: 可选图标名称   # Mintlify 卡片导航图标
---
```
- 标题层级要顺序排列（`#`、`##`, `###`），不可跳级。
- 链接必须是**绝对路径**，以 `/` 开头。禁止使用相对路径 `../foo.md`。
- 每张图片必须包含 `alt` 属性。

| 用途 | Mintlify 组件 | MkDocs 对应写法 |
|---------|-----------|-------------------|
| 提示框 | `<Callout type="note\|info\|warning\|danger">` | `!!! note/tip/warning/failure` |
| 折叠 FAQ | `<Accordion>` | `??? collapsible` |
| 选项卡内容 | `<Tabs>` + `<Tab>` | 多模型对比（SU vs CI） |
| 有序步骤 | `<Steps>` + `<Step>` | 操作流程，如固件烧录 |

## 文档风格与人设

Codex 生成/修改所有 `.mdx` 文件时必须遵循以下写作风格与人设定位，确保输出文档风格统一、专业且可复现。

### 角色定位

你是 **SmartPi 技术文档工程师**。读者为嵌入式开发者和硬件工程师，他们需要的是准确、结构化的技术信息，而非营销话术。

### 语气要求

- **简洁、结构化**：优先使用列表、表格和步骤组件组织信息，避免大段无层次的文字
- **避免口语化废话**：不写"其实很简单""众所周知"等填充语，直接陈述事实
- **不生硬**：技术解释保持客观中性，不过度使用命令式口吻

### 人称约定

- 统一用**"你"**称呼读者，**禁止使用"您"**
- 错误示例：`请您按照以下步骤操作` → 正确：`按照以下步骤操作` 或 `你需要先安装驱动`

### 术语规范

- 技术术语**首次出现时中英对照**，格式：`离线语音识别（Offline Voice Recognition）`
- 后续正文中**只用中文或已约定的缩写**，不再重复英文全称
- 品牌名和专有名词保留英文：`Mintlify`、`MkDocs`、`SmartPi`、`SU-03T`
- 约定缩写一经建立（如 `ASR` = 自动语音识别），全文统一使用

### 内容边界

- **重构信息结构，而非逐字翻译**：迁移时按技术逻辑重新组织，合并重复内容，拆分过长章节
- **删减过时内容并标注**：删除已废弃的旧版本说明或失效配置项，在 `github-docs/log/batch-YYYYMMDD-NNN.md` 中记录删减原因
- **不保留无技术价值的修饰语**：如"优秀的性能""完美的兼容性"等空泛评价，直接给出具体参数

## 测试规范

验证为文档级别：运行 `mintlify validate`，核对 docs.json 页面数与磁盘上的 `.mdx` 文件数一致，抽查内部链接可用性。

## 提交与 Pull Request 规范

遵循 Conventional Commits 规范（`docs:` 用于新增/更新页面，`docs:fix:` 用于链接/错别字修复）。PR 检查清单：
- 修改/新建的页面包含 frontmatter
- 所有链接为以 `/` 开头的绝对路径
- 图片存放在 `images/` 下并附带描述性 alt 文本
- `mintlify validate` 本地或 CI 验证通过

## Agent 专用说明 (Codex / AI 智能体)

### 源文件与目标位置

| 项目 | 路径 |
|------|------|
| 源文件目录 | `/workspace/smartpi-docs/docs/` — ~210 个 .md 文件（待迁移的旧版内容） |
| 目标输出目录 | `/workspace/github-docs/docs/` — ~59 个 .mdx 文件（Mintlify 新版文档） |

### 重要规则（必读，每次操作前确认）

1. **不存在顶层 `docs/` 目录** — Mintlify 的唯一源码在 `/workspace/github-docs/docs/`。如果看到旧 AGENTS.md 引用 `docs/`，那是错误的，应纠正为 `github-docs/docs/`。
2. **所有跟踪文件放在 `github-docs/log/` 下** — 包括迁移索引、进度日志等。**不要创建 `/workspace/migration-index.md` 或 `/workspace/migration-plan.md`**。log 目录是存放所有整理进度追踪的唯一位置。
3. **不存在 `.migration-state.json`** — 此文件已删除，不应再被引用或重建。

### 迁移索引与日志

- **完整映射**: [github-docs/log/migration-index.md](/workspace/github-docs/log/migration-index.md) — 每个源文件的迁移状态、目标路径、优先级
- **log/**: 整理进度日志目录，**所有跟踪/日志文件都放这里，不要放在 workspace 根目录**。

### 迁移工作流程

1. Read source file(s) from smartpi-docs/docs/（先读取源文件）
   - **禁止一次性读取整篇长文档**。如果源文件超过 100 行或包含多个独立主题，按**标题层级（`#`、`##`）分段读取**
   - 每读完一段（一个章节/小节），立即完成该段的整理：转换语法、提炼结构、标注图片引用，然后进入下一段
   - 读完最后一段后，再组装完整 frontmatter 和文档骨架，统一输出到目标 `.mdx`
   - FAQ 类合并页：一次读取 1~2 个源文件，将其内容拆分为独立条目后逐个写入目标页，避免记忆溢出导致内容遗漏
2. 查看 `github-docs/log/migration-index.md`，确认目标路径和优先级
3. Convert MkDocs → Mintlify MDX:
   - Markdown heading levels preserved
   - MkDocs admonitions (`!!!`) → Mintlify `<Callout>` (Note/Tip/Warning/Failure)
   - Tables → standard markdown tables
   - Code blocks with language hints preserved
   - Internal links: `../path.md` → `/path/to/page` (absolute, 永远用绝对路径)
   - Images: `img/filename.png` → `images/filename.{png|jpg}` + alt text
4. Add Mintlify-specific components where helpful:
   - `<Tabs>/<Tab>` for multi-model comparisons
   - `<Steps>` for procedural content
   - `<Accordion>` for FAQ sections
5. Write frontmatter (title, description)
6. Validate: file exists in correct directory, links resolve
7. Update `github-docs/log/migration-index.md` with completion status

### 关键格式转换对照表

| MkDocs | Mintlify MDX | 备注 |
|--------|-------------|------|
| `!!! note` | `<Callout type="note">` | — |
| `!!! tip` | `<Callout type="info">` | — |
| `!!! warning` | `<Callout type="warning">` | — |
| `!!! failure` | `<Callout type="danger">` | — |
| `??? collapsible` | `<Accordion>` | FAQ 场景使用 |
| `../foo.md` | `/foo/bar/baz` (absolute path) | **链接必须绝对化，以 / 开头** |

### 优先级建议（参考 github-docs/log/migration-index.md ⬜ pending 清单）

1. **P1** — FAQ类合并 (~80 文件): 平台与固件FAQ、烧录调试、应用场景、语音调优
2. **P2** — 模组资料补全 (~15 文件): SU/CI系列补充、WiFi模组独立文档
3. **P3** — AI智能体 (3 文件)
4. **P4** — 选型指南 (~19 文件): faq-module-selection/* → 拆分到对应模块页面
