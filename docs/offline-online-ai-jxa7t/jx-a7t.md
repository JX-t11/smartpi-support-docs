---
title: 离在线语音AI大模型模组 JX-A7T
icon: material/robot-outline
description: 集成离线唤醒与在线大模型能力的语音 AI 模组 JX-A7T 使用与设计指南。
---

# 离在线语音AI大模型模组 JX-A7T

## 快速规格一览

| 参数 | JX-A7T |
|------|--------|
| 架构 | **双芯片：语音芯片 CI1302 + WiFi芯片** |
| 处理器 | 32位 RISC CPU + BNPU V3 |
| 离线词条 | **300条**（本地命令词） |
| 在线能力 | **AI大模型对话** |
| WiFi | 802.11b/g/n + BLE 5.0 |
| 供电电压 | 3.6V ~ 5.5V |
| Flash | 2M（语音）+ 2M（WiFi） |
| 封装尺寸 | **28×31.5mm (SMD33)** |

### JX-A7T 定位

> JX-A7T 是 **离在线语音AI大模型模组**：
> - **离线能力**：本地唤醒词、命令词识别（300词）
> - **在线能力**：云端AI大模型自然语言对话
> - **混合模式**：离线快速响应 + 在线智能对话
> - **适用场景**：智能音箱、语音助手、AI陪伴玩具、智能家居控制中心

---

## 定位与适用场景

- **定位**：离在线混合语音AI模组，支持离线唤醒 + 在线大模型对话
- **适用场景**：
  - **智能音箱**：语音助手、智能家居控制
  - **AI玩具**：陪伴机器人、故事机
  - **多模态终端**：智能穿戴、智能家电
- **优势**：离线快速响应 + 在线智能对话，支持智能体平台配置

---

## 模组概述

JX-A7T 是一款离在线语音AI大模型模组，集成语音芯片（CI1302）和WiFi芯片，支持离线唤醒识别和在线大模型对话功能。

### 核心特性

| 指标 | 内容 |
|------|------|
| 架构 | 双芯片方案：语音芯片 CI1302 + WiFi芯片 |
| 处理器 | 32位RISC CPU + BNPU V3 |
| 语音能力 | 离线唤醒词、离线命令词识别（300词）、在线AI大模型对话 |
| 网络连接 | Wi-Fi 802.11b/g/n + BLE 5.0 |
| 供电电压 | 3.6-5.5V |
| Flash | 2M（语音）+ 2M（WiFi） |
| 识别率 | 95% |
| 封装 | SMD33 (28×31.5mm) |
| 功放功率 | VCC 5V 4Ω负载最高可达 1W |

### 高级功能支持

| 功能 | 支持情况 |
|------|---------|
| AEC（回声消除） | ✓ |
| 双麦算法 | ✓ |
| 自然说 | ✓ |
| 声纹识别 | ✓ |
| 声源定位 | ✓ |
| 哭声检测 | ✓ |
| 鼾声检测 | ✓ |
| 文字转语音(TTS) | ✓ |
| 自学习 | ✓ |
| 蓝牙/小程序 | ✓ (BLE 5.0) |
| 小程序修改语音指令 | ✓ (OTA升级) |
| 云端AI大模型 | ✓ |

### 应用场景

- 智能音箱、语音助手
- 智能家居控制中心
- 多模态交互终端
- AI 陪伴玩具
- 智能穿戴设备

---

## 官方资料下载

### 规格书与设计文档

| 文档 | 下载链接 |
|------|---------|
| 官方文档首页 | [查看](https://help.aimachip.com/docs/jx_a7t_v1) |
| JX-A7T 模组规格书 V1.1 | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1194) |
| JX-A7T 电气原理图 V1.1 | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1156) |
| JX-A7T 模块封装 | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1198) |
| 开发板使用指南 | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1185) |
| 产品结构声学设计规范 | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1179) |
| 喇叭（扬声器）选型 | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1180) |
| 麦克风（咪头）选型 | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1181) |

### 芯片资料

| 芯片 | 文档 |
|------|------|
| CI1302 语音芯片（中文） | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1177) |
| CI1302 语音芯片（英文） | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1178) |

---

## 硬件设计指南

### 设计要点

1. **供电设计**
   - 支持 3.6-5.5V 输入
   - 内部 3.3V LDO 输出，外部负载最大 200mA
   - 工作电流 >800mA（4Ω喇叭），待机电流 ~55mA

2. **音频接口**
   - I2S 接口连接功放与麦克风阵列
   - 布线等长，注意信号完整性
   - 支持双麦克风输入

3. **天线设计**
   - WiFi/BLE 天线需注意净空区
   - 预留调试口与校准点

