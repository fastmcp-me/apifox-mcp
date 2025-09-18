[![Add to Cursor](https://fastmcp.me/badges/cursor_dark.svg)](https://fastmcp.me/MCP/Details/1086/apifox)
[![Add to VS Code](https://fastmcp.me/badges/vscode_dark.svg)](https://fastmcp.me/MCP/Details/1086/apifox)
[![Add to Claude](https://fastmcp.me/badges/claude_dark.svg)](https://fastmcp.me/MCP/Details/1086/apifox)
[![Add to ChatGPT](https://fastmcp.me/badges/chatgpt_dark.svg)](https://fastmcp.me/MCP/Details/1086/apifox)
[![Add to Codex](https://fastmcp.me/badges/codex_dark.svg)](https://fastmcp.me/MCP/Details/1086/apifox)
[![Add to Gemini](https://fastmcp.me/badges/gemini_dark.svg)](https://fastmcp.me/MCP/Details/1086/apifox)

# Apifox MCP Server

[![npm version](https://img.shields.io/npm/v/@juzi965/apifox-mcp-server.svg)](https://www.npmjs.com/package/@juzi965/apifox-mcp-server)

一个基于 Stdio 实现的模型上下文协议 (Model Context Protocol) 服务器，旨在无缝桥接 AI 助手与 Apifox 平台的 API 数据。

允许 AI 助手通过标准化的协议直接、实时地获取和理解您在 Apifox 项目中定义的 API 接口详情，从而显著提升开发效率和代码生成质量。

## ✨ 功能特性

### 工具

- `get_api_endpoint_info` - 获取 Apifox 的接口定义信息
  - 请求参数
    - `projectId`: Apifox 项目的唯一标识符。
    - `endpointId`: 目标 API 端点的唯一标识符。
  - 返回数据
    - 一个结构化的 JSON 对象，包含完整的 API 规约 (Specification)，例如：
      - HTTP 请求方法 (Method)
      - 求头 (Request Headers)
      - 路径、查询及请求体参数 (Parameters: Path, Query, Body)
      - 响应体结构 (Response Body Schema)
      - 响应头 (Response Headers)

## 🚀 安装配置

要在 Cursor 中使用此服务器，请添加以下服务器配置:

```json
{
  "mcpServers": {
    "Apifox-MCP": {
      "command": "npx",
      "args": ["@juzi965/apifox-mcp-server"],
      "env": {
        "APIFOX_AUTH": "..."
      }
    }
  }
}
```

### 环境变量

该服务器需要以下环境变量:

- `APIFOX_AUTH`: Apifox 的认证令牌

## 💡 使用方法

<img width="337" alt="image" src="https://github.com/user-attachments/assets/9688b499-7774-4f06-bfa0-d4f80412156e" />

复制协作链接到 Cursor 中，让它帮你完成

- 入参的 TS 类型定义
- 出参的 TS 类型定义
- 接口调用方法的定义
  <img width="1264" alt="Xnip2025-06-19_14-30-13" src="https://github.com/user-attachments/assets/801002bb-c529-47e7-b52c-a6f909bbcd10" />

## 🛠️ 调试

由于 MCP 服务器通过标准输入输出(stdio)通信，调试可能比较困难。我们推荐使用[MCP Inspector](https://github.com/modelcontextprotocol/inspector)，可通过以下命令启动:

```bash
npm run inspector
```

Inspector 将提供一个 URL，可在浏览器中访问调试工具。
