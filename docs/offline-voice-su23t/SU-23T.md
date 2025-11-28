
# 离线语音模组 SU-23T

## 文档定位与适用场景
- 适合家电、玩具、语音面板等无需联网即可响应的产品。
- 优势：低延时、本地数据安全；限制：词表容量有限，需要预置指令。

## 模组概述与规格参数

SU-23T 是亚毫瓦级超低功耗智能纯离线语音识别模组，面向带电池和便携式产品以及对功耗有严苛要求的各类产品。采用 MCU+语音识别专用 NPU 架构内核，采用超低功耗制程工艺，内置高精度语音检测模块配合系统多级启动模式使芯片待机功耗进入亚毫瓦级，工作功耗几毫瓦级别（除功放的功耗）。

| 指标 | 内容 |
| --- | --- |
| 架构 | MCU + 语音识别专用 NPU |
| 功耗特性 | 待机亚毫瓦级，工作几毫瓦级（不含功放） |
| 制程 | 超低功耗制程工艺 |
| 存储器 | 内置 SRAM + Flash |
| 音频输出 | 内置功率放大器 |
| 词表容量 | 50条本地指令 |
| 识别能力 | 3-5米远场识别 |
| 系统支持 | RTOS 轻量级系统 |
| 应用场景 | 带电池小家电、可穿戴设备、玩具、单火线86盒 |
| 供电 | 3.3 V，峰值电流待补 |
| 接口 | UART/GPIO/I2C（型号不同） |

> 完整资料参考：
> - [SU-23T 官方文档](https://help.aimachip.com/docs/offline_su23t)
> - [规格书](https://help.aimachip.com/docs/offline_su23t/offline_su23t-1gb2kbhqnocta)
> - [原理图](https://help.aimachip.com/docs/offline_su23t/offline_su23t-1gb2kb389620n)
> - [封装图](https://help.aimachip.com/docs/offline_su23t/offline_su23t-1gb2kbqtmh489)

### 基本资料附件

### 接口说明

### 开发与烧录资源附件

### 说明
- 去除“源资料路径”等占位文字，后续将直接补充原附件链接。

### 占位
- 待补附件：烧录文档/开发包等

## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具
- [开发包](https://help.aimachip.com/docs/offline_su23t/offline_su23t-1ers5jdo89if9)
- [CH340驱动](https://help.aimachip.com/docs/offline_su23t/offline_su23t-1gb2kcb01m29f)
- [烧录软件](https://help.aimachip.com/docs/offline_su23t/offline_su23t-1gb2kck2qgasl)
- [串口调试](https://help.aimachip.com/docs/offline_su23t/offline_su23t-1gb2kdng2f1v2)
- [产品结构声学规范](https://help.aimachip.com/docs/offline_su23t/offline_su23t-1gb2k9trophtb)
- [喇叭和咪头选型](https://help.aimachip.com/docs/offline_su23t/offline_su23t-1gb2ka6tvahck)

## 固件烧录与升级指南
1. 通过 USB/UART 将固件写入 Flash。
2. 使用配置工具导入词表、编译后烧录。
3. 复位设备并播放测试词表确认成功。

## 指令集 / 词表配置
- 支持多场景词表，结构为“唤醒词 → 命令组 → 动作”。
- 串口协议：0xAA 0x55 CMD LEN DATA CS（详见旧文档）。

> 教程参考：
> - [SU-23T转接板烧录教程](https://help.aimachip.com/docs/offline_su23t/offline_su23t-1ers5mquhdeag)
> - [SU-23T IO口输入输出教学](https://help.aimachip.com/docs/offline_su23t/offline_su23t-1es5qqqjujol9)
> - [SU-23T 串口输入输出教程](https://help.aimachip.com/docs/offline_su23t/offline_su23t-1es5tpug6ofsb)

## 外设开发与应用示例
- 继电器：识别指令后驱动 GPIO 切换。
- 串口反馈：将识别到的词 ID 发给主控。
- 联动应用：与 WiFi 模组结合，实现语音+云端控制。
