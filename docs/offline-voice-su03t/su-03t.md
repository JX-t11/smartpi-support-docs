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
| 待机电流 | ~30mA |
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

### 电气特性
![电气特性](http://help.aimachip.com/uploads/offline_su03t/images/m_286d5aa899e75c05607f28e4bcdd00ba_r.png "电气特性参数")

### 回流焊曲线图
![回流焊曲线](http://help.aimachip.com/uploads/offline_su03t/images/m_3e68303c3d2438dd9984766534ff241d_r.png "回流焊温度曲线")

### 应用电路图
![应用电路](http://help.aimachip.com/uploads/offline_su03t/images/m_3ad236755572fdddfe6c7528952157ec_r.png "典型应用电路")

## 开发环境与工具
- 词表配置工具、串口烧录工具、日志查看软件。
- [SU-03T开发包(老版本)](https://help.aimachip.com/docs/offline_su03t/su_03t_kfb) - 包含SDK、示例代码、配置工具
- [蜂鸟M、脱机烧录器演示固件](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1ecu2mfa1run0)
- [其他开发资料](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1gbcdfsv7adqr)

## 固件烧录与升级指南
1. 安装烧录软件与驱动，连接开发板的 UART 接口。
2. 打开烧录工具，选择对应的固件文件（.bin）。
3. 使用配置工具导入词表、编译后生成固件。
4. 点击烧录按钮，等待进度完成。
5. 复位设备并通过串口或播放测试词表确认成功。

> 参考资料：
> - [常见资料下载](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1e9ef1me6u76e)

## 指令集 / 词表配置
- 支持多场景词表，结构为“唤醒词 → 命令组 → 动作”。
- 串口协议：0xAA 0x55 CMD LEN DATA CS
- 通过开发包中的配置工具可视化编辑词表，支持自定义唤醒词和命令词。
- 每个命令可绑定 GPIO 输出、串口消息、音频播放等动作。

> 教程与示例：
> - [IO输入输出配套固件](https://help.aimachip.com/docs/offline_su03t/su_03t_io)
> - [串口教程配套固件](https://help.aimachip.com/docs/offline_su03t/SU-03T_usart)
> - [ADC教程配套固件](https://help.aimachip.com/docs/offline_su03t/su_03t_adc)
> - [六路继电器配套固件](https://help.aimachip.com/docs/offline_su03t/su_03t_relay)
> - [红外收发配套固件](https://help.aimachip.com/docs/offline_su03t/SU-03T_irc)
> - [呼吸灯、PWM柔和调光固件](https://help.aimachip.com/docs/offline_su03t/su_03t_PWM)
> - [更多教程](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1ec2jtqqtopq7)

## 外设开发与应用示例
- 继电器：识别指令后驱动 GPIO 切换。
- 串口反馈：将识别到的词 ID 发给主控。
- 联动应用：与 WiFi 模组结合，实现语音+云端控制。

---

## 参考链接

| 资源 | 链接 |
|------|------|
| SU-03T 官方文档首页 | [https://help.aimachip.com/docs/offline_su03t](https://help.aimachip.com/docs/offline_su03t) |
| 智能公元平台 | [https://smartpi.cn](https://smartpi.cn) |
| 芯片资料 | [查看](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1e9c648nb2nec) |
