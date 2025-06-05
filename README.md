# apifox-mcp MCP 服务器

这是一个按 Stdio 实现 Model Context Protocol 的服务器，用于访问 Apifox API 数据。

此 TypeScript 实现的 MCP 服务器提供了与 Apifox 平台交互的功能，允许 AI 助手直接获取 API 接口定义信息。

## 功能特性

### 工具

- `get_api_endpoint_info` - 获取 Apifox 的接口定义信息
  - 接收 projectId 和 endpointId 作为必需参数
  - 返回包括请求头、请求方式、请求参数、响应参数、响应头等详细 API 定义

## 开发

安装依赖:

```bash
npm install
```

构建服务器:

```bash
npm run build
```

开发模式(自动重新构建):

```bash
npm run watch
```

启动服务器:

```bash
npm run start
```

## 安装配置

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

### 调试

由于 MCP 服务器通过标准输入输出(stdio)通信，调试可能比较困难。我们推荐使用[MCP Inspector](https://github.com/modelcontextprotocol/inspector)，可通过以下命令启动:

```bash
npm run inspector
```

Inspector 将提供一个 URL，可在浏览器中访问调试工具。
