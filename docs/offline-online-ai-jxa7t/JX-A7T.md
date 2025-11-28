---
title: 离在线语音AI大模型模组 JX-A7T
icon: material/robot-outline
description: 集成离线唤醒与在线大模型能力的语音 AI 模组 JX-A7T 使用与设计指南。
---

# 离在线语音AI大模型模组 JX-A7T

## 文档定位与适用场景
- 适用于语音助手、智能音箱、多模态交互终端。
- 提供离线唤醒、在线大模型回答、本地 TTS 的混合能力。

## 模组概述与规格参数

JX-A7T 是一款离在线语音AI大模型模组，集成语音芯片和WiFi芯片，支持离线唤醒识别和在线大模型对话功能。

| 指标 | 内容 |
| --- | --- |
| 架构 | 双芯片方案：语音芯片 + WiFi芯片 |
| 语音能力 | 离线唤醒词、离线命令词识别、在线AI大模型对话 |
| 网络连接 | WiFi (2.4GHz) + Bluetooth |
| 应用场景 | 智能音箱、语音助手、多模态交互终端 |
| 开发平台 | 智能公元平台（智能体配置） |

> 完整资料参考：
> - [JX-A7T 官方文档](https://help.aimachip.com/docs/jx_a7t_v1)
> - [规格书](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1gfqjpp5sdmt9)
> - [原理图](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1gfqjq17crdse)
> - [模块封装](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1gisoqu149bqg)

## 硬件设计指南
1. 供电：支持 5V 输入，内部稳压至各芯片所需电压。
2. 音频：I2S 接口连接功放与麦克风阵列，布线等长。
3. 天线：WiFi 天线设计，预留调试口与校准点。
4. 参考设计：查看[开发板使用说明书](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1gi6kkmkp65i2)

> 硬件设计参考：
> - [产品结构声学规范](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1ghc3ci6bo9fa)
> - [喇叭和咪头选型](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1ghc3cpavk4ck)

## 开发环境搭建与工具准备
- [JX-A7T开发包 V2.1.4](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1ghc1h40pidif)
- [CH340驱动](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1ghc1dt9vbgb5) - USB转串口驱动
- [烧录软件](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1ghc1e6ojmi46) - 包含语音部分和WiFi部分
- [串口调试工具](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1ghc1eq7ahnev)
- 智能公元平台账号（配置智能体和在线能力）

## 固件烧录与升级指南

### 烧录准备
1. 安装 CH340 驱动，连接开发板。
2. 下载烧录软件，分为语音部分和WiFi部分。
3. 参考[烧录文档](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1ghc1edqjakge)进行操作。

### 烧录步骤
1. 语音芯片烧录：使用[语音部分烧录软件](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1ghc2srur3hse)
2. WiFi芯片烧录：使用[WiFi部分烧录软件](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1ghc2t1f6ka09)
3. 烧录完成后，配置WiFi连接和智能体绑定。

### 出厂固件
- [语音部分出厂固件](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1ghc2t8amj6vq)
- [WiFi部分出厂固件](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1ghc2tdi1r389)

## 智能体平台配置

JX-A7T 通过智能公元平台进行配置，支持自定义唤醒词、命令词和在线AI对话能力。

- [操作指南](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1gfqk1bgtl1q1)
- [智能体平台配置指导手册](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1gk6kmfs6nkqm)
- [接外部模型示例手册](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1gl3c9n4ha304)
- [试用智能体](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1gkfmsllds4ao)

### 离在线混合模式
- **离线模式**：配置本地词表和命令，保证断网时仍可响应核心控制。
- **在线模式**：连接云端大模型服务，实现自然语言对话。
- **混合模式**：离线快速响应 + 在线智能对话，根据场景自动切换。

