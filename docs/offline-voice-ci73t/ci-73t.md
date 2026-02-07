---
title: 离线语音模组 CI-73T
icon: material/microphone
description: 高性能神经网络离线语音模组 CI-73T 完整开发指南，采用 BNPU V3.5，性价比之选。
---

# 离线语音模组 CI-73T

## 快速规格一览

| 参数 | CI-73T1（单麦） | CI-73T2（双麦） |
|------|----------------|----------------|
| 主控芯片 | CI13241 | CI13241 |
| 综合识别率 | 95% | 95% |
| 供电电压 | 3.6-5.5V | 3.6-5.5V |
| 词条数 | 100 | 100 |
| Flash | 1M (CI-73T1) | 2M (CI-73T2) |
| SRAM | 288KB | 288KB |
| AEC（回声消除） | ✗ | ✗ |
| 双麦算法 | ✗ | ✓ |
| 单/双麦 | 单麦 | 双麦 |
| 适用环境 | 中噪声环境 | 高噪声环境 |
| 待机电流 | ~45mA | ~45mA |
| 工作电流 | >500mA (4Ω喇叭) | >500mA (4Ω喇叭) |
| 功放功率 | 2.4W@5V4Ω | 2.4W@5V4Ω |
| 封装 | SMD22/DIP22 | SMD22/DIP22 |
| 尺寸 | 21×15mm | 21×15mm |

### 高级功能支持

| 功能 | 支持情况 |
|------|---------|
| 自然说 | ✓ |
| 声纹识别 | ✓ |
| 声源定位 | ✓ |
| 哭声检测 | ✓ |
| 鼾声检测 | ✓ |
| 文字转语音(TTS) | ✓ |
| 多意图识别 | ✓ |
| 红外控制 | ✓（需平台配置） |
| 自学习 | ✓ |
| 支持语言 | 中/英/日/韩（其他语种可定制） |
| 平台能力 | 支持生成固件 |

### CI-73T 定位

> CI-73T 是 **性价比之选**，相比 CI-03T/CI-33T：

> - **优势**：成本更低，适合对词条数要求不高的场景
> - **限制**：词条数 100（vs CI-03T 的 300、CI-33T 的 500）
> - **特点**：采用 BNPU V3.5，支持 CNN 神经网络

---

## 定位与适用场景

- **定位**：性价比型高性能神经网络离线语音模组，集成 BNPU V3.5 + CPU
- **适用场景**：

    - **智能家电**：风扇、晾衣架、加湿器、茶壶等
    - **智能照明**：台灯、吸顶灯、氛围灯
    - **智能门锁/安防类**：门锁、门磁、门禁面板
    - **智能玩具与小家电**：故事机、互动玩偶等
    - **其他**：86盒、语音面板等
- **优势**：低延时、本地数据安全、成本优化
- **版本说明**：

    - **CI-73T1**：单麦版本，Flash 1MB，适合安静/中噪声环境
    - **CI-73T2**：双麦版本，支持 AEC 和双麦算法，适合高噪声环境

---

## 模组概述

CI-73T 是我司研发的新一代高性能神经网络智能语音模组，集成了脑神经网络处理器 BNPU V3.5 和 CPU 内核，系统主频可达 210MHz，内置高达 288KByte 的 SRAM，集成 PMU 电源管理单元和 RC 振荡器，集成单通道高性能低功耗 Audio Codec 和多路 UART、IIC、PWM、GPIO 等外围控制接口。

### 产品外观

