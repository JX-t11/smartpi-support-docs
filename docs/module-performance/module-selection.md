---
title: 模块性能与选型
icon: lucide/sliders-horizontal
description: 面向售前与硬件工程师的模组性能对比与应用选型指南。
---

# 模块性能与选型

## 文档定位与适用场景
- 面向售前、硬件与方案工程师，帮助快速选择合适模组。

## 模组产品线概览
- 离线语音：CI/SU 系列（多场景词表、本地低延时）。
- 在线语音：JX-A7T、天猫精灵等（云端能力、可扩展性）。
- 联网与视觉：BL-62B、JX-12F、XR-50A 等。

## 主要性能参数对比
| 模组 | 语音能力 | 处理器 | 存储 | 网络 | 典型功耗 |
| --- | --- | --- | --- | --- | --- |
| CI-03T | 离线 150 词 | TODO | TODO | 无 | TODO |
| SU-20T | 离线 200 词 | TODO | TODO | 无 | TODO |
| JX-A7T | 离/在线混合 | TODO | TODO | Wi-Fi | TODO |
| BL-62B | 联网模组 | TODO | TODO | Wi-Fi | TODO |

> TODO: auto_get/downloaded_aimachip/docs/module_parameters/module_parameters-1f3jhb269luet.md 的真实数据。

## 选型指南与建议
1. 按交互方式：离线（低延时）、在线（高自由度）、混合（兼顾）。
2. 按硬件资源：若主控资源有限可选择模块化方案，需深度定制时使用开放 SDK。
3. 按联网需求：需要视频选 XR-50A，只需语音控制可用 CI/SU + WiFi 组合。

## 应用场景推荐
- 家电：CI-03T + BL-62B。
- 智能音箱：JX-A7T + 定制功放。
- 工业告警：SU-23T + 小程序监控。

## 选型表维护
- 与硬件/产品团队定期交叉校验参数，新增模组时补充条目。

| 日期 | 改动 | 数据来源 |
| --- | --- | --- |
| TODO | TODO | TODO |
