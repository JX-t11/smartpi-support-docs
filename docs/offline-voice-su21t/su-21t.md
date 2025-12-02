---
title: 离线语音模组 SU-21T
icon: material/microphone
description: 低成本超低功耗离线语音模组 SU-21T 完整开发指南，小体积，适合穿戴设备。
---

# 离线语音模组 SU-21T

## 快速规格一览

| 参数 | SU-21T |
|------|--------|
| 主控芯片 | 32bit RISC @50MHz |
| 架构 | **低功耗语音专用 NPU** |
| 词条数 | **50**（推荐） |
| 供电电压 | **3.3V**（严禁5V） |
| 接口电平 | 3.3V |
| 功放 | ✗（无功放，需外接） |
| Flash | 1MB |
| 功耗 | **亚毫瓦级**（待机） |
| 封装 | **小体积** |

### SU-21T 定位

> SU-21T 是 **超低功耗小体积模组**：
> - **特点**：待机功耗极低，体积小
> - **对比 SU-20T**：Flash 较小（1M vs 2.5M），无内置功放
> - **适用场景**：手持设备、穿戴设备、对体积功耗要求苛刻的产品

---

## 定位与适用场景

- **定位**：超低功耗、低成本、小体积的离线语音识别模组
- **适用场景**：

    - **穿戴设备**：智能手表、TWS耳机充电仓
    - **便携设备**：手持风扇、录音笔
    - **智能家居**：温湿度计、遥控器
- **优势**：极致低功耗、小体积
- **注意**：**供电电压必须为 3.3V**，无内置功放

---

## 模组概述

SU-21T 是一款低成本、小体积、超低功耗的离线语音识别模组。内置高精度语音检测模块配合系统多级启动模式使芯片待机功耗进入亚毫瓦级，工作功耗几毫瓦级别。

### 产品外观

