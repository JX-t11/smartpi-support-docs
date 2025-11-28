
# 离线语音模组 CI-73T

## 文档定位与适用场景
- 适合家电、玩具、语音面板等无需联网即可响应的产品。
- 优势：低延时、本地数据安全；限制：词表容量有限，需要预置指令。

## 模组概述与规格参数

CI-73T 是新一代高性能神经网络智能语音模组，集成了脑神经网络处理器 BNPU V3.5 和 CPU 内核。

### 产品外观
![CI-73T模组](https://help.aimachip.com/uploads/ci73t/images/m_333645bdf10bc44daaac24860230567d_r.png "CI-73T模组")

### 外观尺寸
![尺寸图1](https://help.aimachip.com/uploads/ci73t/images/m_b13028f157378b8117c01fd6c6c69fa0_r.png "正面尺寸")
![尺寸图2](https://help.aimachip.com/uploads/ci73t/images/m_4cdc2229e44e0c6e0b56346b04aa323e_r.png "侧面尺寸")，适用于智能家居、智能小家电、86盒、玩具、灯具等需要语音操控的产品。

**版本说明**：
- **CI-73T1**: Flash 1MB
- **CI-73T2**: Flash 2MB

| 指标 | 内容 |
| --- | --- |
| 核心处理器 | BNPU V3.5 (神经网络处理器) + 32位CPU |
| 主频 | 最高 210MHz，支持 DSP 扩展加速 |
| 存储器 | 288KB SRAM + 256bit eFuse + 1MB/2MB Flash |
| 神经网络 | 支持 DNN/TDNN/RNN/CNN，可实现高性能语音识别、语音降噪 |
| 音频接口 | 单通道 Audio Codec (ADC+DAC)，支持 8/16/24/32/44.1/48kHz 采样率 |
| 播放功能 | 集成 PA 功率放大器，支持 ALC 自动电平控制 |
| 供电范围 | 3.6V - 5.5V (支持 5V 直接输入) |
| 外设接口 | 3路 UART (最高3Mbps)，1路 IIC，4路 PWM，12个 GPIO |
| 定时器 | 2组 32-bit Timer + 独立看门狗 (IWDG) |
| ESD防护 | 内部增强设计，可通过 4KV 接触放电试验 |

> 完整资料参考：
> - [CI-73T规格书](https://help.aimachip.com/attach_files/ci73t/836)
> - [CI-73T原理图V1.1](https://help.aimachip.com/attach_files/ci73t/835)
> - [产品结构声学规范](https://help.aimachip.com/docs/ci73t/ci73t-1ga9mf9dm92pd)
> - [喇叭和咪头选型](https://help.aimachip.com/docs/ci73t/ci73t-1ga9mg1drm94b)

## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具
- 词表配置工具、串口烧录工具、日志查看软件。
- [CI-73T开发包 V2.1.0](https://help.aimachip.com/attach_files/ci73t/846) - 包含SDK、示例代码、配置工具
- [CH340驱动](https://help.aimachip.com/docs/ci73t/ci73t-1ga9m689eo81r) - USB转串口驱动
- [烧录软件](https://help.aimachip.com/docs/ci73t/ci73t-1ga9m7421n66p) - 固件烧录工具
- [串口调试工具](https://help.aimachip.com/docs/ci73t/ci73t-1ga9m88iuaifv) - 日志查看与命令调试

## 固件烧录与升级指南
1. 安装 CH340 驱动，连接开发板的 USB/UART 接口。
2. 打开烧录软件，选择对应的固件文件（.bin）。
3. 使用配置工具导入词表、编译后生成固件。
4. 点击烧录，等待进度完成。
5. 复位设备并播放测试词表确认成功。

> 参考资料：
> - [烧录文档](https://help.aimachip.com/docs/ci73t/ci73t-1ga9m7fqq5ebj)
> - [出厂固件](https://help.aimachip.com/docs/ci73t/ci73t-1ga9m7os1qmtc)
> - [固件制作演示](https://help.aimachip.com/docs/ci73t/ci73t-1ft7tkm913b0f)
> - [GPIO/串口控制功能演示视频](https://help.aimachip.com/docs/ci73t/ci73t-1fsujbrejoiff)

## 指令集 / 词表配置
- 支持多场景词表，结构为“唤醒词 → 命令组 → 动作”。
- 串口协议：0xAA 0x55 CMD LEN DATA CS
- 通过开发包中的配置工具可视化编辑词表，支持自定义唤醒词和命令词。
- 每个命令可绑定 GPIO 输出、串口消息、音频播放等动作。

> 详细教程：[相关教程配套固件](https://help.aimachip.com/docs/ci73t/ci73t-1fsuj900vqrvp)

## 外设开发与应用示例
- 继电器：识别指令后驱动 GPIO 切换。
- 串口反馈：将识别到的词 ID 发给主控。
- 联动应用：与 WiFi 模组结合，实现语音+云端控制。

