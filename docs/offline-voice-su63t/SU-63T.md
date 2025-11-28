---
title: 离线语音模组 SU-63T
icon: material/microphone
description: 蓝牙双模智能语音 IoT 模组 SU-63T 完整开发指南，支持 BLE 5.1，50条本地指令。
---

# 离线语音模组 SU-63T

## 快速规格一览

| 参数 | SU-63T |
|------|--------|
| 主控芯片 | 32位 CPU @240MHz |
| 架构 | **MCU + 语音识别专用 NPU** |
| 蓝牙版本 | **V5.1+BR+EDR+BLE** |
| 词条数 | **50**（本地指令） |
| 供电电压 | **2.5V - 5.5V** |
| Flash | 1MB |
| 识别距离 | 3-5米远场 |
| 封装 | **SMD18** |

### SU-63T 定位

> SU-63T 是 **蓝牙双模智能语音 IoT 模组**：
> - **特点**：蓝牙双模 + 离线语音识别，Turnkey 方案
> - **蓝牙**：支持 BLE 5.1、A2DP、HFP、SPP 等协议
> - **适用场景**：智能家电、智能家居、智能玩具、无线音视频、工业控制、医疗监护

---

## 定位与适用场景

- **定位**：蓝牙双模智能语音 IoT 模组
- **适用场景**：
  - **智能家电**：空调、电视、洗衣机语音控制
  - **智能家居**：智能开关、智能插座、智能灯具
  - **智能玩具**：语音交互玩具、教育机器人
  - **无线音视频**：蓝牙音箱、耳机、麦克风
  - **工业/医疗**：语音控制设备
- **优势**：蓝牙双模、本地识别、低功耗、丰富接口
- **注意**：**供电电压 2.5V - 5.5V**

---

## 模组概述

SU-63T 是一款蓝牙双模智能语音 IoT 模组。芯片集成 32 位 CPU 处理器，包含 UART、GPIO、SPI、I2C、ADC、功放等外围接口；内置 NPU、浮点运算单元。依托在语音识别技术上的积累和算法的不断优化和创新，将本地识别算法与芯片架构深度融合，为客户提供 Turnkey 语音识别方案。

该模组采用 MCU 加语音识别专用 NPU 架构内核，同时芯片内置 SRAM 和 FLASH，只需少量外围器件即可形成完整解决方案。该方案支持 50 条本地指令离线 3-5 米远场识别，支持 RTOS 轻量级系统，并提供简洁友好的客制化工具，可快速部署到不同的终端产品上。