4. **接口资源**
   - 2路 UART / 1路 I2C / 5路 PWM
   - 语音部分 7个 GPIO + WiFi部分 9个 GPIO

### 参考设计文档

| 文档 | 链接 |
|------|------|
| 开发板使用指南 | [下载PDF](https://help.aimachip.com/attach_files/jx_a7t_v1/1185) |
| 产品结构声学规范 | [查看](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1ghc3ci6bo9fa) |
| 喇叭和咪头选型 | [查看](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1ghc3cpavk4ck) |

---

## 开发环境搭建

### 驱动与工具下载

| 工具 | 说明 | 下载链接 |
|------|------|---------|
| JX-A7T 开发包 V2.1.4 | SDK 和开发资源 | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1241) |
| CH340 驱动 | USB转串口驱动 | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1171) |
| ASR 语音部分烧录软件 | 语音芯片烧录工具 | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1172) |
| WiFi 在线部分烧录软件 | WiFi芯片烧录工具 | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1173) |
| 串口调试软件 | 串口通信调试 | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1176) |

### 环境准备

1. 安装 CH340 USB转串口驱动
2. 安装烧录软件（语音部分 + WiFi部分）
3. 注册智能公元平台账号（配置智能体和在线能力）

---

## 固件烧录指南

### 烧录文档

- [JX-A7T 烧录指引文档 V1.0](https://help.aimachip.com/attach_files/jx_a7t_v1/1240)

### 烧录步骤

1. **准备工作**
   - 安装 CH340 驱动
   - 连接开发板至电脑
   - 确认 COM 口识别正常

2. **语音芯片烧录**
   - 使用 [ASR 语音部分烧录软件](https://help.aimachip.com/attach_files/jx_a7t_v1/1172)
   - 选择对应的固件文件
   - 按照软件提示完成烧录

3. **WiFi芯片烧录**
   - 使用 [WiFi 在线部分烧录软件](https://help.aimachip.com/attach_files/jx_a7t_v1/1173)
   - 选择对应的固件文件
   - 按照软件提示完成烧录

4. **配置联网**
   - 烧录完成后，配置WiFi连接
   - 通过小程序绑定智能体

### 出厂固件下载

| 固件 | 下载链接 |
|------|---------|
| 语音部分出厂固件 (JX-A7T_ASR) | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1225) |
| 语音部分 JSON 配置 | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1226) |
| WiFi部分出厂固件 (A7T_WIFI) | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1201) |
| WiFi部分 JSON 配置 | [下载](https://help.aimachip.com/attach_files/jx_a7t_v1/1202) |

---

## 智能体平台配置

JX-A7T 通过智能公元平台进行配置，支持自定义唤醒词、命令词和在线AI对话能力。

### 配置文档

| 文档 | 说明 | 下载链接 |
|------|------|---------|
| 操作指示文档 | Demo 操作流程 | [下载PDF](https://help.aimachip.com/attach_files/jx_a7t_v1/1242) |
| 智能体平台配置指导手册 | 完整配置教程 | [下载PDF](https://help.aimachip.com/attach_files/jx_a7t_v1/1208) |
| 接外部模型示例手册 | 自定义大模型接入 | [下载PDF](https://help.aimachip.com/attach_files/jx_a7t_v1/1216) |

### 示例资源

| 资源 | 下载链接 |
|------|---------|
| 智能体平台示例 | [下载RAR](https://help.aimachip.com/attach_files/jx_a7t_v1/1232) |
| 知识库示例 | [下载RAR](https://help.aimachip.com/attach_files/jx_a7t_v1/1217) |

### 离在线混合模式

| 模式 | 说明 |
|------|------|
| **离线模式** | 配置本地词表和命令，保证断网时仍可响应核心控制（300词） |
| **在线模式** | 连接云端大模型服务，实现自然语言对话 |
| **混合模式** | 离线快速响应 + 在线智能对话，根据场景自动切换 |

### 快速体验

访问[试用智能体](https://help.aimachip.com/docs/jx_a7t_v1/jx_a7t_v1-1gkfmsllds4ao)页面，可快速体验 JX-A7T 的语音交互能力。

---

## 参考链接

| 资源 | 链接 |
|------|------|
| JX-A7T 官方文档首页 | [https://help.aimachip.com/docs/jx_a7t_v1](https://help.aimachip.com/docs/jx_a7t_v1) |
| 智能公元平台 | [https://smartpi.cn](https://smartpi.cn) |
| 智能体文档 | [https://help.aimachip.com/docs/agent](https://help.aimachip.com/docs/agent) |