![CI-73T模组](https://help.aimachip.com/uploads/ci73t/images/m_333645bdf10bc44daaac24860230567d_r.png "CI-73T模组")

### 外观尺寸

![尺寸图1](https://help.aimachip.com/uploads/ci73t/images/m_b13028f157378b8117c01fd6c6c69fa0_r.png "正面尺寸")
![尺寸图2](https://help.aimachip.com/uploads/ci73t/images/m_4cdc2229e44e0c6e0b56346b04aa323e_r.png "侧面尺寸")

### 核心特性

| 指标分类 | 参数项 | 规格/数值 |
|---------|-------|----------|
| **核心性能** | AI运算内核 | BNPU V3.5 神经网络加速器 |
| | CPU | 32位高性能CPU，最高210MHz |
| | DSP | 32-bit单周期乘法器，支持DSP扩展加速 |
| | 神经网络 | 支持 DNN/TDNN/RNN/CNN |
| **存储资源** | SRAM | 288KB |
| | Flash | 1MB (CI-73T1) / 2MB (CI-73T2) |
| | eFuse | 256bit |
| **音频接口** | Codec | 单通道 Audio Codec (ADC+DAC) |
| | 采样率 | 8/16/24/32/44.1/48 kHz |
| | ALC | 支持自动电平控制 |
| | 功放 | 集成PA功率放大器 |
| **电源** | 供电范围 | 3.6V ~ 5.5V |
| | 时钟 | 内置RC振荡器 |
| **外设接口** | UART | 3路，最高3M波特率 |
| | IIC | 1路 |
| | PWM | 4路 |
| | GPIO | 12个（支持中断，上下拉可配置） |
| | Timer | 2组32-bit |
| | Watchdog | IWDG |
| **EMC/ESD** | ESD | 4KV接触放电 |

> 完整资料参考：
> - [CI-73T规格书](https://help.aimachip.com/attach_files/ci73t/836)
> - [CI-73T原理图V1.1](https://help.aimachip.com/attach_files/ci73t/835)
> - [产品结构声学规范](https://help.aimachip.com/docs/ci73t/ci73t-1ga9mf9dm92pd)
> - [喇叭和咪头选型](https://help.aimachip.com/docs/ci73t/ci73t-1ga9mg1drm94b)

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

- [CI-73T规格书](https://help.aimachip.com/attach_files/ci73t/836)
- [CI-73T原理图V1.1](https://help.aimachip.com/attach_files/ci73t/835)
- [产品结构声学规范](https://help.aimachip.com/docs/ci73t/ci73t-1ga9mf9dm92pd)
- [喇叭和咪头选型](https://help.aimachip.com/docs/ci73t/ci73t-1ga9mg1drm94b)

---

## 开发环境搭建

### 开发工具下载

| 工具 | 说明 | 下载链接 |
|------|------|---------|
| CI-73T 开发包 V2.1.0 | SDK、示例代码、配置工具 | [下载](https://help.aimachip.com/attach_files/ci73t/846) |
| CH340 驱动 | USB转串口驱动 | [下载](https://help.aimachip.com/docs/ci73t/ci73t-1ga9m689eo81r) |
| 烧录软件 | 固件烧录工具 | [下载](https://help.aimachip.com/docs/ci73t/ci73t-1ga9m7421n66p) |
| 串口调试工具 | 日志查看与命令调试 | [下载](https://help.aimachip.com/docs/ci73t/ci73t-1ga9m88iuaifv) |

### 环境准备

1. 安装 CH340 USB转串口驱动
2. 安装烧录软件
3. 注册智能公元平台账号（配置词表和语音）

---

### CI-73T有哪些教程资源？

**问题描述：**

需要获取CI-73T模块的相关教程，包括开发包、烧录教程等学习资料。

**解决方案：**

**官方教程资源：**

1. **开发包下载**：

    - 最新版本开发包 V2.1.0
    - 下载地址：[CI-73T开发包](https://help.aimachip.com/docs/ci73t/ci73t-1ga9ln8gktcu1)
    - 包含：SDK、示例代码、配置工具

2. **烧录教程**：

    - 视频教程：[CI-73T烧录教程](https://www.bilibili.com/video/BV1fPUmYxENX/)
    - 内容涵盖：烧录工具使用、固件下载、调试方法
    - 适合初学者快速上手

3. **官方文档**：

    - 首页链接：[CI-73T官方文档](https://help.aimachip.com/docs/ci73t)
    - 包含：规格书、原理图、应用笔记

**学习路径建议：**

1. **入门阶段**：

    - 阅读规格书了解硬件参数
    - 观看烧录教程熟悉开发流程
    - 下载开发包并运行示例

2. **进阶学习**：

    - 学习智能公元平台使用
    - 掌握词表配置方法
    - 实践自定义功能开发

3. **实战项目**：

    - 从简单控制项目开始
    - 逐步添加复杂功能
    - 参考示例代码学习

**其他资源：**

- 技术支持群：加入官方技术交流群
- 社区论坛：查看他人项目经验
- 在线客服：工作时间实时答疑

**注意事项：**

- 开发包需要使用最新版本，确保兼容性
- 烧录前请先安装CH340驱动
- 遇到问题优先查看官方文档和FAQ
- 保留学习笔记，便于后续查阅

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
| 烧录文档 | [查看](https://help.aimachip.com/docs/ci73t/ci73t-1ga9m7fqq5ebj) |
| 出厂固件 | [下载](https://help.aimachip.com/docs/ci73t/ci73t-1ga9m7os1qmtc) |
| 固件制作演示 | [查看](https://help.aimachip.com/docs/ci73t/ci73t-1ft7tkm913b0f) |
| GPIO/串口控制功能演示视频 | [观看](https://help.aimachip.com/docs/ci73t/ci73t-1fsujbrejoiff) |

---

## 指令集与词表配置

- 支持多场景词表，结构为"唤醒词 → 命令组 → 动作"
- 词条容量：**100条**
- 通过开发包中的配置工具可视化编辑词表
- 支持自定义唤醒词和命令词
- 每个命令可绑定 GPIO 输出、串口消息、音频播放等动作
- 串口协议：`0xAA 0x55 [CMD] [LEN] [DATA] [CS]`

> 详细教程：[相关教程配套固件](https://help.aimachip.com/docs/ci73t/ci73t-1fsuj900vqrvp)

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

- CI-73T 作为语音协处理器，识别成功后通过串口发送 ID 给主控 MCU
- 协议示例：`0xAA 0x55 [CMD_ID] [DATA_LEN] [DATA] [CHECKSUM]`

### 场景 3：联动应用

- 与 WiFi 模组（如 BL-62B）结合，实现语音+云端控制
- 典型方案：CI-73T（语音识别）+ BL-62B（WiFi联网）

---

## 参考链接

| 资源 | 链接 |
|------|------|
| CI-73T 官方文档首页 | [https://help.aimachip.com/docs/ci73t](https://help.aimachip.com/docs/ci73t) |
| 智能公元平台 | [https://smartpi.cn](https://smartpi.cn) |
| 平台入门视频 | [观看](https://www.bilibili.com/video/BV1e8411T77q/?spm_id_from=333.999.0.0) |
| CI-03T 文档（参考） | [https://help.aimachip.com/docs/offline_ci03t](https://help.aimachip.com/docs/offline_ci03t) |
| CI-33T 文档（参考） | [https://help.aimachip.com/docs/offline_ci33t](https://help.aimachip.com/docs/offline_ci33t) |
