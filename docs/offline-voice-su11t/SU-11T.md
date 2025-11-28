
# 离线语音模组 SU-11T

## 文档定位与适用场景
- 适合家电、玩具、语音面板等无需联网即可响应的产品。
- 优势：低延时、本地数据安全；限制：词表容量有限，需要预置指令。

## 模组概述与规格参数

SU-11T 是一款低成本、低功耗、小体积的离线语音识别模组，具有丰富的系统外设资源，包括 UART、I2C、SPI、PWM、ADC 等，能快速应用于智能家居，各类智能小家电，86盒，玩具，灯具等需要语音操控的产品。

| 指标 | 内容 |
| --- | --- |
| 核心处理器 | 32bit RISC 内核 @ 240MHz |
| 指令集 | 支持 DSP 指令集和 FPU 浮点运算单元 |
| FFT加速器 | 最大支持 1024 点复数 FFT/IFFT 运算，或 2048 点实数 FFT/IFFT |
| 存储器 | 内置高速 SRAM + 1MB Flash |
| 音频输出 | 内置 2.4W 单声道 AB 类功放 |
| 麦克风 | 支持 1 路驻极体麦 |
| 供电 | 5V 电源输入，内置5V转3.3V (3.3V外部负载不超过150mA) |
| 接口 | UART (3.3V), I2C, SPI (Master/Slave), 2路PWM, I2S, ADC (12-bit SAR) |
| 保护 | 内置 POR、低电压检测、看门狗 |
| 芯片方案 | 蜂鸟M1 (US518P61) |

> 完整资料参考：
> - [SU-11T 官方文档](https://help.aimachip.com/docs/offline_su11t)
> - [模组规格书 V1.0](https://help.aimachip.com/attach_files/offline_su11t/208)
> - [原理图 V1.0](https://help.aimachip.com/attach_files/offline_su11t/209)

## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具
- [开发手册](https://help.aimachip.com/docs/offline_su11t/offline_su11t-1e9cl47e5drim)
- [烧录资料](https://help.aimachip.com/attach_files/offline_su11t/207)
- [芯片资料：蜂鸟M1](http://help.aimachip.com/docs/chip/chip-1e9c8pkvotlbr)

## 固件烧录与升级指南
1. 通过 USB/UART 将固件写入 Flash。
2. 使用配置工具导入词表、编译后烧录。
3. 复位设备并播放测试词表确认成功。

## 指令集 / 词表配置
- 支持多场景词表，结构为“唤醒词 → 命令组 → 动作”。
- 串口协议：0xAA 0x55 CMD LEN DATA CS（详见旧文档）。

> 开发参考：
> - [烧录资料](https://help.aimachip.com/docs/offline_su11t/offline_su11t-1e9cl4b9cdcmi)
> - [芯片资料](https://help.aimachip.com/docs/offline_su11t/offline_su11t-1e9eev2eeksg0)

## 外设开发与应用示例
- 继电器：识别指令后驱动 GPIO 切换。
- 串口反馈：将识别到的词 ID 发给主控。
- 联动应用：与 WiFi 模组结合，实现语音+云端控制。

