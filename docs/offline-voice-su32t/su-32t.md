---
title: 离线语音模组 SU-32T
icon: material/microphone
description: 高性能双麦抗噪离线语音模组 SU-32T 完整开发指南，DSP+NPU+CPU 异步架构，支持150条本地指令。
---

# 离线语音模组 SU-32T

## 快速规格一览

| 参数 | SU-32T |
|------|--------|
| 主控芯片 | ARM CPU @270MHz |
| 架构 | **DSP + NPU + CPU 异步架构** |
| 词条数 | **150**（本地指令） |
| 供电电压 | **3.3V** |
| 麦克风 | **双麦**（高性能抗噪） |
| SRAM | 1.5MB |
| Flash | 8MB |
| 识别距离 | 远场识别 |
| 封装 | **40 Pin 邮票孔** |

### SU-32T 定位

> SU-32T 是 **高性能双麦抗噪离线语音模组**：
> - **架构**：DSP+NPU+CPU 异步架构，DSP性能是HiFi4的两倍
> - **特点**：高性能双麦抗噪、更好的降噪、增强、BF等功能
> - **适用场景**：智能家居、智能小家电、86盒、玩具、灯具、工业、医疗、物联网、汽车、安防

---

## 定位与适用场景

- **定位**：高性能双麦抗噪离线语音识别模块
- **适用场景**：

    - **智能家居**：智能门锁、智能窗帘、86盒
    - **智能家电**：风扇、空调、智能茶壶、扫地机
    - **照明产品**：智能台灯、灯具
    - **其他**：玩具、故事机、车载音控
- **优势**：双麦抗噪、低延时、本地数据安全
- **注意**：**供电电压 3.3V**

---

## 模组概述

SU-32T 离线双麦语音核心模块是针对大量纯离线控制场景和产品推出的一款高性能双麦抗噪离线语音识别模块。模块主芯片采用 DSP+NPU+CPU 异步架构，前端信号处理 DSP，性能是 HiFi4 的两倍，提供更好的降噪、增强、BF 等功能，高效神经网络处理器提供更快速和准确语音识别。

支持 150 条本地指令离线识别，支持 RTOS 轻量级系统，并具有丰富的外围接口。包括 UART、I2C、SPI、PWM、ADC 等。

### 核心特性

| 指标 | 内容 |
|------|------|
| 架构 | DSP + NPU + CPU 异步架构 |
| CPU | ARM CPU @270MHz |
| 数据带宽 | 双 128bit 数据读写带宽 |
| 运算能力 | 8MACs/周期单精度浮点，16MACs/周期半精度浮点 |
| NN运算 | 32MACs/周期语音 NN 运算能力 |
| 权重支持 | 支持 8/4/2/1 低精度权重 |
| 存储器 | 1.5MB SRAM + 8MB Flash |
| UART | 最多支持 3 路 |
| PWM | 最高 5 路 |
| GPIO | 最高支持 29 个 |
| I2C | 1 路 |
| SPI | 1 路 |
| ADC | 1 路 10bit SAR ADC |
| IR | 支持 IR 输入/输出 |
| 词表容量 | 150条本地指令 |
| 系统支持 | RTOS 轻量级系统 |
| 封装 | 40 Pin 邮票孔 |

### 官方资料下载

