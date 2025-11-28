
# 离线语音模组 SU-32T

## 文档定位与适用场景
- 适合家电、玩具、语音面板等无需联网即可响应的产品。
- 优势：低延时、本地数据安全；限制：词表容量有限，需要预置指令。

## 模组概述与规格参数
| 指标 | 内容 |
| --- | --- |
| 词表容量 | 待补（参考 `auto_get\\downloaded_aimachip\\docs\\offline_su32t` 规格书） |
| 唤醒词 | 固定或自定义（参考旧文档） |
| 供电 | 3.3 V，峰值电流待补 |
| 接口 | UART/GPIO/I2C（型号不同） |

# 规格书

- [SU-32T-V1.0-模组规格书.pdf](https://help.aimachip.com/attach_files/offline_su32t/950)

# 封装图

- [SU-32T V1.1-封装.PcbDoc](https://help.aimachip.com/attach_files/offline_su32t/951)

## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具
- 词表配置工具、串口烧录工具、日志查看软件。
- 安装步骤参考 auto_get/downloaded_aimachip/docs/offline_su32t 文档。

## 固件烧录与升级指南
1. 通过 USB/UART 将固件写入 Flash。
2. 使用配置工具导入词表、编译后烧录。
3. 复位设备并播放测试词表确认成功。

## 指令集 / 词表配置
- 支持多场景词表，结构为“唤醒词 → 命令组 → 动作”。
- 串口协议：0xAA 0x55 CMD LEN DATA CS（详见旧文档）。

# 开发板资料

- [SU-32T-开发板规格书.pdf](https://help.aimachip.com/attach_files/offline_su32t/949)
- [SU-32T-开发板原理图.SchDoc](https://help.aimachip.com/attach_files/offline_su32t/948)

## 外设开发与应用示例
- 继电器：识别指令后驱动 GPIO 切换。
- 串口反馈：将识别到的词 ID 发给主控。
- 联动应用：与 WiFi 模组结合，实现语音+云端控制。

