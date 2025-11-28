
# 离线语音模组 CI-96Z

## 文档定位与适用场景
- 适合家电、玩具、语音面板等无需联网即可响应的产品。
- 优势：低延时、本地数据安全；限制：词表容量有限，需要预置指令。

## 模组概述与规格参数

CI-96Z61/CI-96Z62 金手指模组是新一代高性能神经网络智能语音模组，集成了脑神经网络处理器 BNPU V3.5 和 CPU 内核，性价比极高。

**版本说明**：
- CI-96Z61: 1MB Flash
- CI-96Z62: 2MB Flash

| 指标 | 内容 |
| --- | --- |
| 核心处理器 | BNPU V3.5 (神经网络处理器) + CPU @ 210MHz |
| 存储器 | 288KB SRAM + 1MB/2MB Flash (两种版本) |
| 音频 | 单通道高性能低功耗 Audio Codec |
| 电源 | 集成 PMU 电源管理单元和 RC 振荡器 |
| 外设接口 | 2 路 UART |
| 封装 | 金手指模组 |
| 应用场景 | 智能家居、小家电、86盒、玩具、灯具 |

> 完整资料参考：
> - [CI-96Z 官方文档](https://help.aimachip.com/docs/ci76z)
> - [CI-96Z61 规格书](https://help.aimachip.com/attach_files/ci76z/852)
> - [CI-96Z62 规格书](https://help.aimachip.com/attach_files/ci76z/853)

## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具
- [开发包](https://help.aimachip.com/docs/ci76z/ci76z-1fsi846of9deb)
- [CH340驱动](https://help.aimachip.com/docs/ci76z/ci76z-1gajqr2sup2ni)
- [烧录软件](https://help.aimachip.com/docs/ci76z/ci76z-1gajqrf0ufi11)
- [串口调试](https://help.aimachip.com/docs/ci76z/ci76z-1gajqs3e0dcdm)
- [产品结构声学规范](https://help.aimachip.com/docs/ci76z/ci76z-1gajrfpg05p5e)
- [喇叭和咪头选型](https://help.aimachip.com/docs/ci76z/ci76z-1gajrg3duft4t)

## 固件烧录与升级指南
1. 通过 USB/UART 将固件写入 Flash。
2. 使用配置工具导入词表、编译后烧录。
3. 复位设备并播放测试词表确认成功。

## 指令集 / 词表配置
- 支持多场景词表，结构为“唤醒词 → 命令组 → 动作”。
- 串口协议：0xAA 0x55 CMD LEN DATA CS（详见旧文档）。

> 开发参考：
> - [烧录文档](https://help.aimachip.com/docs/ci76z/ci76z-1gajqrm8sk086)
> - [出厂固件](https://help.aimachip.com/docs/ci76z/ci76z-1gajqrsk2bj76)
> - [芯片资料](https://help.aimachip.com/docs/ci76z/ci76z-1fsi84eholulr)

## 外设开发与应用示例
- 继电器：识别指令后驱动 GPIO 切换。
- 串口反馈：将识别到的词 ID 发给主控。
- 联动应用：与 WiFi 模组结合，实现语音+云端控制。

