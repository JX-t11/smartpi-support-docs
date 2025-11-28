
# 智能体

## 入门
1. 登录智能公元平台 → “智能体 → 配置”。
2. 扫码绑定体验版智能体并选择控制设备。
3. 在小程序中测试问答/控制，确认基本链路畅通。

> TODO: auto_get/downloaded_aimachip/docs/agent/agent-1glq5lget6s8g.md 的界面截图。

## 接入概览
- 适用场景：自研大模型服务、双向流式语音、文本+TTS 服务。
- 架构：设备 ↔ 智能体服务 ↔ 外部 API/MCP 工具。
- 数据流：语音输入 → ASR → 大模型 → TTS → 设备指令。

## HTTP 大模型服务参考 API
- 配置：ASR（默认或自定义）、LLM（SSE/HTTP Endpoint、Token、流式设置）、TTS（默认或外部服务）。
- 接口：`POST /v1/agent/http-chat`，Header 包含 `Content-Type: application/json` 与 `Authorization`。
- 请求体字段：`deviceId`、`question`、`stream`、`context` 等。
- 返回：SSE `data: {"answer": "..."}`，`[DONE]` 结束。

> TODO: auto_get/downloaded_aimachip/docs/agent/agent-1gp190h4ceuro.md 的请求示例与返回日志。

## 完整对话服务（双向流式 WebSocket）
- URL：`wss://.../agent/stream?deviceId=...`。
- 事件：`chat.created`、`conversation.chat.created`、`conversation.message.delta`、`conversation.audio.delta`、`conversation.chat.completed/failed` 等。
- 上行：`input_audio_buffer.append/complete/clear`、`conversation.chat.cancel`。
- 建议实现心跳与断线重连。

## 大模型 + TTS 服务（文本 WebSocket）
- 适用文本输入、语音输出场景。
- 上行事件：`input_text`、`conversation.chat.cancel`。
- 下行事件沿用完整对话服务的文本/音频增量与完成/失败通知。

## 智能体控制设备
- 体验版 + MCP：在小程序配置控件 → 生成 MCP 工具 → 大模型调用。
- coze 插件：导入 mcp_tool.yaml，在对话流中配置 token/deviceKey，绑定插件节点。

## MCP 设备控制步骤
1. 小程序中配置控件并刷新生成工具。
2. 设置工具名称、描述、权限类型。
3. 发布工具、烧录固件并在体验版智能体中验证。

## coze 插件对接
1. 下载 mcp_tool.yaml 并导入 coze 工作空间。
2. 配置变量（token/deviceKey），在对话流中启用插件。
3. 试运行验证，确保日志返回 200。

> TODO: auto_get/downloaded_aimachip/docs/agent/agent-1gp1hsejc96fk.md、agent-1gp1hsm0obadv.md 的截图与流程图。

