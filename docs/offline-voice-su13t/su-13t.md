---
title: 离线语音模组 SU-13T
icon: material/microphone
description: 低成本离线语音模组 SU-13T 完整开发指南，小体积，适合小家电应用。
---

# 离线语音模组 SU-13T

## 快速规格一览

| 参数 | SU-13T |
|------|--------|
| 主控芯片 | 32bit RISC @240MHz |
| 词条数 | **150** |
| 供电电压 | 5V |
| 接口 | UART, I2C, SPI, PWM, ADC |
| 功放 | **2.4W**（内置AB类） |
| Flash | 2M |
| AEC | ✗ |
| 封装 | **SMD** |

### SU-13T 定位

> SU-13T 是 **支持 RTOS 的小体积模组**：
> - **特点**：支持 150 条本地指令（比 SU-03T/SU-10A/SU-11T 多）
> - **系统**：支持 RTOS 轻量级系统
> - **适用场景**：智能门锁、扫地机、空调等需要较多指令的设备

---

## 定位与适用场景

- **定位**：低成本、低功耗、小体积的离线语音识别模组，支持 RTOS
- **适用场景**：

    - **智能家电**：风扇、空调、扫地机、茶壶
    - **智能安防**：智能门锁
    - **智能照明**：台灯
    - **其他**：86盒、玩具
- **优势**：指令条数多(150条)、RTOS系统、丰富接口
- **注意**：不支持 AEC，无法打断唤醒

---

## 模组概述

SU-13T 是一款低成本、低功耗、小体积的离线语音识别模组，该模块语音芯片采用 32bit RISC 架构内核，并加入了专门针对信号处理和语音识别所需要的 DSP 指令集，支持浮点运算的 FPU 运算单元，以及 FFT 加速器。

该方案支持 **150 条本地指令**离线识别，支持 **RTOS 轻量级系统**，具有丰富的外围接口，以及简单友好的客制化工具。

### 核心特性

| 指标分类 | 参数项 | 规格/数值 |
|---------|-------|----------|
| **核心性能** | CPU | 32bit RISC 内核 @ 240MHz |
| | 运算单元 | DSP 指令集 + FPU 浮点运算单元 |
| | 加速器 | FFT 加速器 (最大1024点复数/2048点实数) |
| **存储资源** | SRAM | 高速 SRAM |
| | Flash | 2MB |
| **音频接口** | 麦克风 | 支持 1 路驻极体麦 |
| | 功放 | 内置 **2.4W** 单声道 AB 类功放 |
| | 接口 | I2S input/output |
| **电源** | 供电范围 | 5V 电源输入 (内置5V->3.3V LDO) |
| | 对外供电 | 3.3V (负载≤150mA) |
| **外设接口** | UART | 1路全双工 (3Mbps) |
| | I2C | 1路 (400kHz) |
| | SPI | 1路Master + 1路Slave (30MHz) |
| | PWM | 2路 |
| | ADC | 1路 12-bit SAR-ADC (450Khz) |
| | GPIO | 所有 GPIO 可配置中断/唤醒 |

### 官方资料下载

| 资料 | 链接 |
|------|------|
| 官方文档首页 | [查看](https://help.aimachip.com/docs/offline_su13t) |
| 开发手册 | [下载](https://help.aimachip.com/docs/offline_su13t/offline_su13t-1e9cl1qm7i4t7) |
| 芯片资料 | [查看](https://help.aimachip.com/docs/offline_su13t/offline_su13t-1e9eeu6pmober) |
| 烧录资料 | [下载](https://help.aimachip.com/docs/offline_su13t/offline_su13t-1e9cl1u0u4vgo) |

---


## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具

### 开发工具下载

| 工具 | 说明 | 下载链接 |
|------|------|---------|
| 开发手册 | 离线方案开发指导 | [下载](https://help.aimachip.com/docs/offline_su13t/offline_su13t-1e9cl1qm7i4t7) |
| 烧录资料 | 烧录工具与驱动 | [下载](https://help.aimachip.com/docs/offline_su13t/offline_su13t-1e9cl1u0u4vgo) |

### 芯片资料

- [蜂鸟M (US516P6) 芯片资料](https://help.aimachip.com/docs/offline_su13t/offline_su13t-1e9eeu6pmober)

---

## 固件烧录与升级指南

1. 通过 USB/UART 将固件写入 Flash。
2. 使用配置工具导入词表、编译后烧录。
3. 复位设备并播放测试词表确认成功。

## 指令集 / 词表配置

- 支持多场景词表，结构为"唤醒词 → 命令组 → 动作"。
- 串口协议：0xAA 0x55 CMD LEN DATA CS（详见旧文档）。

> 开发参考：
> - [烧录资料](https://help.aimachip.com/docs/offline_su13t/offline_su13t-1e9cl1u0u4vgo)
> - [芯片资料](https://help.aimachip.com/docs/offline_su13t/offline_su13t-1e9eeu6pmober)

---

## 参考链接

| 资源 | 链接 |
|------|------|
| SU-13T 官方文档首页 | [https://help.aimachip.com/docs/offline_su13t](https://help.aimachip.com/docs/offline_su13t) |
| 智能公元平台 | [https://smartpi.cn](https://smartpi.cn) |
| SU-11T 文档（参考） | [https://help.aimachip.com/docs/offline_su11t](https://help.aimachip.com/docs/offline_su11t) |

