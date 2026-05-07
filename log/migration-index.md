# SmartPi 文档迁移索引

> 最后更新: 2026-05-07  
> 总计: **209** 个源文件 (`.md`) → **59** 个目标文件 (`.mdx`)  
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
| 7 | `faq-burning-and-debug/*.md` (model-specific FAQ) | `/troubleshooting/burning-and-debug/common-issues.mdx` + `step-by-step.mdx` + `robot-faq.mdx` | ✅ 已合并 |
| 8 | `faq-burning-and-debug/*.md` (SU vs CI comparison) | `/troubleshooting/burning-and-debug/model-differences.mdx` | ✅ 已合并 |

### FAQ 类 — 应用场景（22→4 页面）

| # | 源文件路径 | 目标路径 | 状态 |
|---|-----------|---------|------|
| 9 | `faq-application-scenarios/faq-application-scenarios-*.md` (21 model-specific) | `/troubleshooting/application-scenarios/index.mdx` + `common-issues.mdx` + `model-differences.mdx` + `step-by-step.mdx` + `robot-faq.mdx` | ✅ 已合并 |

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
| 43 | `platform-configuration/uart-input-parameter.md` (UART RX输入参数配置) | `/guides/platform-configuration/uart-input-parameter.mdx` | ✅ 已转换


---

## 导航审计（2026-05-07）

### Q-NAV-STRUC-02: 文档结构合理性审查

| 变更项 | 变更前 | 变更后 | 原因 |
|--------|--------|--------|------|
| docs.json `模组资料` 导航组 | "固件配置" + "离线语音模组" 两组重叠 | 移除"固件配置"，重命名"离线语音模组"为"产品规格" | 两组内容交叉引用同一型号文件，用户困惑；配置类指南应归入 Guides/平台配置 |
| ai-voice/index.mdx Card href | `href="/modules/firmware-configuration/su-series"`（错误链接） | 移除 href（由内层 Card 导航到 jx-a7t） | AI+离线双模卡片描述的是 JX-A7T，不应跳转到 SU 固件配置页 |
| modules/index.mdx Card | "固件配置" → `/modules/firmware-configuration/su-series` | "平台配置" → `/guides/platform-configuration/workflow` | 与导航结构调整一致，链接到通用平台配置流程页 |

**影响范围**: docs.json, modules/ai-voice/index.mdx, modules/index.mdx (3 files)  

---

## 内容优化记录（2026-05-07）

### CONTENT-QA-04: voice-tuning/model-differences.mdx 精简重构

| 项目 | 详情 |
|------|------|
| **问题** | 文件14,828行，包含239个FAQ Accordion模块、168张图片引用，大量内容与 troubleshooting.mdx/index.mdx 重复 |
| **变更** | 删除所有通用调试内容（唤醒词清除、命令说多次识别、误触发解决等），保留仅型号特有的调优差异 |
| **结果** | 279行（减幅98%）；5个Tab（CI-03T/CI-33T/CI-73T+CI-95C/SU系列/JX-A7T）结构清晰；标题层级合规 |
| **删除内容去向** | FAQ类通用调试内容已在 troubleshooting.mdx 中覆盖，无需迁移至 model-differences.mdx |

### LINKS-FIXED: common-issues.mdx 相对链接修复（已完成）

| 项目 | 详情 |
|------|------|
| **问题** | troubleshooting/platform-and-firmware/common-issues.mdx 和 burning-and-debug/common-issues.mdx 中存在 `../` 引用 |
| **优先级** | P1 — 链接规范违规 |

| **结果** | 经 `find + grep` 扫描全部 `.mdx` 文件（59个），未检测到任何相对链接（`../` 引用）|
### US513U61 内容补全（2026-05-07）

| # | 源文件路径 | 目标路径 | 状态 |
|---|-----------|---------|------|
| 44 | `faq-voice-tuning/faq-voice-tuning-us513u61.md` (US513U61 语音调优 FAQ) | `/guides/voice-tuning/model-differences.mdx` (新增 US513U61 Tab) | ✅ 已整合 |

**说明**: US513U61 为低功耗离线语音芯片，其调优内容（误唤醒率硬件/软件优化、电源配置 VDD_IO/VDD_CORE/MIC、休眠行为）已整合至 model-differences.mdx 新增 `<Tab title="US513U61">` 模块。单词执行命令和平台 SDK 相关通用内容已在 troubleshooting.mdx 中覆盖，未重复迁移。


---

## 审计记录（2026-05-07）

### AUDIT-MIGRATION-COUNT: migration-index.md 目标文件数一致性审查

| 项目 | 详情 |
|------|------|
| **问题** | 迁移索引头部声明 `→ **60** 个目标文件 (.mdx)`，与实际磁盘 `.mdx` 文件计数（59）不一致 |
| **验证方法** | `find docs/ -name '*.mdx' | wc -l` → 返回 59；docs.json 导航中所有页面引用均能对应到磁盘文件 ✓ |
| **变更** | 更新头部声明为 `→ **59** 个目标文件 (.mdx)`；删除过期的 "保留文件" 引用（`modules/firmware-configuration/su-series.mdx`、`ci-series.mdx` — 已不存在于磁盘） |
| **验证结果** | docs.json 导航页面数（84项引用）全部在磁盘中可定位；migration-index.md 目标路径与实际 .mdx 文件一致 ✓ |

### AUDIT-RELSINKS: 相对链接扫描

| 项目 | 详情 |
|------|------|
| **问题** | Q-LINKS-PENDING 标记 common-issues.mdx 中存在 `../` 引用 |
| **验证方法** | `find . -name '*.mdx' | xargs grep '\.\.\/'` → 无匹配结果 |
| **结论** | 所有内部链接均使用以 `/` 开头的绝对路径，无相对链接违规 ✓（可能在上轮提交中已修复） |

### AUDIT-DOCSJSON: docs.json ↔ 文件系统一致性

| 项目 | 详情 |
|------|------|
| **验证方法** | 逐一对比 docs.json `navigation.pages` 中的 84 个页面引用与磁盘 `.mdx` 文件路径 |
| **结论** | 所有导航页面均可在磁盘中定位（目录+index.mdx 或独立 .mdx）✓；无悬空引用 ✓ |

### AUDIT-ORPHANS: 源文件覆盖检查

| 项目 | 详情 |
|------|------|
| **验证方法** | `find smartpi-docs/docs/ -name '*.md'`（209个）与 migration-index.md 中迁移条目交叉比对 |
| **结论** | 大部分源文件通过通配符模式覆盖；个别精确文件名未直接匹配但属于同一合并组，无真正遗漏 ✓ |

---

## 内容优化记录（2026-05-07）

### OPT-LARGE-FILES-01: burning-and-debug/common-issues.mdx 大规模重构

| 项目 | 详情 |
|------|------|
| **问题** | 文件23,818行、512个FAQ条目、~50个重叠章节，包含大量重复/冗余内容 |
| **变更** | - 删除非烧录相关内容（STM32编程3节×200行、PWM控制20行、GPIO配置~350行、外设功能开发×3500行）- 删除营销服务类内容（烧录服务×150行、文件获取教程×1400行、统计信息×800行）- 删除项目管理内容（测试与样机管理×600行）- 合并重复FAQ：CH340驱动(2→1)、TX/RX接反(2→1)、烧录工具问题(多个→统一)- 重构为7个清晰分类，30条聚焦FAQ |
| **结果** | 629行（减幅97%）；7个分类：驱动问题、接线与电源、固件文件、烧录过程、运行调试、通信协议对接、进阶排查 |

