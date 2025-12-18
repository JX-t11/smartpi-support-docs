---
title: 离线语音模组 SU-20T
icon: material/microphone
description: 超低功耗离线语音模组 SU-20T 完整开发指南，待机亚毫瓦级，适合电池供电产品。
---

# 离线语音模组 SU-20T

## 快速规格一览

| 参数 | SU-20T |
|------|--------|
| 主控芯片 | 32bit RISC @50MHz |
| 架构 | **低功耗语音专用 NPU** |
| 词条数 | **50**（推荐） |
| 供电电压 | **3.3V**（注意不是5V） |
| 接口电平 | 3.3V |
| 功放 | **3W**（内置AB类） |
| Flash | 512KB内置 + 2MB外置 |
| 功耗 | **亚毫瓦级**（待机） |
| 封装 | **SMD** |

### SU-20T 定位

> SU-20T 是 **超低功耗模组**：

> - **特点**：待机功耗极低（亚毫瓦级），适合电池供电
> - **电压**：**仅支持 3.3V 供电**，严禁接 5V
> - **NPU**：内置神经网络处理单元，低功耗下实现语音检测
> - **适用场景**：手持设备、遥控器、穿戴设备

---

## 定位与适用场景

- **定位**：超低功耗、低成本、小体积的离线语音识别模组
- **适用场景**：

    - **电池供电产品**：遥控器、便携风扇、手持按摩仪
    - **穿戴设备**：智能手表、挂脖风扇
    - **智能家居**：温湿度计、无线开关
- **优势**：极致低功耗、内置NPU
- **注意**：**供电电压必须为 3.3V**，否则会烧毁模组

---

## 模组概述

SU-20T 是一款低成本、低功耗、小体积的离线语音识别模组，专为超低功耗应用设计。内置高精度语音检测模块，配合系统多级启动模式使芯片待机功耗进入亚毫瓦级，工作功耗几毫瓦级别。

### 产品外观

![SU-20T模组](http://help.aimachip.com/uploads/offline_su20t/images/m_1ee74c3ca4b6c0ce42a4d1cd55990b6f_r.png "SU-20T功能框图")

### 核心特性

| 指标分类 | 参数项 | 规格/数值 |
|---------|-------|----------|
| **核心性能** | CPU | 32bit 低功耗 RISC 内核 @ 50MHz |
| | 运算单元 | DSP 指令集 + FPU 浮点运算单元 |
| | NPU | 低功耗语音专用神经网络处理单元 |
| **存储资源** | SRAM | 208KB |
| | Flash | 512KB (内置) + 2MB (外置) |
| **音频接口** | 麦克风 | 支持 1 路驻极体麦 |
| | 功放 | 内置 **3W** 单声道 AB 类功放 |
| | 喇叭 | 支持 1 路喇叭输出 |
| **电源** | 供电范围 | **3.3V** (严禁5V) |
| | 功耗 | 待机亚毫瓦级 |
| **外设接口** | UART | 3.3V 电平 |

### 官方资料下载

| 资料 | 链接 |
|------|------|
| 官方文档首页 | [查看](https://help.aimachip.com/docs/offline_su20t) |
| 开发包 V2.1.0 | [下载](https://help.aimachip.com/attach_files/offline_su20t/1164) |
| 芯片资料 | [查看](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1e9eet9mm20ut) |
| 烧录文档 | [下载](https://help.aimachip.com/attach_files/offline_su20t/871) |
| 规格书 V1.1 | [下载](https://help.aimachip.com/attach_files/offline_su20t/868) |
| 原理图 V1.0 | [下载](https://help.aimachip.com/attach_files/offline_su20t/867) |
| CH340 驱动 | [下载](https://help.aimachip.com/attach_files/offline_su20t/869) |
| 串口调试软件 | [下载](https://help.aimachip.com/attach_files/offline_su20t/873) |
| 产品结构声学规范 | [下载](https://help.aimachip.com/attach_files/offline_su20t/876) |
| 喇叭和咪头选型 | [下载](https://help.aimachip.com/attach_files/offline_su20t/877) |

---


## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具

### 开发工具下载

| 工具 | 说明 | 下载链接 |
|------|------|---------|
| 开发包 V2.1.0 | SDK、示例代码、配置工具 | [下载](https://help.aimachip.com/attach_files/offline_su20t/1164) |
| CH340 驱动 | USB转串口驱动 | [下载](https://help.aimachip.com/attach_files/offline_su20t/869) |
| 烧录软件 | 固件烧录工具 | [下载](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1gb2gkumkrc6d) |
| 串口调试工具 | 日志查看与命令调试 | [下载](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1gb2glkff1ti5) |

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
| 蜂鸟L SOC产品手册 | [下载](https://help.aimachip.com/attach_files/offline_su20t/874) |
| 蜂鸟L 离线方案开发指导手册 | [下载](https://help.aimachip.com/attach_files/offline_su20t/875) |
| 蜂鸟L 参考原理图 | [下载](https://help.aimachip.com/attach_files/chip/428) |

### 产品设计参考

| 资料 | 链接 |
|------|------|
| 产品结构声学规范 | [下载](https://help.aimachip.com/attach_files/offline_su20t/876) |
| 喇叭和咪头选型推荐 | [下载](https://help.aimachip.com/attach_files/offline_su20t/877) |

---

## 固件烧录与升级指南

1. 下载并安装 [CH340 驱动](https://help.aimachip.com/attach_files/offline_su20t/869)。
2. 参考[烧录文档](https://help.aimachip.com/attach_files/offline_su20t/871)安装烧录工具。
3. 通过 USB/UART 将固件写入 Flash。
4. 使用配置工具导入词表、编译后烧录。
5. 复位设备并播放测试词表确认成功。

> 参考资料：
> - [出厂固件](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1gb2glbqjuf37)
> - [芯片资料](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1e9eet9mm20ut)
> - [蜂鸟L 离线方案开发指导手册](https://help.aimachip.com/attach_files/offline_su20t/875)

## 指令集 / 词表配置

- 支持多场景词表，结构为"唤醒词 → 命令组 → 动作"。
- 串口协议：0xAA 0x55 CMD LEN DATA CS
- 通过开发包中的配置工具可视化编辑词表。

---

## 参考链接

| 资源 | 链接 |
|------|------|
| SU-20T 官方文档首页 | [https://help.aimachip.com/docs/offline_su20t](https://help.aimachip.com/docs/offline_su20t) |
| 蜂鸟L 芯片资料 | [https://help.aimachip.com/docs/chip/chip-1e9c8p36onh9g](http://help.aimachip.com/docs/chip/chip-1e9c8p36onh9g) |
| 智能公元平台 | [https://smartpi.cn](https://smartpi.cn) |
| SU-21T 文档（参考） | [https://help.aimachip.com/docs/offline_su21t](https://help.aimachip.com/docs/offline_su21t) |
