
# 离线语音模组 SU-21T

## 文档定位与适用场景
- 适合家电、玩具、语音面板等无需联网即可响应的产品。
- 优势：低延时、本地数据安全；限制：词表容量有限，需要预置指令。

## 模组概述与规格参数

SU-21T 是一款低成本、小体积、超低功耗的离线语音识别模组。

### 功能框图
![功能框图](http://help.aimachip.com/uploads/offline_su21t/images/m_88710a5e5a3bca1a66bf82f74c2ea0a5_r.png "SU-21T功能框图")

### 外观尺寸
![尺寸图1](http://help.aimachip.com/uploads/offline_su21t/images/m_5195a7328551a15524a0e64f84ad18a0_r.png "外观尺寸")
![尺寸图2](http://help.aimachip.com/uploads/offline_su21t/images/m_7a869db6a28e57399885b6f241fa5d46_r.png "侧面尺寸"),完美嵌套各类PCB，内置高精度语音检测模块配合系统多级启动模式使芯片待机功耗进入亚毫瓦级，工作功耗几毫瓦级别。

| 指标 | 内容 |
| --- | --- |
| 核心处理器 | 32bit 超低功耗 RISC 内核 MCU @ 50MHz |
| 指令集 | 支持 DSP 指令集和 FPU 浮点运算单元 |
| NPU | 低功耗语音专用 NPU (神经网络处理单元) |
| 存储器 | 208KB SRAM + 1MB Flash |
| 麦克风 | 支持 1 路驻极体麦 |
| 供电 | 3.3V 电源输入 |
| 接口 | UART (3.3V电平) |
| 功耗 | 待机亚毫瓦级，工作几毫瓦级 |

> 完整资料参考：
> - [SU-21T 官方文档](https://help.aimachip.com/docs/offline_su21t)
> - [规格书](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1gb2j7ik4lpf4)
> - [原理图](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1gb2j3itkpacg)

### 主要参数
![主要参数](http://help.aimachip.com/uploads/offline_su21t/images/m_a264b99659a1e049c9d3624b36e4b5d5_r.png "详细参数表")

## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具
- [开发包下载](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1ermqtjmcbo1b)
- [CH340驱动](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1gb2hkm8qnnh6)
- [烧录软件](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1gb2hlcok72aj)
- [串口调试工具](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1gb2hmb13rqgg)
- [产品结构声学规范](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1gb2iarufdc4j)
- [喇叭和咪头选型](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1gb2ib22qitgi)

## 固件烧录与升级指南
1. 通过 USB/UART 将固件写入 Flash。
2. 使用配置工具导入词表、编译后烧录。
3. 复位设备并播放测试词表确认成功。

## 指令集 / 词表配置
- 支持多场景词表，结构为“唤醒词 → 命令组 → 动作”。
- 串口协议：0xAA 0x55 CMD LEN DATA CS（详见旧文档）。

> 教程参考：
> - [SU-21T转接板烧录](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1eri6t7rma7lv)
> - [SU-21T输入输出教学](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1eri8ibv89ls3)
> - [SU-21T串口输入输出教程](https://help.aimachip.com/docs/offline_su21t/offline_su21t-1ermqgsh80p58)

## 外设开发与应用示例
- 继电器：识别指令后驱动 GPIO 切换。
- 串口反馈：将识别到的词 ID 发给主控。
- 联动应用：与 WiFi 模组结合，实现语音+云端控制。

