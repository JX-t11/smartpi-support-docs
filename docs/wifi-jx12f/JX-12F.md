---
title: WiFi模组 JX-12F
icon: lucide/wifi
description: JX-12F WiFi 模组的规格参数、硬件设计与联网开发指引。
---

# WiFi模组 JX-12F

## 文档定位与适用场景
- 面向硬件/嵌入式工程师，覆盖联网、云端控制、数据上报等场景。
- 适用 2.4 GHz Wi-Fi，默认对接智能公元平台，也可扩展到自有云端。

## 模组概述与规格参数

JX-12F 是一款基于 WiFi+BLE 单芯片 SoC 为主控的无线模组，核心处理器 JX-1001 集成了 2.4G Wi-Fi (802.11b/g/n) 和 BLE 5.0 的基带及 MAC 设计。微控制器子系统包含一个低功耗的 32 位 RISC CPU，高速缓存和存储器。

| 指标 | 描述 |
| --- | --- |
| 主控芯片 | JX-1001 (32位 RISC CPU + 高速缓存) |
| 无线能力 | WiFi: 2.4GHz 802.11b/g/n；BLE: 5.0 |
| 处理器 | 低功耗 32 位 RISC CPU，集成高速缓存和存储器 |
| 接口 | UART, GPIO, ADC, DAC, PWM, I2C, SDIO, SPI, IR 远程 |
| 供电 | 3.0~3.6 V (推荐3.3V) |
| 电源管理 | 先进的 PMU，支持多种低功耗模式 |

> 完整资料参考：
> - [JX-12F 官方文档](https://help.aimachip.com/docs/jx12f)
> - [开发手册](https://help.aimachip.com/docs/jx12f/jx12f-1f5tmab5mhti1)
> - [烧录资料](https://help.aimachip.com/docs/jx12f/jx12f-1f5p1tfbs88kl)
> - [参考例程](https://help.aimachip.com/docs/jx12f/jx12f-1f5tmcpj0j3oq)
> - [开发包](https://help.aimachip.com/docs/jx12f/jx12f-1f776ktu2kuik)

## 硬件设计指南
1. 电源：预留 500 mA 峰值，增加 TVS 与 LC 滤波。
2. 天线：避开金属件 15 mm，预留 π 匹配网络。
3. 接口：将 UART 下载脚暴露为测试点，GPIO 根据应用映射。
4. 参考开发手册中的原理图与PCB设计指南。

## 开发环境与工具准备
- [开发包下载](https://help.aimachip.com/docs/jx12f/jx12f-1f776ktu2kuik) - 包含SDK、示例代码、配置工具
- [烧录资料](https://help.aimachip.com/docs/jx12f/jx12f-1f5p1tfbs88kl) - 烧录软件与驱动
- 串口调试助手（3.3V电平）
- 智能公元平台账号（用于云端对接）

## 固件烧录与升级指南
1. 参考[烧录资料](https://help.aimachip.com/docs/jx12f/jx12f-1f5p1tfbs88kl)安装驱动和烧录工具。
2. 按"BOOT+RESET"进入下载模式，配置串口与波特率。
3. 选择固件文件并烧录。
4. 烧录完成后复位，通过串口查看日志验证。
5. OTA：通过云平台上传固件、配置灰度策略、监控升级状态。

## 外设开发与应用指南
- **GPIO/继电器控制**：通过AT指令或SDK API控制GPIO状态。
- **串口透传**：配置为透传模式，将模组作为WiFi桥接设备。
- **云端属性**：在智能公元平台绑定设备模板，实现远程控制和数据上报。
- **与语音模组联动**：通过 UART 与 CI/SU 系列语音模组协作，实现语音+联网功能。

> 详细示例请参考：[参考例程](https://help.aimachip.com/docs/jx12f/jx12f-1f5tmcpj0j3oq)

