---
title: 离线语音模组 CI-33T
icon: material/microphone
description: 高性能神经网络离线语音模组 CI-33T 完整开发指南，支持500词条和4M Flash。
---

# 离线语音模组 CI-33T

## 快速规格一览

| 参数 | 规格 |
|------|------|
| 主控芯片 | CI1303 |
| 综合识别率 | 95% |
| 供电电压 | 3.6-5.5V |
| 词条数 | **500** |
| Flash | **4M** |
| SRAM | 640KB |
| AEC（回声消除） | ✓ |
| 双麦算法 | ✓ |
| 单/双麦 | 双麦 |
| 适用环境 | 中噪声环境 |
| 待机电流 | ~60mA |
| 工作电流 | >500mA (4Ω喇叭) |
| 功放功率 | 2.4W@5V4Ω |
| 封装 | SMD22/DIP22 |
| 尺寸 | 21×15mm |

### 高级功能支持

| 功能 | 支持情况 |
|------|---------|
| 自然说 | ✓ |
| 声纹识别 | ✓ |
| 声源定位 | ✓ |
| 哭声检测 | ✓ |
| 鼾声检测 | ✓ |
| 文字转语音(TTS) | ✓ |
| 自学习 | ✓ |
| 支持语言 | 中/英/日/韩（其他语种可定制） |
| 平台能力 | 支持生成固件 |

### CI-33T vs CI-03T 对比

| 参数 | CI-33T | CI-03T |
|------|--------|--------|
| 词条数 | **500** | 300 |
| Flash | **4M** | 2M |
| 主控芯片 | CI1303 | CI1302 |
| 其他特性 | 相同 | 相同 |

> CI-33T 相比 CI-03T 主要优势在于更大的词条容量（500 vs 300）和更大的 Flash（4M vs 2M），适合需要更多命令词的应用场景。

---

## 定位与适用场景

- **定位**：新一代高性能神经网络离线语音模组，集成 BNPU V3 + CPU，可单独作为语音主控使用
- **适用场景**：
  - **智能家电**：风扇、晾衣架、加湿器、茶壶等需要语音控制的产品
  - **智能照明**：台灯、吸顶灯、氛围灯
  - **智能门锁/安防类**：门锁、门磁、门禁面板
  - **智能玩具与小家电**：故事机、互动玩偶、小型清洁类设备等
  - **其他**：86盒、语音面板等无需联网即可响应的产品
- **优势**：低延时、本地数据安全、大词条容量（500词）
- **版本说明**：
  - **普通双咪版本**：适合双麦克风降噪场景，内部不支持 AEC
  - **单咪 AEC 版本**：单麦克风配合内部 AEC 算法，可有效抑制回声

---

## 模组概述

CI-33T 是我司研发的新一代高性能神经网络智能语音模组，集成了脑神经网络处理器 BNPU V3 和 CPU 内核，系统主频可达 220MHz，内置高达 640KByte 的 SRAM，集成 PMU 电源管理单元，高性能低功耗 Audio Codec+ClassAB 功率放大器和多路 UART、IIC、IIS、PWM、GPIO、PDM 等外围控制接口。

### 核心特性

| 指标分类 | 参数项 | 规格/数值 |
|---------|-------|----------|
| **核心性能** | AI运算内核 | BNPU V3 神经网络加速器 |
| | CPU | 32位高性能CPU，最高220MHz |
| | DSP | 32-bit单周期乘法器，支持DSP扩展加速 |
| **存储资源** | SRAM | 640KB |
| | Flash | 4MB |
| | eFuse | 512bit |
| **音频接口** | Codec | 内置高性能低功耗Audio Codec |
| | ADC/DAC | 双路ADC + 单路DAC |
| | 采样率 | 8/16/24/32/44.1/48 kHz |
| | ALC | 支持自动电平控制 |
| | IIS | 1路音频扩展通路 |
| | 功放 | 内置ClassAB功率放大器 |
| **电源** | 供电范围 | 3.6V ~ 5.5V |
| | LDO | 内置3个高性能LDO |
| **外设接口** | UART | 3路，最高3M波特率 |
| | IIC | 1路 |
| | PWM | 5路 |
| | GPIO | 9个（部分支持5V宽压） |
| | ADC | 1路10bit SAR ADC @1MHz |
| | Timer | 4组32-bit |
| | Watchdog | IWDG + WWDG |
| **EMC/ESD** | EMC | 支持FCC标准 |
| | ESD | 4KV接触放电 |
| | 环保 | ROHS/REACH |

---

## 基本资料下载

