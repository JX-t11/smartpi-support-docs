---
title: 离线语音模组 SU-11T
icon: material/microphone
description: 低成本离线语音模组 SU-11T 完整开发指南，丰富的外设接口，适合智能家居应用。
---

# 离线语音模组 SU-11T

## 快速规格一览

| 参数 | SU-11T |
|------|--------|
| 主控芯片 | 蜂鸟M1 (US518P61) |
| 架构 | 32bit RISC @240MHz |
| 词条数 | **50**（推荐） |
| 供电电压 | 5V |
| 接口 | UART, I2C, SPI, PWM, ADC |
| 功放 | **2.4W**（内置AB类） |
| Flash | 1M |
| AEC | ✗ |
| 封装 | **SMD**（21x15mm） |

### SU-11T 定位

> SU-11T 是 **外设接口丰富的低成本模组**：

> - **特点**：接口丰富（I2C/SPI/ADC），方便扩展传感器或外设
> - **对比 SU-10A**：体积更小（与 SU-03T 相同），接口更多，但Flash较小（1M）
> - **适用场景**：需要读取传感器数据或驱动其他芯片的语音产品

---

## 定位与适用场景

- **定位**：低成本、低功耗、小体积的离线语音识别模组，具备丰富外设
- **适用场景**：

    - **智能家电**：温控器、加湿器（需接温湿度传感器）
    - **智能照明**：调光灯、彩灯（需PWM控制）
    - **智能玩具**：互动玩具（需检测传感器）
    - **其他**：86盒、开关面板
- **优势**：接口丰富、成本低、体积小
- **注意**：不支持 AEC，无法打断唤醒

---

## 模组概述

SU-11T 是一款低成本、低功耗、小体积的离线语音识别模组，具有丰富的系统外设资源，包括 UART、I2C、SPI、PWM、ADC 等，能快速应用于智能家居，各类智能小家电，86盒，玩具，灯具等需要语音操控的产品。

### 核心特性

| 指标分类 | 参数项 | 规格/数值 |
|---------|-------|----------|
| **核心性能** | CPU | 32bit RISC 内核 @ 240MHz |
| | 运算单元 | DSP 指令集 + FPU 浮点运算单元 |
| | 加速器 | FFT 加速器 (最大1024点复数/2048点实数) |
| **存储资源** | SRAM | 高速 SRAM |
| | Flash | 1MB |
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
| 官方文档首页 | [查看](https://help.aimachip.com/docs/offline_su11t) |
| 开发手册 | [下载](https://help.aimachip.com/docs/offline_su11t/offline_su11t-1e9cl47e5drim) |
| 芯片资料 | [查看](https://help.aimachip.com/docs/offline_su11t/offline_su11t-1e9eev2eeksg0) |
| 烧录资料 | [下载](https://help.aimachip.com/docs/offline_su11t/offline_su11t-1e9cl4b9cdcmi) |
| 模组规格书 V1.0 | [下载](https://help.aimachip.com/attach_files/offline_su11t/208) |
| 原理图 V1.0 | [下载](https://help.aimachip.com/attach_files/offline_su11t/209) |

---


## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具

### 开发工具下载

| 工具 | 说明 | 下载链接 |
|------|------|---------|
| 开发手册 | 离线方案开发指导 | [下载](https://help.aimachip.com/docs/offline_su11t/offline_su11t-1e9cl47e5drim) |
| 烧录资料 | 烧录工具与驱动 | [下载](https://help.aimachip.com/docs/offline_su11t/offline_su11t-1e9cl4b9cdcmi) |

### 芯片资料

- [蜂鸟M1 (US518P61) 芯片资料](https://help.aimachip.com/docs/offline_su11t/offline_su11t-1e9eev2eeksg0)

---


## 固件烧录与升级指南
1. 通过 USB/UART 将固件写入 Flash。
2. 使用配置工具导入词表、编译后烧录。
3. 复位设备并播放测试词表确认成功。

## 指令集 / 词表配置
- 支持多场景词表，结构为“唤醒词 → 命令组 → 动作”。
- 串口协议：0xAA 0x55 CMD LEN DATA CS（详见旧文档）。

> 开发参考：
> - [烧录资料](https://help.aimachip.com/docs/offline_su11t/offline_su11t-1e9cl4b9cdcmi)
> - [芯片资料](https://help.aimachip.com/docs/offline_su11t/offline_su11t-1e9eev2eeksg0)
---

## 参考链接

| 资源 | 链接 |
|------|------|
| SU-11T 官方文档首页 | [https://help.aimachip.com/docs/offline_su11t](https://help.aimachip.com/docs/offline_su11t) |
| 智能公元平台 | [https://smartpi.cn](https://smartpi.cn) |
| SU-10A 文档（参考） | [https://help.aimachip.com/docs/offline_su10a](https://help.aimachip.com/docs/offline_su10a) |

