---
title: 芯片手册
icon: material/chip
description: 智能公元系列芯片数据手册与技术文档索引。
---

# 芯片手册

## 定位与适用场景

- **定位**：芯片数据手册与技术文档索引
- **目标**：提供各型号芯片的技术规格与资料下载
- **适用对象**：硬件工程师、嵌入式开发者

---

## 蜂鸟系列芯片

### 蜂鸟 B（US665P3）

蓝牙双模智能语音 IoT 芯片，集成 32 位 CPU 处理器，内置 NPU、浮点运算单元。

**主要特点：**

- 芯片架构：MCU + 语音识别专用 NPU
- 外围接口：UART、GPIO、SPI、SD 卡、I2C、ADC、TouchSensor
- 本地指令：50 条离线识别，3-5 米远场
- 系统支持：RTOS 轻量级系统
- 应用场景：智能家电、智能家居、智能玩具、无线音视频、工业控制、医疗监护

| 文档 | 下载链接 |
|------|---------|
| 蜂鸟B(US665) SOC产品手册 | [下载](https://help.aimachip.com/attach_files/chip/20) |
| 离线方案开发指导手册（通用版本） | [下载](https://help.aimachip.com/attach_files/chip/23) |
| 离线方案开发指导手册（BLE版本） | [下载](https://help.aimachip.com/attach_files/chip/22) |

---

### 蜂鸟 L 系列（US513U6 / US513U61）

亚毫瓦级超低功耗智能纯离线语音识别芯片，面向带电池和便携式产品。

**主要特点：**

- 芯片架构：MCU + 语音识别专用 NPU
- 功耗特性：待机亚毫瓦级，工作几毫瓦级
- 本地指令：50 条离线识别，3-5 米远场
- 应用场景：小家电、可穿戴、玩具、单火线供电 86 盒

| 文档 | 下载链接 |
|------|---------|
| 蜂鸟L-SOC产品手册 | [下载](https://help.aimachip.com/attach_files/chip/427) |
| 蜂鸟L参考原理图 | [下载](https://help.aimachip.com/attach_files/chip/428) |
| 蜂鸟L离线方案开发指导手册 | [下载](https://help.aimachip.com/attach_files/chip/429) |

---

### 蜂鸟 M（US516P6）

低成本纯离线语音识别芯片。

**主要特点：**

- 芯片架构：32bit RISC + DSP 指令集 + FPU + FFT 加速器
- 本地指令：100 条离线识别
- 系统支持：RTOS 轻量级系统
- 应用场景：智能家居、小家电、86 盒、玩具、灯具
- ⚠️ 注意：空芯片需先用调试烧录器烧录基础固件后才支持串口烧录

| 文档 | 下载链接 |
|------|---------|
| 蜂鸟M(US516P6) SOC产品手册(补充) | [下载](https://help.aimachip.com/attach_files/chip/461) |
| 蜂鸟M离线方案开发指导手册 | [下载](https://help.aimachip.com/attach_files/chip/34) |
| 蜂鸟M常见语音性能问题优化指导手册 | [下载](https://help.aimachip.com/attach_files/chip/33) |

---

### 蜂鸟 M1（US518P61）

低成本纯离线语音识别芯片。

**主要特点：**

- 芯片架构：32bit RISC + DSP 指令集 + FPU + FFT 加速器
- 系统支持：RTOS 轻量级系统
- 应用场景：智能家居、小家电、86 盒、玩具、灯具

| 文档 | 下载链接 |
|------|---------|
| 蜂鸟M1(US518P61) SOC产品手册 | [下载](https://help.aimachip.com/attach_files/chip/38) |
| 蜂鸟M1参考原理图 | [下载](https://help.aimachip.com/attach_files/chip/37) |

---

### 蜂鸟 M-T（US516T1）

低成本纯离线语音识别芯片。

**主要特点：**

- 芯片架构：32bit RISC + DSP 指令集 + FPU + FFT 加速器
- 本地指令：150 条离线识别
- 系统支持：RTOS 轻量级系统
- 应用场景：智能家居、小家电、86 盒、玩具、灯具

| 文档 | 下载链接 |
|------|---------|
| 蜂鸟MT(US516T1) SOC产品手册 | [下载](https://help.aimachip.com/attach_files/chip/42) |
| 蜂鸟M-T参考原理图 | [下载](https://help.aimachip.com/attach_files/chip/41) |
| 蜂鸟M-T离线方案开发指导手册 | [下载](https://help.aimachip.com/attach_files/chip/43) |

---

### 蜂鸟 W（US615U6）

安全 Wi-Fi/蓝牙双模智能语音 IoT 芯片。

**主要特点：**

- 芯片架构：MCU + 语音识别专用 NPU
- 无线支持：2.4G IEEE802.11b/g/n Wi-Fi + BLE 配网
- 安全特性：TEE 安全引擎、硬件加解密、固件加密存储、固件签名、安全调试
- 外围接口：UART、GPIO、SPI、SDIO、I2C、I2S、ADC、TouchSensor
- 本地指令：100 条离线识别，3-5 米远场
- 应用场景：智能家电、智能家居、智能玩具、无线音视频、工业控制、医疗监护

| 文档 | 下载链接 |
|------|---------|
| 蜂鸟W(US615) SOC产品手册 | [下载](https://help.aimachip.com/attach_files/chip/46) |
| 蜂鸟W参考原理图 | [下载](https://help.aimachip.com/attach_files/chip/45) |
| 蜂鸟W芯片方案开发指导手册 | [下载](https://help.aimachip.com/attach_files/chip/47) |

---

### 蜂鸟（US527U5）

高性能高集成度低成本智能语音芯片，专为离在线远场语音交互场景设计。

**主要特点：**

- 芯片架构：DSP + NPU + CPU 异步架构
- 前端性能：DSP 性能是 HiFi4 的两倍，提供更好的降噪、增强、BF 功能
- 本地指令：100 条离线识别
- 系统支持：RTOS 轻量级系统
- 应用场景：智能家居、智能家电、86 盒、灯具

| 文档 | 下载链接 |
|------|---------|
| 蜂鸟(US52X) SOC产品手册 | [下载](https://help.aimachip.com/attach_files/chip/50) |
| 蜂鸟离线模组参考原理图 | [下载](https://help.aimachip.com/attach_files/chip/51) |
| 蜂鸟离线方案开发指导手册 | [下载](https://help.aimachip.com/attach_files/chip/52) |

---

## WiFi 芯片

### XR872AT

| 文档 | 下载链接 |
|------|---------|
| XR872 Datasheet V1.0 | [下载](https://help.aimachip.com/attach_files/chip/18) |

---

## CI 系列芯片

### CI1301

| 文档 | 下载链接 |
|------|---------|
| CI1301 Datasheet V1.2 中文版 | [下载](https://help.aimachip.com/attach_files/chip/467) |

### CI1302

| 文档 | 下载链接 |
|------|---------|
| CI1302 Datasheet V1.2 中文版 | [下载](https://help.aimachip.com/attach_files/chip/468) |
| CI1302 中文数据手册 V0.7 | [下载](https://help.aimachip.com/attach_files/chip/441) |
| CI1302 英文版芯片手册 V1.2 | [下载](https://help.aimachip.com/attach_files/chip/373) |

### CI1303

| 文档 | 链接 |
|------|------|
| 详情页面 | [查看](https://help.aimachip.com/docs/chip/chip-1eighak1meul5) |

### CI1306

| 文档 | 链接 |
|------|------|
| 详情页面 | [查看](https://help.aimachip.com/docs/chip/chip-1eighfl1m9ou0) |

### CI230X

| 文档 | 链接 |
|------|------|
| 详情页面 | [查看](https://help.aimachip.com/docs/chip/chip-1eighgjh93k88) |

### CI1311

| 文档 | 链接 |
|------|------|
| 详情页面 | [查看](https://help.aimachip.com/docs/chip/chip-1fsi9suq57ht9) |

### CI1312

| 文档 | 链接 |
|------|------|
| 详情页面 | [查看](https://help.aimachip.com/docs/chip/chip-1fsi9t9v5anak) |

### CI13161

| 文档 | 链接 |
|------|------|
| 详情页面 | [查看](https://help.aimachip.com/docs/chip/chip-1fsi9vpuc9fpu) |

### CI13162

| 文档 | 链接 |
|------|------|
| 详情页面 | [查看](https://help.aimachip.com/docs/chip/chip-1fsia0f2huo7v) |

### CI13241

| 文档 | 链接 |
|------|------|
| 详情页面 | [查看](https://help.aimachip.com/docs/chip/chip-1fsia2i602r88) |

### CI13242

| 文档 | 链接 |
|------|------|
| 详情页面 | [查看](https://help.aimachip.com/docs/chip/chip-1fsia2nc44iqf) |

### CI13081

| 文档 | 链接 |
|------|------|
| 详情页面 | [查看](https://help.aimachip.com/docs/chip/chip-1g52dn07ns5t8) |

### CI13082

| 文档 | 链接 |
|------|------|
| 详情页面 | [查看](https://help.aimachip.com/docs/chip/chip-1g52dn80g31sc) |

---

## 参考链接

| 资源 | 链接 |
|------|------|
| 芯片手册官方首页 | [https://help.aimachip.com/docs/chip](https://help.aimachip.com/docs/chip) |
| 智能公元平台 | [https://smartpi.cn](https://smartpi.cn) |