### 功能框图
![内核架构图](http://help.aimachip.com/uploads/offline_su63t/images/m_3df322837e715788d2c81099678a7128_r.png)

## 外观尺寸

- ![](http://help.aimachip.com/uploads/offline_su63t/images/m_0c8cb6526a24dd62579120f38fd8dc49_r.png)
- ![](http://help.aimachip.com/uploads/offline_su63t/images/m_f7fc5cd5bec0fd682515209116eb1a94_r.png)

### 官方资料下载

| 资料 | 链接 |
|------|------|
| 官方文档首页 | [查看](https://help.aimachip.com/docs/offline_su63t) |
| 规格书 V1.0 | [下载](https://help.aimachip.com/attach_files/offline_su63t/937) |
| 原理图 V1.1 | [下载](https://help.aimachip.com/attach_files/offline_su63t/936) |
| 封装图 V1.1 | [下载](https://help.aimachip.com/attach_files/offline_su63t/938) |
| CH340 驱动 | [下载](https://help.aimachip.com/attach_files/offline_su63t/939) |
| 烧录软件 | [下载](https://help.aimachip.com/attach_files/offline_su63t/940) |
| 烧录文档 | [下载](https://help.aimachip.com/attach_files/offline_su63t/941) |
| 出厂固件 | [下载](https://help.aimachip.com/attach_files/offline_su63t/942) |
| 串口调试软件 | [下载](https://help.aimachip.com/attach_files/offline_su63t/943) |
| 产品结构声学规范 | [下载](https://help.aimachip.com/attach_files/offline_su63t/934) |
| 喇叭和咪头选型 | [下载](https://help.aimachip.com/attach_files/offline_su63t/935) |
| 蜂鸟B(US665) SOC产品手册 | [下载](https://help.aimachip.com/attach_files/offline_su63t/933) |

---

## 核心特性

### 处理器特性
- 集成 32 位处理器，工作频率 240MHz，内置 NPU、浮点运算单元
- 内置 1MB Flash
- 4 级中断优先级

### 接口特性
- 集成 3 路全双工 UART, UART0 和 UART1 支持 DMA 模式
- 集成 1 个 10 比特 ADC
- 集成 1 个高速 SPI 接口，支持主从模式
- 集成 1 个 SD 卡主模式控制器
- 集成 1 个 I2C 控制器，支持主从模式
- 集成 GPIO 控制器，最多支持 9 个 GPIO
- 集成 1 路全速 USB2.0 OTG 控制器
- 集成 4 路多功能 16 位定时器，支持 capture 和 PWM 模式
- 集成 2 路用于马达控制的 PWM
- 集成 Touch Sensor 控制器

### 音频特性
- 两路 16 位 DAC，SNR>=95dB
- 一路 16 位 ADC，SNR≥90dB
- 采样率：8/11.025/16/22.05/24/32/44.1/48KHz
- 1 路模拟 MIC 输入，内置 MIC 偏置电压输出

### 蓝牙特性
- 支持 V5.1+BR+EDR+BLE
- 支持 Class1、2、3 发送功率
- 支持 GFSK、π/4 DQPSK 包型
- 支持 6dBm 发射功率
- 接收灵敏度-90dBm
- 快速 AGC 支持增强型动态范围
- 支持 a2dp/avctp/avdtp/avrcp/hfp/spp/smp/att/gap/gatt/rfcomm/sdp/l2cap

### 电源特性
- 单电源供电，VBAT 2.5V 到 5.5V
- 内置 LDO 用于芯片数字和模拟部分供电

### 开发支持
- 提供完整基于 RTOS 的 SDK
- 支持快速便捷的 UART 等控制协议开发

### 封装
- 封装: SMD18

## 性能参数

| 指标 | 内容 |
| --- | --- |
| 处理器 | 32位 CPU + NPU |
| 工作频率 | 240MHz |
| 存储器 | 内置 1MB Flash + SRAM |
| 蓝牙版本 | V5.1+BR+EDR+BLE |
| 识别距离 | 3-5米远场识别 |
| 指令容量 | 50条本地指令 |
| 系统支持 | RTOS 轻量级系统 |
| 音频采样率 | 8-48KHz 多种采样率 |
| 供电范围 | 2.5V - 5.5V |
| 封装形式 | SMD18 |

## 应用场景

- **智能家电**: 空调、电视、洗衣机等语音控制
- **智能家居**: 智能开关、智能插座、智能灯具
- **智能玩具**: 语音交互玩具、教育机器人
- **无线音视频**: 蓝牙音箱、耳机、麦克风
- **工业控制**: 语音控制的工业设备
- **医疗监护**: 语音控制的医疗设备

## 开发环境与工具

### 开发工具下载

| 工具 | 说明 | 下载链接 |
|------|------|---------|
| CH340 驱动 | USB转串口驱动 | [下载](https://help.aimachip.com/attach_files/offline_su63t/939) |
| 烧录软件 | 固件烧录工具 | [下载](https://help.aimachip.com/attach_files/offline_su63t/940) |
| 烧录文档 | 烧录操作说明 | [下载](https://help.aimachip.com/attach_files/offline_su63t/941) |
| 出厂固件 | 出厂默认固件 | [下载](https://help.aimachip.com/attach_files/offline_su63t/942) |
| 串口调试软件 | 日志查看与命令调试 | [下载](https://help.aimachip.com/attach_files/offline_su63t/943) |

### 芯片资料

> **蜂鸟B系列 (US665)** 是蓝牙双模智能语音 IoT 芯片，支持 BLE 5.1+BR+EDR。
> - 集成 32 位 CPU @240MHz + NPU
> - 内置 1MB Flash + SRAM
> - 支持蓝牙双模 V5.1+BR+EDR+BLE
> - 支持 50 条本地指令离线 3-5 米远场识别
> - 支持 RTOS 轻量级系统

| 资料 | 链接 |
|------|------|
| 蜂鸟B 芯片详情 | [查看](http://help.aimachip.com/docs/chip/chip-1e9btp9avcecd) |
| 蜂鸟B(US665) SOC产品手册 | [下载](https://help.aimachip.com/attach_files/offline_su63t/933) |

### 产品设计参考

| 资料 | 链接 |
|------|------|
| 产品结构声学规范 | [下载](https://help.aimachip.com/attach_files/offline_su63t/934) |
| 喇叭和咪头选型推荐 | [下载](https://help.aimachip.com/attach_files/offline_su63t/935) |

---

## 相关教程配套固件

### IO 输入输出
- [IO 输入输出配套固件](https://help.aimachip.com/docs/offline_su63t/su_63t_io)

### 串口教程
- [串口教程配套固件](https://help.aimachip.com/docs/offline_su63t/SU-63T_usart)

### ADC 教程
- [ADC 教程配套固件](https://help.aimachip.com/docs/offline_su63t/su_63t_adc)

### 蓝牙播放音乐
- [蓝牙播放音乐配套固件](https://help.aimachip.com/docs/offline_su63t/SU-63T_bt)

### ADC + 蓝牙播放音乐
- [ADC+蓝牙播放音乐配套固件](https://help.aimachip.com/docs/offline_su63t/su_63t_adc_bt)

### 微信小程序
- [微信小程序配套固件](https://help.aimachip.com/docs/offline_su63t/su_63t_wxxcx)

### 不用唤醒词直接触发
- ![操作图解](http://help.aimachip.com/uploads/offline_su63t/images/m_626bf57fa8689b72f80b18121c431593_r.png)
- [不用唤醒词直接触发，永不退下固件](https://help.aimachip.com/docs/offline_su63t/su_63t_YBTX)

## 开发支持

提供完整的 SDK 和开发工具：
- 基于 RTOS 的软件开发套件
- 语音识别客制化工具
- 详细的开发文档和示例代码
- 技术支持和应用指导

---

## 参考链接

| 资源 | 链接 |
|------|------|
| SU-63T 官方文档首页 | [https://help.aimachip.com/docs/offline_su63t](https://help.aimachip.com/docs/offline_su63t) |
| 蜂鸟B 芯片资料 | [http://help.aimachip.com/docs/chip/chip-1e9btp9avcecd](http://help.aimachip.com/docs/chip/chip-1e9btp9avcecd) |
| 智能公元平台 | [https://smartpi.cn](https://smartpi.cn) |
