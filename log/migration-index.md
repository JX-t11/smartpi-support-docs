# SmartPi 文档迁移索引

> 最后更新: 2026-05-07  
> 总计: **209** 个源文件 (`.md`) → **60** 个目标文件 (`.mdx`)  
> 迁移方式: 内容分析整合、结构重构、格式转换，非逐字复制

---

## 迁移完成（已完成合并/重构）

### FAQ 类 — 按问题域合并（25→5 页面）

| # | 源文件路径 | 目标路径 | 状态 |
|---|-----------|---------|------|
| 1 | `faq-platform-and-firmware/platform_and_firmware.md` | `/troubleshooting/faq.mdx` | ✅ 已合并 |
| 2 | `faq-platform-and-firmware/*.md` (24 files) | `/troubleshooting/platform-and-firmware/index.mdx` | ✅ 已合并 |
| 3 | `faq-platform-and-firmware/*.md` (model-specific FAQ) | `/troubleshooting/platform-and-firmware/common-issues.mdx` | ✅ 已合并 |
| 4 | `faq-platform-and-firmware/*.md` (SU vs CI comparison) | `/troubleshooting/platform-and-firmware/model-differences.mdx` | ✅ 已合并 |
| 5 | `faq-platform-and-firmware/*.md` (step-by-step troubleshooting) | `/troubleshooting/platform-and-firmware/configuration-guide.mdx` + `beginner-guide.mdx` + `index.mdx` | ✅ 已拆分 |

### FAQ 类 — 烧录调试（23→4 页面）

| # | 源文件路径 | 目标路径 | 状态 |
|---|-----------|---------|------|
| 6 | `faq-burning-and-debug/burning_and_debug.md` | `/troubleshooting/burning-and-debug/index.mdx` | ✅ 已合并 |
| 7 | `faq-burning-and-debug/*.md` (model-specific FAQ) | `/troubleshooting/burning-and-debug/common-issues.mdx` + `step-by-step.mdx` | ✅ 已合并 |
| 8 | `faq-burning-and-debug/*.md` (SU vs CI comparison) | `/troubleshooting/burning-and-debug/model-differences.mdx` | ✅ 已合并 |

### FAQ 类 — 应用场景（22→4 页面）

| # | 源文件路径 | 目标路径 | 状态 |
|---|-----------|---------|------|
| 9 | `faq-application-scenarios/faq-application-scenarios-*.md` (21 model-specific) | `/troubleshooting/application-scenarios/index.mdx` + `common-issues.mdx` + `model-differences.mdx` + `step-by-step.mdx` | ✅ 已合并 |

### FAQ 类 — 硬件设计（22→4 页面）

| # | 源文件路径 | 目标路径 | 状态 |
|---|-----------|---------|------|
| 10 | `faq-hardware-design/hardware_design.md` + individual models | `/guides/hardware-design/index.mdx` | ✅ 已合并 |
| 11 | `faq-hardware-design/*.md` (model-specific) | `/guides/hardware-design/model-differences.mdx` + `faq.mdx` | ✅ 已合并 |

### FAQ 类 — 语音调优（25→5 页面）

| # | 源文件路径 | 目标路径 | 状态 |
|---|-----------|---------|------|
| 12 | `faq-voice-tuning/voice_tuning.md` + general content | `/guides/voice-tuning/index.mdx` + `troubleshooting.mdx` + `parameters.mdx` | ✅ 已合并拆分 |
| 13 | `faq-voice-tuning/*.md` (model-specific) | `/guides/voice-tuning/model-differences.mdx` | ✅ 已合并 |

### FAQ 类 — 模块选型（22→1 页面）

| # | 源文件路径 | 目标路径 | 状态 |
|---|-----------|---------|------|
| 14 | `faq-module-selection/module_selection.md` + individual models | `/modules/selection-guide.mdx` | ✅ 已合并重构 |

### 平台配置（29→8 页面）

| # | 源文件路径 | 目标路径 | 状态 |
|---|-----------|---------|------|
| 15 | `platform-configuration/platform-configuration.md` | `/guides/platform-configuration/index.mdx` | ✅ 已合并 |
| 16 | `platform-configuration/firmware-config-workflow.md` | `/guides/platform-configuration/workflow.mdx` | ✅ 已转换 |
| 17 | `platform-configuration/firmware-config-parameters.md` (all models merged) | `/guides/platform-configuration/parameters.mdx` | ✅ 已合并重构 |
| 18 | `platform-configuration/command_execution_control.md` | `/guides/platform-configuration/command-execution-control.mdx` | ✅ 已转换 |
| 19 | `platform-configuration/gpio-timing-control.md` + `gpio-control-logic-error.md` | `/guides/platform-configuration/gpio-timing-and-error.mdx` | ✅ 已合并 |
| 20 | `platform-configuration/device-behavior-id.md` | `/guides/platform-configuration/device-behavior-id.mdx` | ✅ 已转换 |
| 21 | `platform-configuration/custom_command_variable.md` | `/guides/platform-configuration/custom-command-variable.mdx` | ✅ 已转换 |
| 22 | `platform-configuration/variable-control-setup.md` | `/guides/platform-configuration/variable-control-setup.mdx` | ✅ 已转换 |

