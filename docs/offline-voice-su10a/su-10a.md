---
title: 离线语音模组 SU-10A
icon: material/microphone
description: 低成本离线语音模组 SU-10A 完整开发指南，内置3W功放，适合小家电应用。
---

# 离线语音模组 SU-10A

## 快速规格一览

| 参数 | SU-10A |
|------|--------|
| 主控芯片 | 蜂鸟M (US516P6) |
| 架构 | 32bit RISC @240MHz |
| 词条数 | **50**（推荐） |
| 供电电压 | 5V |
| 接口电平 | 默认5V（可改3.3V） |
| 功放 | **3W**（内置AB类） |
| Flash | 2M |
| AEC | ✗ |
| 封装 | **SMD**（26x15mm） |

### SU-10A 定位

> SU-10A 是 **集成度极高的低成本模组**：
> - **特点**：内置 3W 功放，可直接驱动 4Ω/3W 喇叭
> - **接口**：UART 默认 5V 电平，兼容 5V 单片机
> - **适用场景**：需要较大声音播报的低成本产品

---

## 定位与适用场景

- **定位**：低成本、低功耗、小体积的离线语音识别模组
- **适用场景**：

    - **智能家电**：电饭煲、风扇、取暖器
    - **智能照明**：吸顶灯、台灯
    - **智能玩具**：故事机、机器人
    - **其他**：86盒、开关面板
- **优势**：内置大功率功放(3W)、5V供电、成本低
- **注意**：不支持 AEC，无法打断唤醒

---

## 模组概述

SU-10A 是一款低成本、低功耗、小体积的离线语音识别模组，能快速应用于智能家居，各类智能小家电，86盒，玩具，灯具等需要语音操控的产品。

### 核心特性

| 指标分类 | 参数项 | 规格/数值 |
|---------|-------|----------|
| **核心性能** | CPU | 32bit RISC 内核 @ 240MHz |
| | 运算单元 | DSP 指令集 + FPU 浮点运算单元 |
| | 加速器 | FFT 加速器 (最大1024点复数/2048点实数) |
| **存储资源** | SRAM | 高速 SRAM |
| | Flash | 2MB |
| **音频接口** | 麦克风 | 支持 1 路驻极体麦 |
| | 功放 | 内置 **3W** 单声道 AB 类功放 |
| **电源** | 供电范围 | 5V 电源输入 |
| **外设接口** | UART | 默认 5V 电平（支持改 3.3V） |
| **系统** | RTOS | 支持 RTOS 轻量级系统 |
| | 词条数 | 最多 100 条本地指令 |

### 官方资料下载

| 资料 | 链接 |
|------|------|
| 官方文档首页 | [查看](https://help.aimachip.com/docs/offline_su10a) |
| 开发手册 | [下载](https://help.aimachip.com/docs/offline_su10a/offline_su10a-1e9cl76gk7dg4) |
| 芯片资料 | [查看](https://help.aimachip.com/docs/offline_su10a/offline_su10a-1e9eevuotgmdg) |
| 调试工具 | [下载](https://help.aimachip.com/docs/offline_su10a/offline_su10a-1e9cl7oj0frb8) |
| 模组规格书 V1.0 | [下载](https://help.aimachip.com/attach_files/offline_su10a/210) |
| 原理图 V1.1 | [下载](https://help.aimachip.com/attach_files/offline_su10a/211) |
| 离线方案开发指导手册 | [下载](https://help.aimachip.com/attach_files/offline_su10a/213) |
| 环境搭建 | [下载](https://help.aimachip.com/attach_files/offline_su10a/212) |
| SSCOM 串口调试工具 | [下载](https://help.aimachip.com/attach_files/offline_su10a/214) |

---


## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具

### 开发工具下载

| 工具 | 说明 | 下载链接 |
|------|------|---------|
| 开发手册 | 离线方案开发指导 | [下载](https://help.aimachip.com/docs/offline_su10a/offline_su10a-1e9cl76gk7dg4) |
| 调试工具 | 串口调试助手 | [下载](https://help.aimachip.com/docs/offline_su10a/offline_su10a-1e9cl7oj0frb8) |
| 环境搭建 | 开发环境搭建指南 | [查看](https://help.aimachip.com/attach_files/offline_su10a/212) |

### 芯片资料

> **蜂鸟M (US516P6)** 是云知声针对大量纯离线控制场景推出的低成本纯离线语音识别芯片。
> - 采用 32bit RISC 架构内核
> - 加入专门针对信号处理和语音识别的 DSP 指令集
> - 支持浮点运算的 FPU 运算单元及 FFT 加速器
> - 支持 100 条本地指令离线识别
> - 支持 RTOS 轻量级系统

| 资料 | 链接 |
|------|------|
| 蜂鸟M 芯片资料首页 | [查看](https://help.aimachip.com/docs/offline_su10a/offline_su10a-1e9eevuotgmdg) |
| 蜂鸟M 芯片详情 | [查看](http://help.aimachip.com/docs/chip/chip-1e9c8pck1n820) |
| 蜂鸟M SOC产品手册(补充) | [下载](https://help.aimachip.com/attach_files/chip/461) |
| 蜂鸟M 离线方案开发指导手册 | [下载](https://help.aimachip.com/attach_files/chip/34) |
| 蜂鸟M 语音性能优化指导手册 | [下载](https://help.aimachip.com/attach_files/chip/33) |

---


## 固件烧录与升级指南

> **注意**：空芯片内部没有基础固件，不支持串口烧录。如需串口烧录，需先用调试烧录器或离线烧录器烧录基础固件。购买芯片时请与销售沟通。

1. 通过 USB/UART 将固件写入 Flash。
2. 使用配置工具导入词表、编译后烧录。
3. 复位设备并播放测试词表确认成功。

## 指令集 / 词表配置
- 支持多场景词表，结构为“唤醒词 → 命令组 → 动作”。
- 串口协议：0xAA 0x55 CMD LEN DATA CS（详见旧文档）。

> 开发参考：
> - [开发手册](https://help.aimachip.com/docs/offline_su10a/offline_su10a-1e9cl76gk7dg4)
> - [调试工具](https://help.aimachip.com/docs/offline_su10a/offline_su10a-1e9cl7oj0frb8)
---

## 参考链接

| 资源 | 链接 |
|------|------|
| SU-10A 官方文档首页 | [https://help.aimachip.com/docs/offline_su10a](https://help.aimachip.com/docs/offline_su10a) |
| SU-10A 规格书页面 | [查看](https://help.aimachip.com/docs/offline_su10a/offline_su10a-1e9c65hbi4kra) |
| 蜂鸟M 芯片资料 | [https://help.aimachip.com/docs/chip/chip-1e9c8pck1n820](https://help.aimachip.com/docs/chip/chip-1e9c8pck1n820) |
| 智能公元平台 | [https://smartpi.cn](https://smartpi.cn) |
| SU-03T 文档（参考） | [https://help.aimachip.com/docs/offline_su03t](https://help.aimachip.com/docs/offline_su03t) |
