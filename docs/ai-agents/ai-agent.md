# 智能体

## 入门

### 1. 登录智能公元平台

登录到智能公元平台 [https://smartpi.cn/](https://smartpi.cn/)，选择左侧菜单 **"智能体" → "配置"**，点击 **"体验版智能体"** 按钮。

### 2. 绑定智能体

按照弹出窗口里的提示，打开 **"智能公元"微信小程序** 进入到设备详情页面，点击 **"AI智能体"** 菜单，扫描二维码绑定智能体。

### 3. 开始对话

绑定成功后，就可以和设备进行交流了。

---

## 智能体接入 API

智能体支持三种接入方式，适用于不同的应用场景：

| 接入方式 | 协议 | 适用场景 |
|---------|------|---------|
| 大模型服务 | HTTP SSE | 自研大模型服务，文本问答 |
| 完整对话服务 | WebSocket | 双向流式语音对话 |
| 大模型+TTS服务 | WebSocket | 文本输入、语音输出 |

---

## 大模型服务参考 API

适用于接入自研大模型服务的场景。

### 配置说明

- **ASR 服务**：自动语音识别，可选"默认"或"自定义"
- **大模型服务**：
  - **连接方式**：默认为 SSE (HTTP)，服务器发送事件推送实时数据
  - **请求地址**：填写大模型服务的请求 URL
  - **流式**：支持流式返回结果，逐步返回而非一次性返回
  - **附加参数**：可添加额外参数，将携带在请求体中
- **TTS 服务**：文本转语音，可选"默认"或自定义外部服务

### 接口说明

- **请求方式**：`POST`
- **URL 示例**：`https://your-domain/api/v1/chat`
- **Header**：`Content-Type: application/json`

**请求体示例**：

```json
{
  "deviceId": "JX_A7T_7C3E821CB729",
  "question": "你是谁？",
  "stream": true
}
```

**返回示例（SSE 流式）**：

```
data:{"code": 0,"message": "","data": {"answer": "我","id": "12341231"}}
data:{"code": 0,"message": "","data": {"answer": "是","id": "12341231"}}
data:{"code": 0,"message": "","data": {"answer": "小智","id": "12341231"}}
data:{"code": 0,"message": "","data": {"answer": "有什么","id": "12341231"}}
data:{"code": 0,"message": "","data": {"answer": "可以","id": "12341231"}}
data:{"code": 0,"message": "","data": {"answer": "帮您","id": "12341231"}}
data:"[DONE]"
```

---

## 完整对话服务参考 API

适用于双向流式语音对话场景，支持实时语音输入和输出。

### 配置说明

平台支持接入双向流式语音对话 WebSocket OpenAPI。输入音频格式和输出音频格式根据可选项进行配置，附加参数将在 WebSocket 建连时携带在请求地址里。

### 接口说明

- **URL 示例**：`wss://your-domain/api/v1/chat?deviceId=12345678`

### 上行事件

#### 流式上传音频片段

```json
{
  "id": "event_id",
  "event_type": "input_audio_buffer.append",
  "data": {
    "delta": "base64EncodedAudioDelta"
  }
}
```

#### 提交音频

```json
{
  "id": "event_id",
  "event_type": "input_audio_buffer.complete"
}
```

#### 清除缓冲区音频

```json
{
  "id": "event_id",
  "event_type": "input_audio_buffer.clear"
}
```

#### 打断智能体输出

```json
{
  "id": "event_id",
  "event_type": "conversation.chat.cancel"
}
```

### 下行事件

#### 对话连接成功

```json
{
  "id": "7446668538246561xxxx",
  "event_type": "chat.created",
  "detail": {
    "logid": "20241210152726467C48D89D6DB2F3***"
  }
}
```

#### 对话开始

```json
{
  "id": "744666853824656xxx",
  "event_type": "conversation.chat.created",
  "data": {
    "id": "123",
    "conversation_id": "123"
  },
  "detail": {
    "logid": "20241210152726467C48D89D6DB2F3***"
  }
}
```

#### 增量消息

```json
{
  "id": "event_1",
  "event_type": "conversation.message.delta",
  "data": {
    "id": "msg_006",
    "conversation_id": "123",
    "type": "answer",
    "content": "你好你好"
  },
  "detail": {
    "logid": "20241210152726467C48D89D6DB2F3***"
  }
}
```

#### 增量语音

```json
{
  "id": "event_1",
  "event_type": "conversation.audio.delta",
  "data": {
    "id": "msg_006",
    "type": "answer",
    "content": "base64audio",
    "conversation_id": "123"
  },
  "detail": {
    "logid": "20241210152726467C48D89D6DB2F3***"
  }
}
```

#### 消息完成

```json
{
  "id": "event_1",
  "event_type": "conversation.message.completed",
  "data": {
    "id": "msg_002",
    "conversation_id": "123"
  },
  "detail": {
    "logid": "20241210152726467C48D89D6DB2F3***"
  }
}
```

#### 语音回复完成

```json
{
  "id": "event_1",
  "event_type": "conversation.audio.completed",
  "data": {
    "id": "msg_002",
    "conversation_id": "123"
  },
  "detail": {
    "logid": "20241210152726467C48D89D6DB2F3***"
  }
}
```

---

## 大模型和 TTS 服务参考 API

适用于文本输入、语音输出的场景。

### 接口说明

- **URL 示例**：`wss://your-domain/api/v1/chat?deviceId=12345678`

### 上行事件

#### 提交文本

```json
{
  "id": "event_id",
  "event_type": "input_text",
  "deviceId": "12345678",
  "question": "你是谁？",
  "stream": true
}
```

#### 打断智能体输出

```json
{
  "id": "event_id",
  "event_type": "conversation.chat.cancel"
}
```

### 下行事件

下行事件与完整对话服务相同，包括 `conversation.message.delta`、`conversation.audio.delta`、`conversation.message.completed`、`conversation.audio.completed` 等。

---

## 智能体控制设备

智能体支持通过 MCP（模型上下文协议）控制设备，也支持对接 coze 插件。

---

## MCP 设备控制

模型上下文协议（Model Context Protocol, MCP）可帮助大模型使用外部工具，实现与大模型交互过程中控制设备的能力。

### 配置步骤

#### 1. 配置小程序控件

根据您希望设备具备的能力，配置小程序控件。例如：

- 配置滑块控件，用来调节灯光亮度
- 配置开关控件，用来控制灯开关
- 配置按钮控件，用来控制加湿器开关
- 配置开关控件，用来控制窗帘开关

#### 2. 生成 MCP 工具

切换到 **"MCP工具"** 菜单，点击 **"刷新"** 按钮，系统会根据先前配置的小程序控件，生成对应的 MCP 工具。

#### 3. 配置工具信息

工具分为两种类型：**控制** 和 **查询**。每个工具需要填写：

- **工具名称**：确保含义清晰
- **工具描述**：帮助大模型更好地理解工具用途

#### 4. 发布 MCP 工具

版本发布前，请确认勾选 ✔ **"发布MCP工具"**。

#### 5. 烧录固件并验证

将生成好的固件烧录到设备中，使用平台提供的 **"体验版智能体"**，即可在与设备对话的过程中，通过 MCP 控制设备。

---

## coze 插件对接

我们在 coze 的商店里上架了示例固件对应的插件，您可以通过关键词 **"智能公元IOT插件"** 搜索找到。

如果你想做自己的插件，以下教程将告诉您怎么通过智能公元平台制作 coze 插件。

### 一、生成插件

1. 在智能公元平台版本详情页面里，选中 **"MCP工具"** 菜单，点击 **"预览"** 按钮
2. 在弹出的工具预览窗口中，点击 **"下载插件"** 按钮，保存下载下来的 `mcp_tool.yaml` 文件
3. 打开 coze 平台 [https://www.coze.cn/](https://www.coze.cn/)，在 **"工作空间" → "资源库"**，添加插件
4. 在新建插件窗口里，点击右上角的 **"导入"** 按钮
5. 上传保存的 `mcp_tool.yaml` 文件
6. 点击 **"下一步"**，然后点击 **"确认"**
7. 在资源库的列表里会显示刚添加的插件
8. 将工具列表里的所有工具都设置为 **"启用"** 状态
9. 进行试运行，试运行通过后，状态便会变更为"通过"
   - 试运行时需要输入对应参数的参数值
   - 其中 `token` 固定填写为 `Bearer test`
   - 其他参数可随便填

### 二、配置插件

1. 打开对话流的编辑界面，选中 **"开始"** 节点，配置输入变量 `token` 和 `deviceKey`
2. 选中大模型节点，**注意要把大模型的深度思考开关关闭**，不然会导致每次对话耗时太长
3. 在 **"技能"** 栏里添加插件
4. 在 **"输入"** 栏里引用"开始"节点的变量 `token` 和 `deviceKey`
5. 在 **"用户提示词"** 栏填写变量 `token` 和 `deviceKey`
6. 在结束节点里设置打开 **"流式输出"** 开关
7. 最后将编辑好的对话流发布