### 语音模块（18 models → 4 pages）

| # | 源文件路径 | 目标路径 | 状态 |
|---|-----------|---------|------|
| 23 | `offline-voice-su*/su-*-t.md` (9 SU models) | `/modules/offline-voice/su-series.mdx` | ✅ 已合并 |
| 24 | `offline-voice-ci*/ci-*-t[2].md` (6 CI models + ci73t2) | `/modules/offline-voice/ci-series.mdx` | ✅ 已合并 |
| 25 | `offline-voice-jxb5c/jx-b5c.md` | `/modules/offline-voice/jx-b5c.mdx` | ✅ 已转换（独立文件） |

### AI 智能体（5→4 页面）

| # | 源文件路径 | 目标路径 | 状态 |
|---|-----------|---------|------|
| 26 | `ai-agents/get-started.md` → `tutorial.md` | `/guides/ai-agents/get-started.mdx` + `index.mdx` | ✅ 已合并重构 |
| 27 | `ai-agents/knowledge-base-setup.md` | `/guides/ai-agents/knowledge-base.mdx` | ✅ 已转换 |
| 28 | `ai-agents/platform-guide.md` → `ai-agent.md` | `/guides/ai-agents/console.mdx` | ✅ 已合并 |

### WiFi 模块（3→1 页面）

| # | 源文件路径 | 目标路径 | 状态 |
|---|-----------|---------|------|
| 29 | `wifi-jx12f/jx-12f.md` + `wifi-bl62b/bl-62b.md` + `wifi-image-xr50a/xr-50a.md` | `/modules/wifi/index.mdx` | ✅ 已合并 |

### 其他独立页面（单文件 → 单文件）

| # | 源文件路径 | 目标路径 | 状态 |
|---|-----------|---------|------|
| 30 | `index.md` | `/index.mdx` | ✅ 已转换 |
| 31 | `tags.md` | `/tags.mdx` | ✅ 已转换 |
| 32 | `disclaimer.md` | `/reference/disclaimer.mdx` | ✅ 已转换 |
| 33 | `block-programming/block-programming.md` | `/reference/block-programming/index.mdx` | ✅ 已转换 |
| 34 | `chip/chip.md` | `/reference/chip/index.mdx` | ✅ 已转换 |
| 35 | `open-source/open-source.md` | `/reference/open-source/index.mdx` | ✅ 已转换 |
| 36 | `knowledge-base/kb-creation-guide.md` | `/reference/knowledge-base-guide.mdx` + `guides/ai-agents/knowledge-base.mdx` | ✅ 已拆分 |
| 37 | `miniapp-guide/miniapp-guide.md` | `/guides/miniapp-guide/index.mdx` | ✅ 已转换 |
| 38 | `platform-cases/platform-cases.md` + `tutorials-examples/tutorials.md` | `/examples/platform-cases/index.mdx` + `guides/tutorials/index.mdx` | ✅ 已拆分 |
| 39 | `product-design-guide/design-guide.md` → `faq-hardware-design` merged content | `/guides/hardware-design/product-design.mdx` | ✅ 已整合 |
| 40 | `offline-online-ai-jxa7t/jx-a7t.md` | `/modules/ai-modules/jx-a7t.mdx` | ✅ 已转换 |
| 41 | `online-voice-tmall/tmall-genie.md` + voice tuning content | `/guides/voice-tuning/tmall-genie.mdx` | ✅ 已合并 |
| 42 | `module-performance/module-selection.md` (superseded by selection-guide) | — | ⏭️ 内容已并入 /modules/selection-guide.mdx，源文件未迁移 |


---

## 导航审计（2026-05-07）

### Q-NAV-STRUC-02: 文档结构合理性审查

| 变更项 | 变更前 | 变更后 | 原因 |
|--------|--------|--------|------|
| docs.json `模组资料` 导航组 | "固件配置" + "离线语音模组" 两组重叠 | 移除"固件配置"，重命名"离线语音模组"为"产品规格" | 两组内容交叉引用同一型号文件，用户困惑；配置类指南应归入 Guides/平台配置 |
| ai-voice/index.mdx Card href | `href="/modules/firmware-configuration/su-series"`（错误链接） | 移除 href（由内层 Card 导航到 jx-a7t） | AI+离线双模卡片描述的是 JX-A7T，不应跳转到 SU 固件配置页 |
| modules/index.mdx Card | "固件配置" → `/modules/firmware-configuration/su-series` | "平台配置" → `/guides/platform-configuration/workflow` | 与导航结构调整一致，链接到通用平台配置流程页 |

**影响范围**: docs.json, modules/ai-voice/index.mdx, modules/index.mdx (3 files)  
**保留文件**: `modules/firmware-configuration/su-series.mdx`, `modules/firmware-configuration/ci-series.mdx` 仍存在于磁盘但不在导航中（可通过内部链接或搜索访问）
