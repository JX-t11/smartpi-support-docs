
# 离线语音模组 CI-33T

## 文档定位与适用场景
- 适合家电、玩具、语音面板等无需联网即可响应的产品。
- 优势：低延时、本地数据安全；限制：词表容量有限，需要预置指令。

## 模组概述与规格参数
| 指标 | 内容 |
| --- | --- |
| 词表容量 | 待补（参考 `auto_get\\downloaded_aimachip\\docs\\offline_ci33t` 规格书） |
| 唤醒词 | 固定或自定义（参考旧文档） |
| 供电 | 3.3 V，峰值电流待补 |
| 接口 | UART/GPIO/I2C（型号不同） |

# 基本资料附件

- [CI-33T-V1.3-模组规格书.pdf](https://help.aimachip.com/attach_files/offline_ci33t/1007)
- [CI-33T-V1.3-原理图.pdf](https://help.aimachip.com/attach_files/offline_ci33t/1006)
- [CI-33T封装图.PCB](https://help.aimachip.com/attach_files/offline_ci33t/1008)

### 开发与烧录资源附件
- [01、CH340安装包.rar](https://help.aimachip.com/attach_files/offline_ci33t/1002)
- [02、模块烧录软件.rar](https://help.aimachip.com/attach_files/offline_ci33t/1003)
- [CI-33T烧录指引文档V1.2.docx](https://help.aimachip.com/attach_files/offline_ci33t/1004)
- [CI-33T烧录调试接线.png](https://help.aimachip.com/attach_files/offline_ci33t/1005)
- [04、模块出厂固件.rar](https://help.aimachip.com/attach_files/offline_ci33t/1001)
- [05、串口调试软件.rar](https://help.aimachip.com/attach_files/offline_ci33t/1000)
- [CI-33T开发包；版本V2.1.0.rar](https://help.aimachip.com/attach_files/offline_ci33t/999)
- [产品结构声学规范.rar](https://help.aimachip.com/attach_files/offline_ci33t/998)
- [喇叭和咪头选型推荐.rar](https://help.aimachip.com/attach_files/offline_ci33t/997)

### 说明
- 本节仅保留原资料的附件链接，去除冗余“项目分享/关闭”等内容。

## 硬件设计指南
1. 电源：独立 LDO，加 RC 滤波，保持语音前端稳定。
2. 麦克风/喇叭：差分走线、保持对称，严格按照推荐距离布置。
3. 串口/IO：预留调试接口并加 ESD 保护。

## 开发环境与工具
- 词表配置工具、串口烧录工具、日志查看软件。
- 安装步骤参考 auto_get/downloaded_aimachip/docs/offline_ci33t 文档。

## 固件烧录与升级指南
1. 通过 USB/UART 将固件写入 Flash。
2. 使用配置工具导入词表、编译后烧录。
3. 复位设备并播放测试词表确认成功。

## 指令集 / 词表配置
- 支持多场景词表，结构为“唤醒词 → 命令组 → 动作”。
- 串口协议：0xAA 0x55 CMD LEN DATA CS（详见旧文档）。

### 教程与配套固件
- [CI-33T语音+蓝牙控制灯泡教程](https://help.aimachip.com/docs/offline_ci33t/offline_ci33t-1eob1dvf3q5mo)
- [CI-33T语音+2.4G无线透传控制灯泡教程](https://help.aimachip.com/docs/offline_ci33t/offline_ci33t-1eob1neus8oio)

## 外设开发与应用示例
- 继电器：识别指令后驱动 GPIO 切换。
- 串口反馈：将识别到的词 ID 发给主控。
- 联动应用：与 WiFi 模组结合，实现语音+云端控制。
