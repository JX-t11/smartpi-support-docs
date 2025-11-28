
# 离线语音模组 SU-22T

## 文档定位与适用场景
- 适合家电、玩具、语音面板等无需联网即可响应的产品。
- 优势：低延时、本地数据安全；限制：词表容量有限，需要预置指令。

## 模组概述与规格参数

SU-22T 是一款低成本、低功耗、小体积的离线语音识别模组。

### 功能框图
![功能框图](http://help.aimachip.com/uploads/offline_su22t/images/m_3d413b27beb6e1e7bd88ff442ca11fee_r.png "SU-22T功能框图")

### 外观尺寸
![尺寸图1](http://help.aimachip.com/uploads/offline_su22t/images/m_02b3765d97f7c018de8cbeff11976994_r.png "外观尺寸")
![尺寸图2](http://help.aimachip.com/uploads/offline_su22t/images/m_05ce407347c6b78fd1cb35e0ee00ac48_r.png "侧面尺寸"),支持50条本地指令离线3-5米远场识别，支持RTOS轻量级系统，具有丰富的外围接口。特别适合于手持语音识别产品、电池供电产品等应用。

| 指标 | 内容 |
| --- | --- |
| 核心处理器 | 32bit 低功耗 RISC 内核 MCU @ 50MHz |
| 指令集 | 支持 DSP 指令集和 FPU 浮点运算单元 |
| NPU | 内置低功耗语音专用 NPU (神经网络处理单元) |
| 网络支持 | 支持 DNN/TDNN/LSTM 等主流网络 |
| 存储器 | 208KB SRAM + 1MB Flash |
| 音频输出 | 内置 1W 单声道 AB 类功放 |
| 麦克风 | 支持 1 路驻极体麦 |
| 供电 | 3.3V 电源输入 |
| 接口 | 1路UART, 2路I2C (400kHz), SPI (Master/Slave), PWM |
| 识别能力 | 支持50条本地指令，3-5米远场识别 |

> 完整资料参考：
> - [SU-22T 官方文档](https://help.aimachip.com/docs/offline_su22t)
> - [规格书](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1gb2jmqk30o27)
> - [原理图](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1gb2jlv1a2utp)

### 主要参数
![主要参数](http://help.aimachip.com/uploads/offline_su22t/images/m_c86ce5cd6a7507255f7a4c632700c42e_r.png "详细参数表")

## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具
- [开发包下载](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1eb42ql1i4h75)
- [CH340驱动](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1gb2j6ifmvg1t)
- [烧录软件](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1gb2j7enh3ild)
- [串口调试工具](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1gb2j8frbqhfo)
- [产品结构声学规范](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1gb2jdkhahq9q)
- [喇叭和咪头选型](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1gb2je1b0lk5i)

## 固件烧录与升级指南
1. 通过 USB/UART 将固件写入 Flash。
2. 使用配置工具导入词表、编译后烧录。
3. 复位设备并播放测试词表确认成功。

## 指令集 / 词表配置
- 支持多场景词表，结构为“唤醒词 → 命令组 → 动作”。
- 串口协议：0xAA 0x55 CMD LEN DATA CS（详见旧文档）。

> 教程参考：
> - [SU-22T语音控制四路继电器](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1epdknhetaa11)
> - [串口烧录教程](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1eqfq5oj20nn8)
> - [利用PWM灯光亮度调节和呼吸灯](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1eqg6058go5fd)
> - [SU-22T串口输入输出教学](https://help.aimachip.com/docs/offline_su22t/offline_su22t-1eqifb3sfe2m9)

## 外设开发与应用示例
- 继电器：识别指令后驱动 GPIO 切换。
- 串口反馈：将识别到的词 ID 发给主控。
- 联动应用：与 WiFi 模组结合，实现语音+云端控制。
