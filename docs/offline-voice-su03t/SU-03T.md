
# 离线语音模组 SU-03T

## 文档定位与适用场景
- 适合家电、玩具、语音面板等无需联网即可响应的产品。
- 优势：低延时、本地数据安全；限制：词表容量有限，需要预置指令。

## 模组概述与规格参数

SU-03T 是一款低成本、低功耗、小体积的离线语音识别模组，能快速应用于智能家居、智能小家电、86盒、玩具、灯具等需要语音操控的产品。

### 产品外观
![SU-03T模组](http://help.aimachip.com/uploads/offline_su03t/images/m_2d304486dfc378816d5a4af73d544004_r.png "SU-03T模组")

### 外观尺寸
![尺寸图1](http://help.aimachip.com/uploads/offline_su03t/images/m_080f3c3df80084ad5d4e88fab588338d_r.png "外观尺寸")
![尺寸图2](http://help.aimachip.com/uploads/offline_su03t/images/m_07c91fa8f490336921af7558392cc15d_r.png "PCB尺寸")

| 指标 | 内容 |
| --- | --- |
| 核心处理器 | 32bit RISC 内核 @ 240MHz |
| 指令集 | 支持 DSP 指令集和 FPU 浮点运算单元 |
| 加速器 | FFT 加速器 (最大1024点复数FFT/IFFT 或 2048点实数FFT/IFFT) |
| 存储器 | 高速 SRAM + 内置 2MB Flash |
| 音频输出 | 内置 2.4W 单声道 AB 类功放 |
| 麦克风 | 支持 1 路驻极体麦 |
| 音频接口 | I2S input/output |
| 供电 | 5V 电源输入，内置 5V→3.3V (外部负载≤150mA) |
| 时钟源 | RC 12MHz + PLL 锁相环 |
| 外设接口 | 1路 SPI Master (30MHz)，1路 SPI Slave (30MHz)，1路全双工 UART (3Mbps, 3.3V) |
| GPIO | 所有 GPIO 可配置外部中断和唤醒源 |
| 保护功能 | 内置 POR、低电压检测、看门狗 |

> 完整资料参考：
> - [SU-03T 官方文档](https://help.aimachip.com/docs/offline_su03t)
> - [基本资料与规格书](https://help.aimachip.com/docs/offline_su03t/offline_su03t-1e9c63ok0doou)

### 主要参数表
![主要参数1](http://help.aimachip.com/uploads/offline_su03t/images/m_bc91ca3d234ca73bcff61582728eaa9e_r.png "主要参数表")
![主要参数2](http://help.aimachip.com/uploads/offline_su03t/images/m_89ac46589c055c7c342c56c813b00ae8_r.png "详细参数")

### 管脚定义
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

