---
title: WiFi模组 BL-62B
icon: lucide/wifi
description: BL-62B WiFi+BLE 模组的规格说明、设计要点与开发流程。
---

# WiFi模组 BL-62B 章节文档

## 1. 文档定位与适用场景
- **文档目标**：面向需要将 BL-62B WiFi+BLE 模组快速集成到物联网终端的硬件与嵌入式开发者，提供规格、设计、开发、量产、维护所需的最小必备信息。
- **适用角色**：硬件工程师（原理图/PCB 设计）、嵌入式软件工程师（固件与 AT 配置）、生产测试工程师（烧录、校准）、项目经理（版本控制与交付验收）。
- **典型场景**：
  1. 家电联网（如空调、冰箱）通过 Wi-Fi 上报状态、下发控制。
  2. 工业/仓储传感器以 Wi-Fi 上传数据，并使用 BLE 做调试或配网。
  3. 智慧灯光/智能插座等低功耗控制设备需要 Wi-Fi 与 BLE 双模协同。
- **使用方式**：可作为模组数据手册补充，或作为开发入门的 SOP。

## 2. 模组概述与规格参数
BL-62B 基于 BL602 SoC，集成 2.4G 802.11b/g/n Wi-Fi 与 BLE 5.0，具备低功耗 32 位 RISC CPU、Cache 与片上存储。外围接口涵盖 UART、GPIO、ADC、DAC、PWM、I2C、SDIO、SPI、IR 等，适合需要 Wi-Fi 与 BLE 并存的 IoT 场景。

### 2.1 关键特性概述
| 类别 | 说明 |
| --- | --- |
| 无线能力 | 2.4 GHz IEEE 802.11b/g/n（1×1 SISO，20 MHz 带宽）、BLE 5.0（支持 BLE 辅助配网及双广播通道）。
| 处理器 | 32 位 RISC-V MCU，带 FPU、RTC、2×32 位定时器、4×DMA，DFS 频率 1 MHz ~ 192 MHz，支持 JTAG。|
| 内存与存储 | 276 KB RAM、128 KB ROM、1 Kb eFuse、片上 2 MB QSPI Flash（可挂载 XIP Flash）。|
| 无线协议/安全 | Wi-Fi 支持 WPS/WEP/WPA/WPA2 Personal、WPA2 Enterprise、WPA3；BLE 与 Wi-Fi 共存，集成 balun/PA/LNA。|
| 安全特性 | AES-128/192/256、SHA-1/224/256、TRNG、公钥加速器 (PKA)、QSPI OTFAD 即时解密。|
| 封装与尺寸 | SMD16 / DIP-16，16 mm × 24 mm × 3 mm；天线区域需 6 mm Keep-out，焊盘 1.5 mm 长、间距 2.0 mm。|
| 认证 | FCC、CE、IC、REACH、RoHS 等，量产需向模组供应链确认证书有效期。|

