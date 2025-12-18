---
title: 离线语音模组 SU-03T
icon: material/microphone
description: 低成本离线语音模组 SU-03T 完整开发指南，适合低成本、小体积应用场景。
---

# 离线语音模组 SU-03T

## 快速规格一览

| 参数 | SU-03T |
|------|--------|
| 主控芯片 | 32bit RISC @240MHz |
| 综合识别率 | 90%+ |
| 供电电压 | 3.6-5.5V |
| 词条数 | **50**（推荐） |
| Flash | 2M |
| SRAM | 高速SRAM |
| AEC（回声消除） | ✗ |
| 双麦算法 | ✗ |
| 单/双麦 | 单麦（驻极体） |
| 适用环境 | 安静环境 |
| 待机电流 | 68mA（平均） |
| 工作电流 | >500mA (4Ω喇叭) |
| 功放功率 | 2.4W@5V4Ω |
| 封装 | **SMD18** |
| 尺寸 | 21×15mm |

### 高级功能支持

| 功能 | 支持情况 |
|------|---------|
| 自然说 | ✗ |
| 声纹识别 | ✗ |
| 声源定位 | ✗ |
| 哭声检测 | ✗ |
| 鼾声检测 | ✗ |
| 文字转语音(TTS) | ✗（仅播报预置录音） |
| 自学习 | ✗ |
| 平台能力 | 支持生成固件 |

### SU-03T 定位

> SU-03T 是 **入门级低成本模组**：

> - **优势**：成本极低，体积小，开发简单
> - **限制**：不支持 AEC（回声消除），抗噪能力较弱，词条数较少
> - **适用场景**：玩具、简单的语音控制设备（如开关、晾衣架）

---

## 定位与适用场景

- **定位**：低成本、低功耗、小体积的离线语音识别模组
- **适用场景**：

    - **智能家电**：风扇、晾衣架、加湿器、茶壶等
    - **智能照明**：台灯、吸顶灯、氛围灯
    - **智能玩具**：故事机、互动玩偶等
    - **其他**：86盒、语音面板等
- **优势**：低延时、本地数据安全、成本极低
- **注意**：不支持打断唤醒（因无AEC），播报时无法识别

### 授权与识别方式

**授权费用：**

- SU-03T模块**无需支付额外的License费用**
- 固件通过智能公元平台免费生成
- 无按产量收取的授权费或专利费

**识别方式：**

- 采用**离线语音识别**技术
- 本地处理，无需网络连接
- 支持命令词识别，不支持连续语音识别
- 识别响应速度快，隐私安全性高

---

## 模组概述

SU-03T 是一款低成本、低功耗、小体积的离线语音识别模组，能快速应用于智能家居、智能小家电、86盒、玩具、灯具等需要语音操控的产品。

### 产品外观