- [CI-33T-V1.3-模组规格书.pdf](https://help.aimachip.com/attach_files/offline_ci33t/1007)
- [CI-33T-V1.3-原理图.pdf](https://help.aimachip.com/attach_files/offline_ci33t/1006)
- [CI-33T封装图.PCB](https://help.aimachip.com/attach_files/offline_ci33t/1008)

### 开发与烧录资源附件
- [01、CH340安装包.rar](https://help.aimachip.com/attach_files/offline_ci33t/1002)
- [02、模块烧录软件.rar](https://help.aimachip.com/attach_files/offline_ci33t/1003)
- [CI-33T烧录指引文档V1.2.docx](https://help.aimachip.com/attach_files/offline_ci33t/1004)
- [CI-33T烧录调试接线.png](https://help.aimachip.com/attach_files/offline_ci33t/1005)
- [04、模块出厂固件.rar](https://help.aimachip.com/attach_files/offline_ci33t/1001)
- [05、串口调试软件.rar](https://help.aimachip.com/attach_files/offline_ci33t/1000)
- [CI-33T开发包；版本V2.1.0.rar](https://help.aimachip.com/attach_files/offline_ci33t/999)
- [产品结构声学规范.rar](https://help.aimachip.com/attach_files/offline_ci33t/998)
- [喇叭和咪头选型推荐.rar](https://help.aimachip.com/attach_files/offline_ci33t/997)

---

## 硬件设计指南

### 1. 电源设计

- **独立供电**：建议使用独立的 LDO 或 DC-DC + LDO 为模组供电
- **滤波电容**：在 VCC 引脚附近放置 10uF + 100nF 滤波电容
- **接地设计**：数字地与模拟地单点汇合，避免大电流回流经过音频前端

### 2. 声学设计

- **麦克风布局**：差分走线并包地处理，麦克风孔应有良好密封性
- **隔离设计**：麦克风与喇叭之间应有声学隔离（如减震棉）
- **功放电路**：功放电路应远离麦克风电路

### 3. 接口与防护

- **UART/IO**：预留 TX/RX 测试点以便调试升级
- **ESD 防护**：对外接口建议放置 ESD 保护器件

### 参考设计文档

- [产品结构声学规范.rar](https://help.aimachip.com/attach_files/offline_ci33t/998)
- [喇叭和咪头选型推荐.rar](https://help.aimachip.com/attach_files/offline_ci33t/997)

---

## 开发环境搭建

### 开发工具下载

| 工具 | 说明 | 下载链接 |
|------|------|---------|
| CI-33T 开发包 V2.1.0 | SDK和开发资源 | [下载](https://help.aimachip.com/attach_files/offline_ci33t/999) |
| CH340 驱动 | USB转串口驱动 | [下载](https://help.aimachip.com/attach_files/offline_ci33t/1002) |
| 烧录软件 | 模块烧录工具 | [下载](https://help.aimachip.com/attach_files/offline_ci33t/1003) |
| 串口调试软件 | 串口通信调试 | [下载](https://help.aimachip.com/attach_files/offline_ci33t/1000) |

### 环境准备

1. 安装 CH340 USB转串口驱动
2. 安装烧录软件
3. 注册智能公元平台账号（配置词表和语音）

---

## 固件烧录指南

### 烧录文档

- [CI-33T烧录指引文档V1.2.docx](https://help.aimachip.com/attach_files/offline_ci33t/1004)
- [CI-33T烧录调试接线.png](https://help.aimachip.com/attach_files/offline_ci33t/1005)

### 烧录步骤

1. **硬件连接**：将模组 UART_TX/RX 与 PC 串口工具连接，保证 GND 相连
2. **进入烧录模式**：拉低 BOOT 引脚后上电
3. **执行烧录**：打开烧录软件，选择固件文件与端口，点击开始烧录
4. **验证结果**：复位模组，对着麦克风说出唤醒词，观察串口日志与语音播报

### 出厂固件

- [04、模块出厂固件.rar](https://help.aimachip.com/attach_files/offline_ci33t/1001)

---

## 指令集与词表配置

- 支持多场景词表，结构为"唤醒词 → 命令组 → 动作"
- 词条容量：**500条**（比 CI-03T 多 200 条）
- 通过智能公元平台配置唤醒词、命令词和回复语
- 串口协议：`0xAA 0x55 [CMD] [LEN] [DATA] [CS]`

---

## 教程与配套固件

### 项目教程

| 教程名称 | 说明 | 下载链接 |
|---------|------|---------|
| 语音+蓝牙控制灯泡 | 使用CI-33T和蓝牙模块远距离控制灯泡 | [下载ZIP](https://help.aimachip.com/attach_files/offline_ci33t/534) |
| 语音+2.4G无线透传控制灯泡 | 使用语音模块和2.4G无线透传实现超远距离控制 | [下载ZIP](https://help.aimachip.com/attach_files/offline_ci33t/552) |

### 在线教程链接

- [CI-33T语音+蓝牙控制灯泡教程](https://help.aimachip.com/docs/offline_ci33t/offline_ci33t-1eob1dvf3q5mo)
- [CI-33T语音+2.4G无线透传控制灯泡教程](https://help.aimachip.com/docs/offline_ci33t/offline_ci33t-1eob1neus8oio)

---

## 外设开发与应用示例

### 场景 1：继电器控制（开关灯）

```c
// 伪代码示例
void on_voice_command(int cmd_id) {
    if (cmd_id == CMD_LIGHT_ON) {
        gpio_set_level(PIN_RELAY, 1);
        play_voice("灯已打开");
    }
}
```

### 场景 2：串口透传（对接主控 MCU）

- CI-33T 作为语音协处理器，识别成功后通过串口发送 ID 给主控 MCU
- 协议示例：`0xAA 0x55 [CMD_ID] [DATA_LEN] [DATA] [CHECKSUM]`

### 场景 3：联动应用

- 与 WiFi 模组（如 BL-62B）结合，实现语音+云端控制
- 典型方案：CI-33T（语音识别）+ BL-62B（WiFi联网）

---

## 参考链接

| 资源 | 链接 |
|------|------|
| CI-33T 官方文档首页 | [https://help.aimachip.com/docs/offline_ci33t](https://help.aimachip.com/docs/offline_ci33t) |
| 智能公元平台 | [https://smartpi.cn](https://smartpi.cn) |
| CI-03T 文档（参考） | [https://help.aimachip.com/docs/offline_ci03t](https://help.aimachip.com/docs/offline_ci03t) |
