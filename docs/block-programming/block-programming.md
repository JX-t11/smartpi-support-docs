# CI-03T/CI-33T 搭配米思奇图形化编程

CI-03T/CI-33T 离线语音模组支持使用米思奇（Mixly）进行图形化编程开发，无需编写 C 代码即可实现语音控制、串口通信等功能。

!!! warning "重要提示"
    使用前请将米思齐软件更新到最新版 **Mixly 2.0 rc4**！绝大多数的报错都是米思齐版本不一致导致的！

---

## 01、开发环境搭建

### 安装包下载

安装包下载地址：[01、米思奇软件安装和模块导入；版本2310081760.zip](https://help.aimachip.com/attach_files/block/639)

### 1. 安装 Notepad++ 并发送至桌面

将 Notepad++ 发送至桌面并打开，后续需要用它编辑配置文件。

### 2. 配置账号信息

找到 `CI-03T安装包/ci03t/build` 目录下的 `blockTool.exe.config` 文件，使用 Notepad++ 打开，分别填写在智能公元平台注册的账号和密码。

![配置文件示例](http://help.aimachip.com/uploads/block/images/m_c03cd9b0b5b77edd879b195e139f280c_r.png)

### 3. 更新米思奇软件

打开米思奇软件安装包，选择 **一键更新** 到最新版本。

!!! tip "建议"
    多更新两次，一般一次不能更新到位。

![Mixly 软件一键更新示意](http://help.aimachip.com/uploads/block/images/m_719cceb66e334faf6a455f284cf52eeb_r.png)

### 4. 导入板卡

打开米思奇并导入板卡，在右上角板卡选择列表中确认目标板卡已加载。

![导入板卡菜单](http://help.aimachip.com/uploads/block/images/m_c65d91e5846fcbdf3c881d84eb391af9_r.png)

### 5. 硬件连接

正确连接模块和 CH340：

| 模组引脚 | CH340 引脚 | 说明 |
|---------|-----------|------|
| TX | RX | 发送 → 接收（交叉连接） |
| RX | TX | 接收 → 发送（交叉连接） |
| GND | GND | 共地 |
| 5V/3.3V | 5V/3.3V | 供电保持一致 |

![硬件连接示意](http://help.aimachip.com/uploads/block/images/m_f6449a06986d9dd5cabb8bb452258ee8_r.png)

### 6. 上传固件

点击左上角 **"上传"** 按钮，等待固件生成。此过程大约需要 3 分钟左右。

![编译生成提示](http://help.aimachip.com/uploads/block/images/m_f7104bb76f16f28ad1572ba7fb0acaad_r.png)
!!! warning "重要"
    固件生成成功后，根据提示将设备 **重新上电**，完成烧录。

---

## 02、CI-03T 与 Arduino 进行串口通信

### 硬件连接

| CI-03T 引脚 | Arduino 引脚 |
|------------|-------------|
| TX | RX |
| RX | TX |
| GND | GND |

### Block 逻辑示例

1. 初始化串口（波特率 9600 或与 Arduino 同步）
2. 语音识别"打开空调" → 串口发送 `AC_ON`
3. 语音识别"关闭空调" → 串口发送 `AC_OFF`

### Arduino 代码示例

```cpp
void setup() {
  Serial.begin(9600);
  pinMode(13, OUTPUT);
}

void loop() {
  if (Serial.available()) {
    String cmd = Serial.readString();
    if (cmd == "AC_ON") {
      digitalWrite(13, HIGH);
    } else if (cmd == "AC_OFF") {
      digitalWrite(13, LOW);
    }
  }
}
```

### 验证

对模组说"打开空调"，观察 Arduino LED 是否点亮；使用串口助手可查看原始数据。

**示例附件下载**：[02、米思奇环境Arduino接收CI-03T发出的数据，并作出反馈；版本2305161011.zip](https://help.aimachip.com/attach_files/block/523)

---

## 03、CI03T 对接 Block

### API 接口文档

Block 生成固件 API 链接地址：[API 文档](https://console-docs.apipost.cn/preview/fd2e6ef6f45ac983/1a1bedf171ee2377)

---

## 常用积木指令

### 流程控制积木

- **顺序执行**：按顺序执行积木块
- **条件判断**：如果…否则…
- **循环**：重复 N 次、条件循环

### 变量与运算积木

- 数值 / 文本 / 布尔变量管理状态
- 支持基础算术与比较运算

### 硬件控制积木

| 分类 | 用法 | 注意事项 |
|-----|------|---------|
| 数字输出 | 控制引脚高低电平（LED、继电器） | 校准引脚映射，避免冲突 |
| PWM 输出 | 调节亮度或电机速度 | 设置频率/占空比，避免过载 |
| 输入检测 | 读取按键、传感器、电位器 | 需要下拉/上拉配置 |

### 串口通信积木

- 初始化串口并设置波特率（常用 9600 / 115200）
- 发送字符串 / 数字给外部 MCU
- 接收外部数据并根据字符串判断执行

---

## 常见问题（FAQ）

| 问题 | 解决方案 |
|-----|---------|
| 上传卡住或报错 | 检查 `blockTool.exe.config` 账号密码、网络连接，重新启动 Mixly |
| 烧录完成设备无反应 | 务必 **重新上电** 或重启设备 |
| 串口接收不到数据 | 检查 TX/RX 是否交叉、波特率是否一致、串口号是否被占用 |
| 语音指令无法识别 | 确认技能已发布并同步词库、固件为最新版本、麦克风/供电正常 |
| 提示"板卡不存在"或"权限不足" | 重新执行一键更新、确认账号权限 |
| 找不到积木指令 | 在"扩展/管理库"启用对应插件 |
| 生成固件提示磁盘空间不足或路径错误 | 确保磁盘空间充足、安装路径避免中文/过长目录 |

---

## 附加资源

| 资源 | 链接 |
|-----|------|
| 官方 Block 文档 | [https://help.aimachip.com/docs/block](https://help.aimachip.com/docs/block) |
| 开发环境搭建 | [https://help.aimachip.com/docs/block/minxly_01](https://help.aimachip.com/docs/block/minxly_01) |
| 串口通信示例 | [https://help.aimachip.com/docs/block/ci-03t_01](https://help.aimachip.com/docs/block/ci-03t_01) |
| CI03T 对接 Block | [https://help.aimachip.com/docs/block/block-1f3a936php1n6](https://help.aimachip.com/docs/block/block-1f3a936php1n6) |
| Mixly 官方手册 | [https://mixly.org/](https://mixly.org/) |
| 智能公元平台 | [https://smartpi.cn/](https://smartpi.cn/) |
