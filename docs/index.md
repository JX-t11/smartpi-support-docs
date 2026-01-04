---
title: 智能公元文档
icon: lucide/book-open
description: 智能公元平台在不同模组、平台入口以及工具链上的统一操作与开发文档。
---

# 智能公元文档
 
智能公元平台在不同模组、平台入口以及工具链上的统一操作与开发文档。

- 覆盖硬件模组（WiFi、离线语音、AI 模组等）的接线、烧录、调试与量产
- 提供平台与工具（小程序平台、Block 积木编程等）的使用指引
- 汇总常见问题、示例工程和开源资源，方便查阅与协作

!!! tip "第一次来，可以这样阅读"
    1. 从 **平台与通用指南** 了解整体能力和工具链。
    2. 在 **模组与硬件章节** 找到你当前使用的模组型号。
    3. 遇到共性问题，优先查看 **常见问题** 与 **教程和示例固件**。

## 平台使用与开发入门

<div class="grid cards" markdown>

- [固件配置全流程](platform-configuration/firmware-config-workflow.md)
    从创建产品到固件下载的完整可视化配置引导。
- [Block 积木编程](block-programming/block-programming.md)  
    图形化搭积木的方式编写逻辑，对零基础用户友好。
- [小程序平台操作指南](miniapp-guide/miniapp-guide.md)  
    智能公元小程序平台入口、项目管理与调试步骤。
- [教程和示例固件](tutorials-examples/tutorials.md)
    官方示例工程、演示固件与上手教程合集。
- [产品结构设计指南](product-design-guide/design-guide.md)  
    声学结构、喇叭与麦克风选型等产品设计建议。
- [芯片手册](chip/chip.md)  
    核心芯片的规格书、寄存器说明等原始技术资料。

</div>

## 智能体开发平台

<div class="grid cards" markdown>

- [快速开始](ai-agents/get-started.md)
    几分钟内完成你的第一个 AI 智能体创建与部署。
- [智能体功能介绍](ai-agents/ai-agent.md)  
    数字人 / 智能体相关概念、能力边界与使用方式总览。
- [知识库配置指南](ai-agents/knowledge-base-setup.md)
    如何上传文档并让 AI 学习你的私有知识库。
- [智能体开发教程](ai-agents/tutorial.md)
    从零到一开发具有特定功能的 AI 语音助手实战。

</div>

## 模组资料库

<div class="grid cards" markdown>

- [离在线语音 AI 模组 · JX-A7T](offline-online-ai-jxa7t/jx-a7t.md)  
    离在线语音识别 + AI 大模型接入模组，支持 WiFi。
- [离线语音 · SU 系列](offline-voice-su03t/su-03t.md) 
    包含 SU-03T, SU-10A, SU-32T, SU-63T 等全系列离线模组。
- [离线语音 · CI 系列](offline-voice-ci03t/ci-03t.md) 
    包含 CI-03T, CI-33T, CI-73T, CI-96Z 等高性能语音芯片模组。
- [WiFi 模组 · JX-12F / BL-62B](wifi-jx12f/jx-12f.md)  
    纯 WiFi 通信模组，提供 AT 指令、透传与配网指南。
- [WiFi 图像模组 · XR-50A](wifi-image-xr50a/xr-50a.md)  
    支持摄像头图像采集、实时传输与 WiFi 联网功能。
- [在线语音模组 · 天猫精灵](online-voice-tmall/tmall-genie.md)  
    天猫精灵生态接入模组，支持在线语音交互与控制。

</div>

## 常见问题与技术支持

<div class="grid cards" markdown>

- [烧录与调试 FAQ](faq-burning-and-debug/burning_and_debug.md)
    解决固件烧录失败、串口无日志、无法唤醒等初次使用问题。
- [硬件设计 FAQ](faq-hardware-design/hardware_design.md)
    电路接线、功放原理、电源稳定性等硬件相关避坑指南。
- [语音调优 FAQ](faq-voice-tuning/voice_tuning.md)
    提升唤醒灵敏度、降低误触发、解决播报音质问题。
- [平台与固件 FAQ](faq-platform-and-firmware/platform_and_firmware.md)
    关于平台账号、固件生成失败、变量逻辑控制等问题的解答。
- [模块选型指南](module-performance/module-selection.md)  
    对比各模组关键指标、功耗与识别距离，为项目选型提供参考。
- [开源仓库与案例](open-source/open-source.md)
    智能公元相关的开源 SDK、工具与典型应用案例归档。

</div>

## 学习资源

<div class="grid cards" markdown>

- **智能公元帮助中心**：[help.aimachip.com](https://help.aimachip.com/)
    官方技术文档中心，包含各模组详细规格资料。
- **B 站教程频道**：[机芯智能官方账号](https://space.bilibili.com/1903518159)
    包含开发环境搭建指导、实际操作演示和教程视频。

</div>


---

!!! note "声明"
    本站部分内容整理自技术交流群聊与社区问答，如有侵权请联系删除。[查看完整免责声明](disclaimer.md)