### 2.2 功能框图与主要参数
![BL-62B 功能框图](http://help.aimachip.com/uploads/wifi_image_xr50a/images/m_f28de39f639081e8b9ccdc7f3617fb19_r.png)

![BL-62B 主要参数](http://help.aimachip.com/uploads/wifi_image_xr50a/images/m_039a0a5f0ed6e4bcf15188c348af4273_r.png)

### 2.3 规格参数表
| 参数项 | 典型值/范围 | 备注 |
| --- | --- | --- |
| 工作电压 | 3.0 V ~ 3.6 V | 推荐 3.3 V，Ripple < 50 mV。|
| 峰值电流 | 发射场景典型 ≥350 mA | 需预留 >500 mA 供电裕量应对发射，详见规格书。|
| 低功耗模式 | 多级睡眠/唤醒 | 结合 PMU 配置，详见 `BL62B_EVB开发板用户指南V1.1.pdf`。|
| 工作温度 | -40 ℃ ~ 85 ℃ | 以规格书为准。|
| I/O 电压 | 1.8 V/3.3 V | 依据引脚复用，需在原理图注明。|
| 天线形式 | 板载 PCB / 外接 IPEX | 根据 BOM 选型，确保预留测试口。|

### 2.4 机械尺寸与封装
- 模组整体尺寸 16 mm（宽）× 24 mm（长）× 3 mm（厚），引脚面高度 0.8 mm，底部金手指长度 1.5 mm。
- 引脚分两侧各 8 个，Pad 间距 2.0 mm，焊盘宽 1.0 mm，焊盘间距中心到中心 2.2 mm；中部 14 mm × 14 mm 区域为主控与屏蔽罩。
- 顶部 6 mm 区域为 PCB 天线 Keep-out，禁止敷铜/走线/器件；建议外壳离天线边缘 ≥3 mm。
- 推荐使用无铅回流焊（峰值 235~250 ℃），端口底部预留 0.6 mm 走线窗口，可兼容贴片或垂直 DIP。

![BL-62B 模组尺寸（规格书 V1.2）](BL-62B模组规格书V1.2/BL-62B模组规格书V1.2-图片-3.jpg)

### 2.5 规格书主要参数（V1.2 摘录）
| 项目 | 说明 |
| --- | --- |
| 模组型号 | BL-62B |
| 封装 | SMD16 / DIP-16 |
| 物理尺寸 | 16 × 24 × 3 mm（±0.2 mm） |
| 认证 | FCC、CE、IC、REACH、RoHS |
| 内置 Flash | 芯片内置 2 MB QSPI Flash，可外接 Nor Flash |
| 支持接口 | UART / GPIO / ADC / DAC / PWM / I2C / SDIO / SPI / IR / PIR / TSEN / eFuse |
| I/O 数量 | 13（可复用为 SDIO、SPI、PWM、ADC 等） |
| 串口速率 | 9.6/19.2/38.4/115.2/921.6 kbps，最高 5 Mbps |
| 射频频段 | 2400 ~ 2483.5 MHz（Wi-Fi / BLE 共存） |
| 天线 | 板载 PCB 天线，支持外接 IPEX 天线 |
| Wi-Fi 安全 | WPS/WEP/WPA/WPA2 Personal/WPA2 Enterprise/WPA3 |
| 供电范围 | 3.0 V ~ 3.6 V，供电电流 >300 mA |
| 工作环境 | -30 ℃ ~ 85 ℃，< 90% RH |
| 存储环境 | -45 ℃ ~ 135 ℃，< 90% RH |

### 2.6 模块级管脚定义
> 与 EVB 板 18Pin 引出位不同，模组本体只暴露 SMD16/DIP-16 两行共 16Pin；IO0 默认驱动板载 LED，IO8 为下载脚。

| 序号 | Pin | 功能说明（节选自《BL-62B模组规格书V1.2》） |
| --- | --- | --- |
| 1 | RST | 模块复位输入 |
| 2 | IO5 | GPIO5 / SDIO_DAT3 / SPI_MOSI / I2C_SDA / UART / PWM_CH0 / ADC_CH4 / JTAG_TDI |
| 3 | IO2 | GPIO2 / SDIO_DAT0 / FLASH_D2 / SPI_SS / I2C_SCL / UART / PWM_CH2 / JTAG_TCK |
| 4 | IO11 | GPIO11 / SPI_SCLK / I2C_SDA / UART / PWM_CH1 / IR_OUT / ADC_CH10 / JTAG_TDO |
| 5 | IO12 | GPIO12 / SPI_MISO / I2C_SCL / UART1 / PWM_CH2 / ADC_VREF&CH0 / JTAG_TMS |
| 6 | IO14 | GPIO14 / SPI_SS / I2C_SCL / UART / PWM_CH4 / ADC_CH2 / DAC_OUTB / JTAG_TCK |
| 7 | IO17 | GPIO17 / FLASH_D3 / SPI_MOSI / I2C_SDA / UART / PWM_CH2 / DC_TP_OUT / JTAG_TDI |
| 8 | VCC | 3.3 V 电源输入 |
| 9 | GND | 数字地 |
|10 | IO0 | GPIO0 / SDIO_CLK / FLASH_D1 / SPI_MISO / I2C_SCL / UART / PWM_CH0 / JTAG_TMS（默认控制板载 LED） |
|11 | IO8 | GPIO8 / SPI_MISO / I2C_SCL / UART / PWM_CH3 / JTAG_TMS（下载模式需拉高，运行拉低） |
|12 | IO1 | GPIO1 / SDIO_CMD / FLASH_D2 / SPI_MOSI / I2C_SDA / UART / PWM_CH1 / JTAG_TDI |
|13 | IO3 | GPIO3 / SDIO_DAT1 / FLASH_D3 / SPI_SCLK / I2C_SDA / UART / PWM_CH3 / JTAG_TDO |
|14 | IO4 | GPIO4 / SDIO_DAT2 / SPI_MISO / I2C_SCL / UART / PWM_CH4 / ADC_CH1 / JTAG_TMS |
|15 | RXD0 | GPIO7 / SPI_SCLK / I2C_SDA / UART0_RX / UART / PWM_CH2 / JTAG_TDO（唯一可用于固件烧录的 RX） |
|16 | TXD0 | GPIO16 / SPI_MISO / I2C_SCL / UART0_TX / UART / PWM_CH1 / JTAG_TMS（唯一可用于固件烧录的 TX） |

> 若选择 UART 功能，需要配合 UART_SIGX_SEL(X=0~7) 将具体信号映射到对应引脚（SIG0/1/2/3：UART0 RTS/CTS/TXD/RXD，SIG4/5/6/7：UART1 RTS/CTS/TXD/RXD）。

### 2.7 典型应用电路
- 模块 VCC 侧需靠近引脚放置 100 nF 去耦电容，地线最短回路接至屏蔽壳。
- RST、BOOT（IO8）建议外接上拉/下拉与调试按键，方便量产烧录。
- UART0_TX/RX 需配合 3.3 V 电平串口（若连接 5 V MCU，请加电平转换）。

![BL-62B 参考应用电路](BL-62B模组规格书V1.2/BL-62B模组规格书V1.2-图片-13.jpg)

### 2.8 BL62B_EVB 资源与引脚映射
- **USB Type-C**：兼做电源输入与 UART0 调试口，供整板供电、固件烧录和日志输出。
- **BL-62B 模组载板**：内置 BL602，提供 RTOS、TCP/IP、低功耗和加密能力，可直接联调 IoT/M2M/智能家居。
- **按键与 IO8 跳帽**：板载复位键；烧录时将 IO8 跳帽拨至 H（拉高进入下载），运行时拨至 L（拉低，板内已下拉）。
- **RGB 指示灯**：R/G/B 分别连接 GPIO17/GPIO14/GPIO11，便于快速验证 PWM 与状态指示。

| 序号 | Pin | 主要复用功能（摘自《BL62B_EVB开发板用户指南V1.1》） |
| --- | --- | --- |
| 1 | RST | 复位输入 |
| 2 | IO5 | GPIO5 / SDIO_DAT3 / SPI_MOSI / I2C_SDA / UART / PWM_CH0 / ADC_CH4 / JTAG_TDI |
| 3 | IO2 | GPIO2 / SDIO_DAT0 / FLASH_D2 / SPI_SS / I2C_SCL / UART / PWM_CH2 / JTAG_TCK |
| 4 | IO11 | GPIO11 / SPI_SCLK / I2C_SDA / UART / PWM_CH1 / IR_OUT / ADC_CH10 / JTAG_TDO |
| 5 | IO12 | GPIO12 / SPI_MISO / I2C_SCL / UART / PWM_CH2 / ADC_VREF / ADC_CH0 / JTAG_TMS |
| 6 | IO14 | GPIO14 / SPI_SS / I2C_SCL / UART / PWM_CH4 / ADC_CH2 / DAC_OUTB / JTAG_TCK |
| 7 | IO17 | GPIO17 / FLASH_D3 / SPI_MOSI / I2C_SDA / UART / PWM_CH2 / DC_TP_OUT / JTAG_TDI |
| 8 | GND | 数字地 |
| 9 | 5V | 5 V 输出 |
| 10 | 3V3 | 3.3 V 输出 |
| 11 | GND | 数字地 |
| 12 | GND | 数字地 |
| 13 | IO0 | GPIO0 / SDIO_CLK / FLASH_D1 / SPI_MISO / I2C_SCL / UART / PWM_CH0 / JTAG_TMS |
| 14 | IO1 | GPIO1 / SDIO_CMD / FLASH_D2 / SPI_MOSI / I2C_SDA / UART / PWM_CH1 / JTAG_TDI |
| 15 | IO3 | GPIO3 / SDIO_DAT1 / FLASH_D3 / SPI_SCLK / I2C_SDA / UART / PWM_CH3 / JTAG_TDO |
| 16 | IO4 | GPIO4 / SDIO_DAT2 / SPI_MISO / I2C_SCL / UART / PWM_CH4 / ADC_CH1 / JTAG_TMS |
| 17 | RX0 | GPIO7 / SPI_SCLK / I2C_SDA / UART0_RX / UART / PWM_CH2 / JTAG_TDO（唯一可用于烧录的 RX） |
| 18 | TX0 | GPIO16 / SPI_MISO / I2C_SCL / UART0_TX / UART / PWM_CH1 / JTAG_TMS（唯一可用于烧录的 TX） |

> 选择 UART 功能后需配合 UART_SIGX_SEL（X=0~7）映射具体信号：SIG0/1/2/3 对应 UART0 RTS/CTS/TXD/RXD，SIG4/5/6/7 对应 UART1 RTS/CTS/TXD/RXD。  
> 参考示意：`smallpdf-convert-20251120-145546/BL62B_EVB开发板用户指南V1.1-1-图片-5.jpg`

## 3. 硬件设计指南
### 3.1 原理图要点
1. **供电设计**：为 3.3 V 主电源单独布置 LDO/DC-DC，输出需满足模组峰值电流，近模组放置 ≥22 µF + 0.1 µF 去耦。 
2. **复位与启动脚**：暴露 EN、RST、BOOT/GPIO 等关键引脚，便于固件烧录与量产测试。
3. **接口规划**：

| 接口 | 典型引脚 | 设计提示 |
| --- | --- | --- |
| UART0 | TXD0/RXD0 | 固件下载口，需引出 3.3 V、GND、RTS/CTS（如有）。|
| UART1 | TXD1/RXD1 | 推荐留作调试或外设控制。|
| SPI | MOSI/MISO/SCLK/CS | 走线等长，必要时加串阻抑制反射。|
| I2C | SDA/SCL | 需要上拉，阻值依赖总线容量。|
| PWM/ADC | GPIO 多复用 | 参考规格书映射表，避免与启动脚冲突。|

4. **调试接口**：暴露 SWD/JTAG（若 SoC 支持）或串口，方便固件调试。

### 3.2 PCB 与射频要求
- **天线隔离**：模组天线区（L 天线/PCB 天线）不得覆铜，保持 ≥15 mm 边界，底层禁止走线。
- **地平面**：在模组下方布满地平面并通过过孔密集连接，降低噪声。
- **差分/高速线**：SDIO/SPI 线长一致，拐角 45°，必要时加地护线。
- **散热**：高功耗场景建议在模组下方铺铜帮助散热。
- **ESD/浪涌**：对外接口（UART、GPIO、天线）加 TVS 管，防止静电损伤。

### 3.3 参考资料
- `BL62B_EVB开发板用户指南V1.1.pdf`：包含接口定义、夹具接线、典型原理图和 PCB 布局建议，可截取重点图示嵌入本章节。
- `BL-62B模组规格书V1.2.pdf`：提供完整引脚功能表、封装尺寸、RF 设计约束，量产前必须根据最新版确认。

### 3.4 电气与功耗指标（规格书 V1.2）
#### 3.4.1 环境与电气绝对值
| 参数 | 条件 | 最小 | 典型 | 最大 | 单位 |
| --- | --- | --- | --- | --- | --- |
| 存储温度 | - | -45 | 正常温度 | 135 | ℃ |
| 工作温度 | - | -30 | 20 | 85 | ℃ |
| 最大焊接温度 | IPC/JEDEC J-STD-020 | - | - | 260 | ℃ |
| 静电防护 (HBM) | - | 2000 | - | - | V |

#### 3.4.2 I/O 电压与逻辑阈值（VCC_IO=3.3 V）
| 参数 | 最小 | 典型 | 最大 | 单位 |
| --- | --- | --- | --- | --- |
| V<sub>IL</sub> | -0.3 | - | 1.32 | V |
| V<sub>IH</sub> | 2.06 | - | 3.6 | V |
| V<sub>OL</sub> (|I<sub>OL</sub>|=7.5~50 mA) | -0.3 | - | 0.4 | V |
| V<sub>OH</sub> (|I<sub>OH</sub>|=7.5~50 mA) | 2.9 | - | 3.4 | V |
| I<sub>MAX</sub> 单 GPIO | - | - | 12 | mA |

#### 3.4.3 Wi-Fi 射频性能
| 描述 | 最小 | 典型 | 单位 |
| --- | --- | --- | --- |
| 输入频率 | 2400 | 2483.5 | MHz |
| 匹配回损 S11 | - | < -10 | dB |
| 输出功率（CCK 1 Mbps） | - | 19.0 | dBm |
| 输出功率（11g 54 Mbps OFDM） | - | 17.7 | dBm |
| 输出功率（HT20 MCS0/MCS7） | - | 17.4 / 16.5 | dBm |
| EVM（CCK 1 Mbps / 11 Mbps） | -22.2 / -21.6 | - | dB |
| EVM（OFDM 6 Mbps / 54 Mbps） | -26.5 / -30 | - | dB |
| 接收灵敏度（CCK 1 Mbps / 11 Mbps） | -97 / -92 | - | dBm |
| 接收灵敏度（6 Mbps OFDM） | -92 | - | dBm |
| 接收灵敏度（54 Mbps OFDM） | -76 | - | dBm |
| 接收灵敏度（HT20 MCS0 / MCS7） | -92 / -74 | - | dBm |

#### 3.4.4 功耗（BL602，25 ℃，VCC=3.3 V）
| 模式 | 备注 | 最小 | 典型 | 单位 |
| --- | --- | --- | --- | --- |
| RX | 11b/11g/11n | - | 35/39/39 | mA |
| TX | 11b 11 Mbps@21 dBm | Duty 50% | 190 | mA |
| TX | 11b 11 Mbps@21 dBm | Duty 99% | 310 | mA |
| TX | 11g 54 Mbps@18 dBm | Duty 50% | 145 | mA |
| TX | 11g 54 Mbps@18 dBm | Duty 99% | 215 | mA |
| TX | 11n MCS7@17 dBm | Duty 50% | 130 | mA |
| TX | 11n MCS7@17 dBm | Duty 99% | 230 | mA |
| MCU Run | Freq @192 MHz | - | 22 | mA |
| MCU Standby | Freq <10 MHz | - | 2 | mA |
| Sleep | PDS7，快速唤醒 | - | 12 | µA |
| Hibernate | HBN，RTC 或 GPIO 唤醒 | - | 0.5 | µA |
| Shut-down | - | - | 0.1 | µA |

#### 3.4.5 焊接回流建议
- 升温区：25~150 ℃，速度 1~3 ℃/s，持续 60~90 s。
- 恒温区：150~200 ℃，持续 60~120 s。
- 回流峰值：235~250 ℃，>217 ℃ 的时间 60~90 s。
- 降温区：1~5 ℃/s，确保焊点完整性；建议遵循 IPC/JEDEC J-STD-020。

## 4. 开发环境与工具
### 4.1 推荐环境
| 组件 | 版本/要求 | 备注 |
| --- | --- | --- |
| 操作系统 | Windows 10 64-bit / Ubuntu 20.04 | 需具备 USB 转串口驱动权限。|
| 工具链 | Bouffalo Lab 官方 BL_MCU_SDK / GCC RISC-V 工具链 | 版本号随 SDK 发布，参见开发手册附件。|
| IDE | VS Code / Eclipse / 官方 BL DevCube | 依团队习惯，需安装 C/C++ 插件。|
| 烧录工具 | BLDevCube / BLFlashCube | 对应固件烧录，配置参数见下节。|
| 调试工具 | 串口助手、逻辑分析仪、数字万用表 | 串口需支持 3.3 V 电平。|

附：BL62B_EVB 用户指南提供的官方交叉编译与 SDK 资源：
- Windows 工具链：https://github.com/jixinintelligence/bl602-604-win-gcc.git
- Linux 工具链：https://github.com/jixinintelligence/bl602-604_toolchain.git
- SDK 源码：https://github.com/jixinintelligence/bl602-604.git
- 烧录工具：位于 SDK `tools/flash_tool/`

### 4.2 SDK 获取与目录结构
1. 从 MinDoc `BL-62B` 页面附件或内网镜像下载最新 SDK 包（含 BL_MCU_SDK、工具链与 PDF）。
2. 参考 MinDoc 附件《入门例程BL-62B.json》，将推荐工程导入 IDE，确保示例位于 `examples/wifi/` 目录。
3. SDK 结构示例：
```
bl62b-sdk/
  |- docs/  # 存放规格、API 与移植说明
  |- tools/ # 烧录、调试脚本
  |- examples/
      |- wifi/
      |- ble/
      |- combo/
  |- components/
```
4. 初始化工程后需执行 `python tools/env_check.py`（如有）验证依赖。

> 最小硬件准备清单：1×PC、1×BL62B_EVB 开发板、1×USB Type-C 数据线（来自 BL62B_EVB 用户指南 2.2 节）。

### 4.3 驱动与依赖
- 安装 USB 转串口驱动（如 CH340/CP210x）。
- 若使用 BLE 调试 APP，需预先注册开发者账号并获取云端配网参数，网络凭据由项目提供并在量产脚本中加密写入。

### 4.4 开发环境搭建参考
- SDK 内 `./docs/Quickstart_Guide` 提供从工具链安装、环境变量配置到示例工程编译/烧录的分步指引，可直接复用或改编为团队 SOP。

## 5. 固件烧录与升级
### 5.1 烧录准备
| 项目 | 描述 |
| --- | --- |
| 硬件连接 | 使用 4 线串口（TX/RX/3.3V/GND）连接模组，BOOT 脚拉至低电平进入下载模式。|
| 软件工具 | BLDevCube/BLFlashCube（与当前 SDK 发布包版本保持一致）。|
| 固件文件 | `.bin` / `.img`，建议统一存放在 `firmware/bl62b/`。|
| 供电 | 保持 3.3 V ±5%，烧录前确认电源稳定。|

### 5.2 烧录步骤
1. 打开 BLDevCube，选择芯片 `BL602/BL604`，串口设为调试口。 
2. 在 **MCU** 标签中加载 `boot2.bin`、`partition.bin`、`app.bin` 等镜像，地址按 SDK `partition_cfg_*.toml` 设置。
3. 设置波特率（推荐 2 Mbps，如稳定性不足可降至 921600）。
4. 点击 **Create & Download**，在日志中确认写入成功。
5. 断电或释放 BOOT 脚重启，验证串口日志。

### 5.3 OTA 升级流程
- 支持 HTTP/HTTPS 或 MQTT OTA。流程：
  1. 设备通过 Wi-Fi 连接至服务器，查询版本。
  2. 下载差分/整包并校验签名。
  3. 写入备用分区并重启。
- OTA 请求/响应字段示例：`{"product_key","sn","cur_ver","target_ver","firmware_url"}`，可参考入门例程 JSON 与后台接口文档。
- 若需要 BLE 辅助 OTA，可参考 `BL62B_EVB开发板用户指南V1.1.pdf` 中的测试流程。

### 5.4 量产烧录与校准
| 流程 | 关键点 |
| --- | --- |
| 批量夹具 | 夹具需引出 UART、供电、天线测试口，确保良好接触。|
| 校准项目 | XTAL 频偏、RF 输出功率、MAC/证书写入及功能自检，详见规格书附录。|
| 测试脚本 | 建议使用 Python/Go 编写烧录脚本，通过串口解析结果并输出 CSV 报告。|

## 6. 外设开发与应用
### 6.1 Wi-Fi 网络接入
- 快速接入流程：上电 -> 启动 STA -> 执行连接 -> 配置 MQTT/HTTP -> 数据上报。
- 推荐使用 AT 或 SDK API 两种方式：

| 场景 | 指令/API | 示例 | 备注 |
| --- | --- | --- | --- |
| STA 配网 | `AT+WJAP="SSID","PWD"` | ```AT+WJAP="DemoAP","12345678"
``` | 完整 AT 指令表见《BL62B_EVB开发板用户指南V1.1.pdf》。|
| MQTT 上报 | `mqtt_client_publish(topic, payload)` | 参考 `examples/wifi/mqtt_demo` | QoS/认证参数需根据项目确定。|
| HTTP OTA | `http_client_get(url)` | 参考 `examples/wifi/http_ota` | 需配置 TLS 根证书。|

- 对需要配网 APP/BLE 辅助配网的场景，使用 BLE 广播共享 Wi-Fi 凭据，详见下一小节。

### 6.2 BLE 调试与配网
1. 模组默认打开 BLE 广播（量产固件将广播设备标识、固件版本等基础信息）。
2. 广播帧字段包含设备 ID、固件版本、自定义配网标志。
3. 配网流程：
   - 手机 APP 通过 BLE 连接 -> 写入 Wi-Fi 凭据 -> 模组保存并重启 Wi-Fi。
4. BLE 服务 UUID、特征定义与通知格式可参照 `入门例程BL-62B.json` 或项目自定义协议。

### 6.3 外设接口示例
- **GPIO/PWM 控制**：
  ```c
  bl_gpio_enable(GPIO10);
  bl_pwm_set_duty(GPIO11, 50);
  ```
- **ADC 采样**：
  ```c
  adc_channel_config(channel, sample_rate);
  adc_read(channel, &value);
  ```
- **UART 数据透传**：通过 `AT+UART` 配置串口参数后使用 `AT+SEND=<len>` 发送数据；具体参数表见《BL62B_EVB开发板用户指南V1.1.pdf》。

### 6.4 示例工程
- `入门例程BL-62B.json` 覆盖 MQTT Demo、HTTP OTA、BLE Combo、低功耗示例等，可直接导入 SDK 项目；导入前确认所需外设（按例程说明连接按键、LED、传感器）及配置文件。

## 7. 常见问题排查 (FAQ)
| 问题 | 可能原因 | 排查步骤 |
| --- | --- | --- |
| 无法进入下载模式 | BOOT/RST 连接不正确或供电不足 | 检查 BOOT 脚电平、复位时序，并确认 3.3 V 稳定；必要时通过万用表测量。|
| Wi-Fi 连接频繁掉线 | AP 信号弱或功耗策略过激进 | 采集 RSSI、确认省电策略；在 SDK 中禁用过早休眠，或优化天线布局。|
| BLE 搜索不到 | BLE 未启用或广播间隔过长 | 通过日志确认 BLE 初始化；调整广播间隔至 100~500 ms。|
| MQTT 无法上线 | 证书/时间配置缺失 | 检查 TLS 根证书、系统时间；可在启动阶段通过 SNTP 或平台时间戳 API 同步。|
| OTA 失败 | 分区设置错误或网络超时 | 校验 `partition_cfg`，并在日志中查找 `OTA` 关键字；必要时降低下载速度。|
