
# 离线语音模组 SU-20T

## 文档定位与适用场景
- 适合家电、玩具、语音面板等无需联网即可响应的产品。
- 优势：低延时、本地数据安全；限制：词表容量有限，需要预置指令。

## 模组概述与规格参数

SU-20T 是一款低成本、低功耗、小体积的离线语音识别模组，专为超低功耗应用设计。

### 功能框图
![功能框图](http://help.aimachip.com/uploads/offline_su20t/images/m_1ee74c3ca4b6c0ce42a4d1cd55990b6f_r.png "SU-20T功能框图")

### 外观尺寸
![尺寸图1](http://help.aimachip.com/uploads/offline_su20t/images/m_409d6fc70b101af5b53336a458a97f87_r.png "外观尺寸")
![尺寸图2](http://help.aimachip.com/uploads/offline_su20t/images/m_adb62bb166a8d8e2b5349dd46ecee4b0_r.png "侧面尺寸")内置高精度语音检测模块，配合系统多级启动模式使芯片待机功耗进入亚毫瓦级，工作功耗几毫瓦级别，能快速应用于智能家居、智能小家电、86盒、玩具、灯具等需要语音操控的产品。

| 指标 | 内容 |
| --- | --- |
| 核心处理器 | 32bit 低功耗 RISC 内核 MCU @ 50MHz |
| 指令集 | 支持 DSP 指令集和 FPU 浮点运算单元 |
| NPU | 低功耗语音专用 NPU (神经网络处理单元) |
| 存储器 | 208KB SRAM，512KB 内置Flash + 2MB 外置Flash |
| 音频输出 | 内置 3W 单声道 AB 类功放 |
| 麦克风 | 支持 1 路驻极体麦 + 1 路喇叭 |
| 供电 | 3.3V 电源输入 |
| 接口 | UART (3.3V电平) |
| 功耗 | 待机亚毫瓦级，工作几毫瓦级 |

> 完整资料参考：
> - [SU-20T 官方文档](https://help.aimachip.com/docs/offline_su20t)
> - [规格书](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1gb2giv8rh7gq)
> - [原理图](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1gb2gsr3tmoqt)

### 主要参数
![主要参数](http://help.aimachip.com/uploads/offline_su20t/images/m_e31ac44cc87e7fc596fce6eba3eade2a_r.png "详细参数表")

## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具
- [开发包下载](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1e9ckvgvp0prs) - 包含SDK、示例代码、配置工具
- [CH340驱动](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1gb2gk176g491) - USB转串口驱动
- [烧录软件](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1gb2gkumkrc6d) - 固件烧录工具
- [串口调试工具](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1gb2glkff1ti5)
- [产品结构声学规范](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1gb2guj7cjq6t)
- [喇叭和咪头选型](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1gb2guvpkpndd)

## 固件烧录与升级指南
1. 参考[烧录文档](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1gb2gkumkrc6d)安装驱动和烧录工具。
2. 通过 USB/UART 将固件写入 Flash。
3. 使用配置工具导入词表、编译后烧录。
4. 复位设备并播放测试词表确认成功。

> 参考资料：
> - [出厂固件](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1gb2glbqjuf37)
> - [芯片资料](https://help.aimachip.com/docs/offline_su20t/offline_su20t-1e9eet9mm20ut)

## 指令集 / 词表配置
- 支持多场景词表，结构为"唤醒词 → 命令组 → 动作"。
- 串口协议：0xAA 0x55 CMD LEN DATA CS
- 通过开发包中的配置工具可视化编辑词表。

## 外设开发与应用示例
- 继电器：识别指令后驱动 GPIO 切换。
- 串口反馈：将识别到的词 ID 发给主控。
- 联动应用：与 WiFi 模组结合，实现语音+云端控制。
