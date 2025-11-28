---
title: 教程和示例固件
icon: lucide/graduation-cap
description: 覆盖入门到进阶的教程与示例固件，提供从准备到验证的完整实践路径。
---

# 教程和示例固件

## 文档定位与适用场景
- 面向希望循序渐进学习的开发者，覆盖入门到进阶案例。
- 目标：提供“准备 → 配置 → 调试 → 验证”的完整路径。

## 教程概览
| 类别 | 内容 | 适用模组 | 来源 |
| --- | --- | --- | --- |
| 快速入门 | 点亮 LED、串口打印 | CI/SU 系列 | 官方 SDK |
| 进阶功能 | OTA、云端交互 | WiFi 模组 | auto_get/downloaded_aimachip/docs/tutorials-and-sample-firmware |
| 综合案例 | 语音+云端+App | 多模组 | 平台案例 |

## 环境搭建与基础工具
- 下载 SDK、安装编译器、配置串口与日志工具。
- 提供 `setup_env.sh`、`flash.bat` 等脚本模板。

## 基础入门教程
1. Hello World：串口打印验证工具链。
2. 词表下发：通过配置工具导入离线词表。
3. 联网配置：在 WiFi 模组上完成 STA 连接。

## 进阶功能示例
- OTA 升级：后台上传固件、设备下载、验证回滚。
- 云端属性同步：配置 MQTT Topic、推送属性。
- 多模组协同：语音触发 WiFi 模组控制继电器。

## 综合应用案例
- 拆分步骤并提供硬件连接图、串口日志、关键代码片段。
- 记录预期效果与常见错误。

> TODO: auto_get/downloaded_aimachip/docs/tutorials-and-sample-firmware/*.md 的详细教程链接与固件包。

## 教程/固件维护
- 发布新固件或教程时更新索引表并注明适配版本。

| 日期 | 教程/固件 | 版本 | 备注 |
| --- | --- | --- | --- |
| TODO | TODO | TODO | TODO |