![功能框图](http://help.aimachip.com/uploads/offline_su21t/images/m_88710a5e5a3bca1a66bf82f74c2ea0a5_r.png "SU-21T功能框图")

### 外观尺寸

![尺寸图1](http://help.aimachip.com/uploads/offline_su21t/images/m_5195a7328551a15524a0e64f84ad18a0_r.png "外观尺寸")
![尺寸图2](http://help.aimachip.com/uploads/offline_su21t/images/m_7a869db6a28e57399885b6f241fa5d46_r.png "侧面尺寸")

### 核心特性

| 指标分类 | 参数项 | 规格/数值 |
|---------|-------|----------|
| **核心性能** | CPU | 32bit 超低功耗 RISC 内核 @ 50MHz |
| | 运算单元 | DSP 指令集 + FPU 浮点运算单元 |
| | NPU | 低功耗语音专用神经网络处理单元 |
| **存储资源** | SRAM | 208KB |
| | Flash | 1MB |
| **音频接口** | 麦克风 | 支持 1 路驻极体麦 |
| | 功放 | **无内置功放** (需外接) |
| **电源** | 供电范围 | **3.3V** (严禁5V) |
| | 功耗 | 待机亚毫瓦级 |
| **外设接口** | UART | 3.3V 电平 |

### 官方资料下载

| 资料 | 链接 |
|------|------|
| 官方文档首页 | [查看](https://help.aimachip.com/docs/offline_su21t) |
| 开发包 V2.1.0 | [下载](https://help.aimachip.com/attach_files/offline_su21t/897) |
| 开发包(旧版本) | [下载](https://help.aimachip.com/attach_files/offline_su21t/580) |
| 烧录软件 | [下载](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1gb2hlcok72aj) |
| 规格书 | [下载](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1gb2j7ik4lpf4) |
| 原理图 | [下载](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1gb2j3itkpacg) |
| 产品结构声学规范 | [下载](https://help.aimachip.com/attach_files/offline_su21t/890) |
| 喇叭和咪头选型 | [下载](https://help.aimachip.com/attach_files/offline_su21t/891) |

---


## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具

### 开发工具下载

| 工具 | 说明 | 下载链接 |
|------|------|---------|
| 开发包 V2.1.0 | SDK、示例代码、配置工具 | [下载](https://help.aimachip.com/attach_files/offline_su21t/897) |
| CH340 驱动 | USB转串口驱动 | [下载](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1gb2hkm8qnnh6) |
| 烧录软件 | 固件烧录工具 | [下载](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1gb2hlcok72aj) |
| 串口调试工具 | 日志查看与命令调试 | [下载](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1gb2hmb13rqgg) |

### 芯片资料

> **蜂鸟L系列 (US513U6/US513U61)** 是一颗亚毫瓦级超低功耗智能纯离线语音识别芯片，面向带电池和便携式产品以及对功耗有严苛要求的各类产品。
> - 采用 MCU + 语音识别专用 NPU 架构内核
> - 采用超低功耗制程工艺
> - 内置高精度语音检测模块 + 多级启动模式
> - 待机功耗亚毫瓦级，工作功耗几毫瓦级
> - 支持 50 条本地指令离线 3-5 米远场识别
> - 支持 RTOS 轻量级系统

| 资料 | 链接 |
|------|------|
| 蜂鸟L 芯片详情 | [查看](http://help.aimachip.com/docs/chip/chip-1e9c8p36onh9g) |
| 蜂鸟L SOC产品手册 | [下载](https://help.aimachip.com/attach_files/chip/427) |
| 蜂鸟L 离线方案开发指导手册 | [下载](https://help.aimachip.com/attach_files/chip/429) |
| 蜂鸟L 参考原理图 | [下载](https://help.aimachip.com/attach_files/chip/428) |

### 产品设计参考

| 资料 | 链接 |
|------|------|
| 产品结构声学规范 | [下载](https://help.aimachip.com/attach_files/offline_su21t/890) |
| 喇叭和咪头选型推荐 | [下载](https://help.aimachip.com/attach_files/offline_su21t/891) |

---

## 固件烧录与升级指南

1. 安装 CH340 驱动。
2. 通过 USB/UART 将固件写入 Flash。
3. 使用配置工具导入词表、编译后烧录。
4. 复位设备并播放测试词表确认成功。

> 教程参考：
> - [SU-21T转接板烧录](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1eri6t7rma7lv)
> - [转接板固件烧录资料](https://help.aimachip.com/attach_files/offline_su21t/572)

## 指令集 / 词表配置

- 支持多场景词表，结构为"唤醒词 → 命令组 → 动作"。
- 串口协议：0xAA 0x55 CMD LEN DATA CS（详见旧文档）。

> 教程参考：
> - [SU-21T输入输出教学](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1eri8ibv89ls3) - [资料下载](https://help.aimachip.com/attach_files/offline_su21t/576)
> - [SU-21T串口输入输出教程](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1ermqgsh80p58) - [资料下载](https://help.aimachip.com/attach_files/offline_su21t/577)
>
> **教程功能说明**：
> - IO输入输出：语音控制灯光亮灭、调暗调亮、呼吸灯制作、按键控制
> - 串口教程：语音控制串口发送16进制数，串口输入触发语音模块输出

---

## 参考链接

| 资源 | 链接 |
|------|------|
| SU-21T 官方文档首页 | [https://help.aimachip.com/docs/offline_su21t](https://help.aimachip.com/docs/offline_su21t) |
| 蜂鸟L 芯片资料 | [https://help.aimachip.com/docs/chip/chip-1e9c8p36onh9g](http://help.aimachip.com/docs/chip/chip-1e9c8p36onh9g) |
| 智能公元平台 | [https://smartpi.cn](https://smartpi.cn) |
| SU-20T 文档（参考） | [https://help.aimachip.com/docs/offline_su20t](https://help.aimachip.com/docs/offline_su20t) |
