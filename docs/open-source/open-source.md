---
title: 开源仓库
icon: fontawesome/brands/github
description: 智能公元相关官方开源项目与示例工程的索引与使用说明。
---

# 开源仓库

## 文档定位与适用场景
- 面向需要复用官方开源工程的开发者。
- 目标：快速了解仓库列表、功能、依赖与贡献方式。

## 开源项目概览
| 仓库 | 功能 | 适配模组 | 语言 |
| --- | --- | --- | --- |
| TODO: auto_get/downloaded_aimachip/docs/kyck/CI_03t_05.md | 语音控制 Demo | CI-03T | C/Arduino |
| TODO: auto_get/downloaded_aimachip/docs/kyck/su_03t_count123.md | 计数示例 | SU-03T | C |
| TODO: auto_get/downloaded_aimachip/docs/kyck/su_61t_01.md | 在线语音示例 | SU-61T | C++ |

## 热门项目推荐
1. **CI-03T 串口对接**：封装 AT 指令、实现状态机，适合快速联调。
2. **SU 系列计数器**：展示语音指令与 IO 控制结合方式。

## 项目获取与编译
1. `git clone <repo>`。
2. 根据 README 配置工具链（GCC/Keil/Arduino IDE）。
3. 运行 `make flash` 或使用官方烧录工具完成下载。

> TODO: auto_get/downloaded_aimachip/docs/kyck/kyck-1eee8pp458hem.md 的依赖与脚本示例。

## 贡献代码指南
- 提交前运行格式化、lint、单元测试。
- PR 中说明适配模组、测试环境、影响范围。
- 遵循仓库分支策略与 issue 模板。

## 维护与版本对齐
- 定期验证示例仍能编译/运行。
- 标记已归档或不再维护的仓库。

| 日期 | 仓库 | 变更 | 备注 |
| --- | --- | --- | --- |
| TODO | TODO | TODO | TODO |