| 资料 | 链接 |
|------|------|
| 官方文档首页 | [查看](https://help.aimachip.com/docs/offline_su32t) |
| 规格书 V1.0 | [下载](https://help.aimachip.com/attach_files/offline_su32t/950) |
| 封装图 V1.1 | [下载](https://help.aimachip.com/attach_files/offline_su32t/951) |
| CH340 驱动 | [下载](https://help.aimachip.com/attach_files/offline_su32t/952) |
| 烧录软件 | [下载](https://help.aimachip.com/attach_files/offline_su32t/953) |
| 喇叭和咪头选型 | [下载](https://help.aimachip.com/attach_files/offline_su32t/958) |

### 开发板资料

| 资料 | 链接 |
|------|------|
| 开发板规格书 | [下载](https://help.aimachip.com/attach_files/offline_su32t/949) |
| 开发板原理图 | [下载](https://help.aimachip.com/attach_files/offline_su32t/948) |

---

## 硬件设计指南

1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具

### 开发工具下载

| 工具 | 说明 | 下载链接 |
|------|------|---------|
| CH340 驱动 | USB转串口驱动 | [下载](https://help.aimachip.com/attach_files/offline_su32t/952) |
| 烧录软件 | 固件烧录工具 | [下载](https://help.aimachip.com/attach_files/offline_su32t/953) |
| 喇叭和咪头选型 | 音频器件选型参考 | [下载](https://help.aimachip.com/attach_files/offline_su32t/958) |

### 芯片资料

> **蜂鸟系列 (US52X)** 是专门为离在线远场语音交互场景设计的高性能、高集成度、低成本智能语音芯片。
> - 采用 DSP+NPU+CPU 异步架构
> - 前端信号处理 DSP 性能是 HiFi4 的两倍
> - 提供更好的降噪、增强、BF 等功能
> - 高效神经网络处理器提供更快速和准确语音识别
> - 支持 150 条本地指令离线识别
> - 支持 RTOS 轻量级系统

| 资料 | 链接 |
|------|------|
| 蜂鸟芯片详情 | [查看](http://help.aimachip.com/docs/chip/chip-1e9c8qlkoou22) |
| 蜂鸟(US52X) SOC产品手册 | [下载](https://help.aimachip.com/attach_files/chip/50) |
| 蜂鸟离线方案开发指导手册 | [下载](https://help.aimachip.com/attach_files/chip/52) |
| 蜂鸟离线模组参考原理图 | [下载](https://help.aimachip.com/attach_files/chip/51) |

---

## 固件烧录与升级指南

1. 下载并安装 [CH340 驱动](https://help.aimachip.com/attach_files/offline_su32t/952)。
2. 下载 [烧录软件](https://help.aimachip.com/attach_files/offline_su32t/953)。
3. 通过 USB/UART 将固件写入 Flash。
4. 使用配置工具导入词表、编译后烧录。
5. 复位设备并播放测试词表确认成功。

## 指令集 / 词表配置

- 支持多场景词表，结构为"唤醒词 → 命令组 → 动作"。
- 串口协议：0xAA 0x55 CMD LEN DATA CS
- 支持 150 条本地指令离线远场识别

## 外设开发与应用示例

- 继电器：识别指令后驱动 GPIO 切换。
- 串口反馈：将识别到的词 ID 发给主控。
- 联动应用：与 WiFi 模组结合，实现语音+云端控制。
- IR控制：支持 IR 输入/输出控制红外设备。

---

### 无多余IO口时如何与单片机通信？

**问题描述：**

使用 SU-32T 作为主控芯片时，已占用 UART1 和 UART3 分别连接屏幕和护理床，没有多余的串口和 IO 口与单片机通信。

**解决方案：**

- **高低电平应答方案**：在没有多余 IO 口的情况下，可使用高低电平信号作为简单的应答机制
- **串口共用方案**：通过制定不同的指令内容作为区分，尝试共用串口（需注意可能会造成信息紊乱）

**注意事项：**

- 串口共用已被研发验证不可行，会导致信息紊乱，不建议使用
- SU-32T 最多支持 3 路 UART，规划通信时需合理分配资源
- 对于简单的控制需求，高低电平应答是可行的替代方案

---

## 参考链接

| 资源 | 链接 |
|------|------|
| SU-32T 官方文档首页 | [https://help.aimachip.com/docs/offline_su32t](https://help.aimachip.com/docs/offline_su32t) |
| 蜂鸟芯片资料 | [http://help.aimachip.com/docs/chip/chip-1e9c8qlkoou22](http://help.aimachip.com/docs/chip/chip-1e9c8qlkoou22) |
| 智能公元平台 | [https://smartpi.cn](https://smartpi.cn) |
| SU-30T/31T 文档（参考） | [https://help.aimachip.com/docs/offline_su30t](https://help.aimachip.com/docs/offline_su30t) |
