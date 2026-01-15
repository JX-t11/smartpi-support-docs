---
title: 离线语音模组 CI-95C
icon: material/microphone
description: 高性能神经网络离线语音模组 CI-95C 完整开发指南，支持1000词条、97%识别率、蓝牙小程序。
---

# 离线语音模组 CI-95C

## 快速规格一览

| 参数 | CI-95C1/C2 |
|------|------------|
| 主控芯片 | CI1352 |
| 综合识别率 | **97%** |
| 供电电压 | 3.6-5.5V |
| 词条数 | **1000** |
| Flash | **4M** |
| SRAM | 640KB |
| AEC（回声消除） | ✗ |
| 双麦算法 | ✓ |
| 单/双麦 | 双麦 |
| 适用环境 | 高噪声环境 |
| 待机电流 | ~45mA |
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
| **蓝牙/小程序** | **✓** |
| **小程序修改语音指令** | **✓** |
| 支持语言 | 中/英/日/韩 |
| 平台能力 | 支持生成固件 |

### CI-95C 定位

> CI-95C 是 **高端旗舰型**，相比其他 CI 系列：

> - **识别率最高**：97%（vs CI-03T/CI-33T/CI-73T 的 95%）
> - **词条数最多**：1000条（vs CI-03T 的 300、CI-33T 的 500、CI-73T 的 100）
> - **蓝牙小程序**：支持通过小程序修改语音指令（OTA升级）
> - **适用场景**：高噪声环境，对识别率要求高的产品

---

## 定位与适用场景

- **定位**：高端旗舰型高性能神经网络离线语音模组，集成 BNPU V3 + CPU
- **适用场景**：

    - **智能家电**：风扇、晾衣架、加湿器、茶壶等
    - **智能照明**：台灯、吸顶灯、氛围灯
    - **智能门锁/安防类**：门锁、门磁、门禁面板
    - **智能玩具与小家电**：故事机、互动玩偶等
    - **其他**：86盒、语音面板等
- **优势**：高识别率(97%)、大词条容量(1000词)、蓝牙小程序支持
- **版本说明**：

    - **CI-95C1**：Flash 1MB
    - **CI-95C2**：Flash 2MB

---

## 模组概述

CI-95C 是我司研发的新一代高性能神经网络智能语音模组，集成了脑神经网络处理器 BNPU V3 和 CPU 内核，系统主频可达 220MHz，内置高达 640KByte 的 SRAM，集成 PMU 电源管理单元，高性能低功耗 Audio Codec+Class AB 功率放大器和 UART、IIC、PWM、GPIO 等外围控制接口。

支持 DNN/TDNN/RNN/CNN 等神经网络及卷积计算，支持语音识别、声纹识别、**命令词自学习**、语音检测及**深度学习降噪**等功能。

### 核心特性

| 指标分类 | 参数项 | 规格/数值 |
|---------|-------|----------|
| **核心性能** | AI运算内核 | BNPU V3 神经网络加速器 |
| | CPU | 32位高性能CPU，最高220MHz |
| | DSP | 32-bit单周期乘法器，支持DSP扩展加速 |
| | 神经网络 | 支持 DNN/TDNN/RNN/CNN |
| **存储资源** | SRAM | 640KB |
| | Flash | 1MB (CI-95C1) / 2MB (CI-95C2) |
| | eFuse | 512bit |
| **音频接口** | Codec | 单通道 Audio Codec (ADC+DAC) |
| | 采样率 | 8/16/24/32/44.1/48 kHz |
| | ALC | 支持自动电平控制 |
| | 功放 | 内置Class AB功率放大器 |
| **电源** | 供电范围 | 3.6V ~ 5.5V |
| | LDO | 内置3个高性能LDO |
| | 时钟 | 内置RC振荡器 |
| **外设接口** | UART | 3路（UART0支持5V电平通讯） |
| | IIC | 1路 |
| | PWM | 4路 |
| | GPIO | 12个 |
| **EMC/ESD** | EMC | 支持FCC标准 |
| | ESD | 4KV接触放电 |
| | 环保 | ROHS/REACH |