![SU-03T模组](http://help.aimachip.com/uploads/offline_su03t/images/m_2d304486dfc378816d5a4af73d544004_r.png "SU-03T模组")

### 外观尺寸

![尺寸图1](http://help.aimachip.com/uploads/offline_su03t/images/m_080f3c3df80084ad5d4e88fab588338d_r.png "外观尺寸")
![尺寸图2](http://help.aimachip.com/uploads/offline_su03t/images/m_07c91fa8f490336921af7558392cc15d_r.png "PCB尺寸")

### 核心特性

| 指标分类 | 参数项 | 规格/数值 |
|---------|-------|----------|
| **核心性能** | CPU | 32bit RISC 内核 @ 240MHz |
| | 运算单元 | DSP 指令集 + FPU 浮点运算单元 |
| | 加速器 | FFT 加速器 (最大1024点复数/2048点实数) |
| **存储资源** | SRAM | 高速 SRAM |
| | Flash | 2MB |
| **音频接口** | 麦克风 | 支持 1 路驻极体麦 |
| | 功放 | 内置 2.4W 单声道 AB 类功放 |
| | 接口 | I2S input/output |
| **电源** | 供电范围 | 5V 电源输入 (内置5V->3.3V LDO) |
| | 对外供电 | 3.3V (负载≤150mA) |
| | 时钟 | RC 12MHz + PLL 锁相环 |
| **外设接口** | UART | 1路全双工 (3Mbps) |
| | I2C | 1路 (400kHz) |
| | SPI | 1路Master + 1路Slave (30MHz) |
| | PWM | 2路 |
| | ADC | 1路 12-bit SAR-ADC (450Khz) |
| | GPIO | 所有 GPIO 可配置中断/唤醒 |
| **保护功能** | 监控 | POR、低电压检测、看门狗 |

---

## 官方资料下载

### 基本资料

| 资料 | 链接 |
|------|------|
| 原理图 | [下载](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1e9c64320m7b4) |
| 规格书 | [下载](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1e9c64cmn4l8s) |
| 封装图 | [下载](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1e9c64lmb1k0h) |
| 开发板资料 | [下载](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1ecu2m15522vj) |

### 烧录资料

| 资料 | 链接 |
|------|------|
| CH340驱动 | [下载](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1e9ef257a487g) |
| 烧录软件 | [下载](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1e9ef2d3j713u) |
| 烧录文档 | [下载](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1e9ef2n43b4k1) |
| 出厂固件 | [下载](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1e9ef31r383u8) |
| 串口调试 | [下载](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1e9ef3brv57no) |

### 开发包

| 资料 | 链接 |
|------|------|
| SU-03T开发包(老版本) | [下载](https://help.aimachip.com/docs/offline_su03t/su_03t_kfb) |
| SU-03T开发包 版本240816 | [下载](https://help.aimachip.com/attach_files/offline_su03t/722) |
| Linux二次开发环境搭建（无虚拟机） | [下载](https://help.aimachip.com/attach_files/offline_su03t/618) |
| Linux二次开发环境搭建（附带虚拟机） | [下载](https://help.aimachip.com/attach_files/offline_su03t/617) |

### 产品设计

| 资料 | 链接 |
|------|------|
| 产品结构声学设计 | [下载](https://help.aimachip.com/docs/offline_su03t/su_03t_999) |
| 喇叭和咪头选型 | [下载](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1ecu2n8d8f503) |

### 视频教程

| 类型 | 链接 |
|------|------|
| 机芯智能B站官方教程 | [查看](https://space.bilibili.com/1399467255) |
| 串口教程视频 | [查看](https://www.bilibili.com/video/BV1nv4y197uR/) |
| 入门例程演示 | [查看](https://www.smartpi.cn/#/example) |

---


### 主要参数表
![主要参数1](http://help.aimachip.com/uploads/offline_su03t/images/m_bc91ca3d234ca73bcff61582728eaa9e_r.png "主要参数表")
![主要参数2](http://help.aimachip.com/uploads/offline_su03t/images/m_89ac46589c055c7c342c56c813b00ae8_r.png "详细参数")

### 管脚定义

SU-03T 模组共接出 **18 个接口**：

> **重要烧录引脚说明**：
> - **B0/B1**：UART0 调试器烧录口
> - **B6/B7**：UART1 串口烧录口（串口烧录使用）
> - **B2/B3**：升级狗烧录/脱机烧录（建议生产使用）
> - 具体烧录方式请查看烧录文档

![管脚图](http://help.aimachip.com/uploads/offline_su03t/images/m_670ba5e42da2a974fef896c3160873f5_r.png "管脚定义")
![管脚说明1](http://help.aimachip.com/uploads/offline_su03t/images/m_42843b026736450eca247fe406953714_r.png "管脚说明表1")
![管脚说明2](http://help.aimachip.com/uploads/offline_su03t/images/m_824e771cdf61b5a3ee4b6b851f5fd50e_r.png "管脚说明表2")
## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 常见问题

已将本页的大段指南与常见问题整理到独立文档：

- [SU-03T 平台与固件 FAQ](../faq-platform-and-firmware/faq-platform-and-firmware-su-03t.md)
- [SU-03T 烧录与调试 FAQ](../faq-burning-and-debug/faq-burning-and-debug-su-03t.md)
- [SU-03T 硬件设计 FAQ](../faq-hardware-design/faq-hardware-design-su-03t.md)
- [SU-03T 语音调优 FAQ](../faq-voice-tuning/faq-voice-tuning-su-03t.md)
- [SU-03T 模块选型 FAQ](../faq-module-selection/faq-module-selection-su-03t.md)
- [SU-03T 应用场景与项目 FAQ](../faq-application-scenarios/faq-application-scenarios-su-03t.md)

---

## 参考链接

| 资源 | 链接 |
|------|------|
| SU-03T 官方文档首页 | [https://help.aimachip.com/docs/offline_su03t](https://help.aimachip.com/docs/offline_su03t) |
| 智能公元平台 | [https://smartpi.cn](https://smartpi.cn) |
| 芯片资料 | [查看](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1e9c648nb2nec) |
