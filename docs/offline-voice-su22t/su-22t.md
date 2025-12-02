---
title: 离线语音模组 SU-22T
icon: material/microphone
description: 低功耗离线语音模组 SU-22T 完整开发指南，内置1W功放，适合电池供电产品。
---

# 离线语音模组 SU-22T

## 快速规格一览

| 参数 | SU-22T |
|------|--------|
| 主控芯片 | 32bit RISC @50MHz |
| 架构 | **低功耗语音专用 NPU** |
| 词条数 | **50**（推荐） |
| 供电电压 | **3.3V**（严禁5V） |
| 接口电平 | 3.3V |
| 功放 | **1W**（内置AB类） |
| Flash | 1MB |
| SRAM | 208KB |
| 识别距离 | 3-5米远场 |
| 封装 | **小体积** |

### SU-22T 定位

> SU-22T 是 **低功耗小体积模组**：
> - **特点**：内置 1W 功放，低功耗设计
> - **对比 SU-21T**：内置功放（SU-21T无功放）
> - **适用场景**：手持设备、电池供电产品、智能家居

---

## 定位与适用场景

- **定位**：低成本、低功耗、小体积的离线语音识别模组
- **适用场景**：

    - **智能家居**：86盒、灯具、开关面板
    - **智能小家电**：风扇、加湿器、空气净化器
    - **玩具产品**：故事机、互动玩偶
    - **电池供电产品**：手持风扇、遥控器
- **优势**：低延时、本地数据安全、内置功放
- **注意**：**供电电压必须为 3.3V**

---

## 模组概述

SU-22T 是一款低成本、低功耗、小体积的离线语音识别模组，能快速应用于智能家居、各类智能小家电、86盒、玩具、灯具等语音操控的产品。其低功耗特性亦特别适合于手持语音识别产品、电池供电产品等应用。支持50条本地指令离线3-5米远场识别，支持RTOS轻量级系统，具有丰富的外围接口。

### 功能框图
![功能框图](http://help.aimachip.com/uploads/offline_su22t/images/m_3d413b27beb6e1e7bd88ff442ca11fee_r.png "SU-22T功能框图")

### 外观尺寸
![尺寸图1](http://help.aimachip.com/uploads/offline_su22t/images/m_02b3765d97f7c018de8cbeff11976994_r.png "外观尺寸")
![尺寸图2](http://help.aimachip.com/uploads/offline_su22t/images/m_05ce407347c6b78fd1cb35e0ee00ac48_r.png "侧面尺寸")

### 核心特性

| 指标 | 内容 |
| --- | --- |
| 核心处理器 | 32bit 低功耗 RISC 内核 MCU @ 50MHz |
| 指令集 | 支持 DSP 指令集和 FPU 浮点运算单元 |
| NPU | 内置低功耗语音专用 NPU (神经网络处理单元) |
| 网络支持 | 支持 DNN/TDNN/LSTM 等主流网络 |
| 存储器 | 208KB SRAM + 1MB Flash |
| 音频输出 | 内置 1W 单声道 AB 类功放 |
| 麦克风 | 支持 1 路驻极体麦 |
| 供电 | 3.3V 电源输入 |
| 接口 | 1路UART, 2路I2C (400kHz), SPI (Master/Slave), PWM |
| 识别能力 | 支持50条本地指令，3-5米远场识别 |

### 官方资料下载

| 资料 | 链接 |
|------|------|
| 官方文档首页 | [查看](https://help.aimachip.com/docs/offline_su22t) |
| 规格书 V1.1 | [下载](https://help.aimachip.com/attach_files/offline_su22t/900) |
| 串口调试软件 | [下载](https://help.aimachip.com/attach_files/offline_su22t/910) |
| 喇叭和咪头选型 | [下载](https://help.aimachip.com/attach_files/offline_su22t/905) |

### 主要参数表
![主要参数](http://help.aimachip.com/uploads/offline_su22t/images/m_c86ce5cd6a7507255f7a4c632700c42e_r.png "详细参数表")

## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具

### 开发工具下载

| 工具 | 说明 | 下载链接 |
|------|------|---------|
| 串口调试软件 | 日志查看与命令调试 | [下载](https://help.aimachip.com/attach_files/offline_su22t/910) |
| 喇叭和咪头选型 | 音频器件选型参考 | [下载](https://help.aimachip.com/attach_files/offline_su22t/905) |

### 芯片资料

> **蜂鸟L系列 (US513U6/US513U61)** 是一颗亚毫瓦级超低功耗智能纯离线语音识别芯片，面向带电池和便携式产品以及对功耗有严苛要求的各类产品。
> - 采用 MCU + 语音识别专用 NPU 架构内核
> - 支持 DNN/TDNN/LSTM 等主流网络
> - 内置低功耗语音专用 NPU
> - 支持 50 条本地指令离线 3-5 米远场识别
> - 支持 RTOS 轻量级系统

| 资料 | 链接 |
|------|------|
| 蜂鸟L 芯片详情 | [查看](http://help.aimachip.com/docs/chip/chip-1e9c8p36onh9g) |
| 蜂鸟L SOC产品手册 | [下载](https://help.aimachip.com/attach_files/chip/427) |
| 蜂鸟L 离线方案开发指导手册 | [下载](https://help.aimachip.com/attach_files/chip/429) |
| 蜂鸟L 参考原理图 | [下载](https://help.aimachip.com/attach_files/chip/428) |

## 固件烧录与升级指南
1. 通过 USB/UART 将固件写入 Flash。
2. 使用配置工具导入词表、编译后烧录。
3. 复位设备并播放测试词表确认成功。

## 指令集 / 词表配置
- 支持多场景词表，结构为“唤醒词 → 命令组 → 动作”。
- 串口协议：0xAA 0x55 CMD LEN DATA CS（详见旧文档）。

> 教程参考：
> - [SU-22T语音控制四路继电器](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1epdknhetaa11) - [资料下载](https://help.aimachip.com/attach_files/offline_su22t/555)
> - [串口烧录教程](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1eqfq5oj20nn8) - [资料下载](https://help.aimachip.com/attach_files/offline_su22t/563)
> - [利用PWM灯光亮度调节和呼吸灯](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1eqg6058go5fd) - [资料下载](https://help.aimachip.com/attach_files/offline_su22t/564)
> - [SU-22T串口输入输出教学](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1eqifb3sfe2m9) - [资料下载](https://help.aimachip.com/attach_files/offline_su22t/565)

## 外设开发与应用示例
- 继电器：识别指令后驱动 GPIO 切换。
- 串口反馈：将识别到的词 ID 发给主控。
- 联动应用：与 WiFi 模组结合，实现语音+云端控制。

---

## 参考链接

| 资源 | 链接 |
|------|------|
| SU-22T 官方文档首页 | [https://help.aimachip.com/docs/offline_su22t](https://help.aimachip.com/docs/offline_su22t) |
| 蜂鸟L 芯片资料 | [https://help.aimachip.com/docs/chip/chip-1e9c8p36onh9g](http://help.aimachip.com/docs/chip/chip-1e9c8p36onh9g) |
| 智能公元平台 | [https://smartpi.cn](https://smartpi.cn) |
| SU-21T 文档（参考） | [https://help.aimachip.com/docs/offline_su21t](https://help.aimachip.com/docs/offline_su21t) |