### 基本资料下载

| 资料 | 链接 |
|------|------|
| 规格书 | [下载](https://help.aimachip.com/attach_files/ci95c/968) |
| 原理图 | [查看](https://help.aimachip.com/docs/ci95c/ci95c-1gbc4s9t0h53j) |
| 封装图 | [查看](https://help.aimachip.com/docs/ci95c/ci95c-1gbc4slitcarm) |

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

- [产品结构声学规范](https://help.aimachip.com/docs/ci95c/ci95c-1gbc4u6b1uffk)
- [喇叭和咪头选型](https://help.aimachip.com/docs/ci95c/ci95c-1gbc4udomsj3l)

---

## 开发环境搭建

### 开发工具下载

| 工具 | 说明 | 下载链接 |
|------|------|---------|
| 开发包 | SDK、示例代码、配置工具 | [下载](https://help.aimachip.com/docs/ci95c/ci95c-1fsi86li45iaf) |
| CH340 驱动 | USB转串口驱动 | [下载](https://help.aimachip.com/docs/ci95c/ci95c-1gbc4su0hjk96) |
| 烧录软件 | 固件烧录工具 | [下载](https://help.aimachip.com/docs/ci95c/ci95c-1gbc4terinvt9) |
| 串口调试工具 | 日志查看与命令调试 | [下载](https://help.aimachip.com/docs/ci95c/ci95c-1gbc4tsroi2tj) |

### 环境准备

1. 安装 CH340 USB转串口驱动
2. 安装烧录软件
3. 注册智能公元平台账号（配置词表和语音）

---

## 固件烧录指南

### 烧录步骤

1. **安装驱动**：安装 CH340 驱动，连接开发板的 USB/UART 接口
2. **打开软件**：打开烧录软件，选择对应的固件文件（.bin）
3. **配置词表**：使用配置工具导入词表、编译后生成固件
4. **执行烧录**：点击烧录，等待进度完成
5. **验证结果**：复位设备并播放测试词表确认成功

### 烧录资料

| 资料 | 链接 |
|------|------|
| 烧录文档 | [查看](https://help.aimachip.com/docs/ci95c/ci95c-1gbc4t9nju523) |
| 出厂固件 | [下载](https://help.aimachip.com/docs/ci95c/ci95c-1gbc4tneb1d42) |
| 芯片资料 | [查看](https://help.aimachip.com/docs/ci95c/ci95c-1fsi86ue89j82) |

---

## 指令集与词表配置

- 支持多场景词表，结构为"唤醒词 → 命令组 → 动作"
- 词条容量：**1000条**（CI系列最大）
- 通过开发包中的配置工具可视化编辑词表
- 支持自定义唤醒词和命令词
- 每个命令可绑定 GPIO 输出、串口消息、音频播放等动作
- 串口协议：`0xAA 0x55 [CMD] [LEN] [DATA] [CS]`

### 蓝牙小程序功能

CI-95C 支持通过蓝牙小程序进行配置：

- **OTA 升级**：通过小程序修改语音指令，无需重新烧录
- **词表配置**：在线修改唤醒词和命令词
- **参数调整**：调整识别阈值、音量等参数

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

## 参考链接

| 资源 | 链接 |
|------|------|
| CI-95C 官方文档首页 | [https://help.aimachip.com/docs/ci95c](https://help.aimachip.com/docs/ci95c) |
| 智能公元平台 | [https://smartpi.cn](https://smartpi.cn) |
| CI-03T 文档（参考） | [https://help.aimachip.com/docs/offline_ci03t](https://help.aimachip.com/docs/offline_ci03t) |
| CI-96Z 文档（参考） | [https://help.aimachip.com/docs/ci76z](https://help.aimachip.com/docs/ci76z) |
