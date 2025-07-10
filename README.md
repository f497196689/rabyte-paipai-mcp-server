# 什么是 Rabyte PaiPai MCP 服务

---
PaiPai 是讯兔科技自研的投研垂类模型，目前主要有文本问答(支持深度推理模式,真人研究员思维链+领先推理模型+全量投研语料)、定量分析模式(一键Excel拉数:将闹钟的策略、分析需求转化为金融数据查询代码并获取到精准数据结果)、个股相关Agent(个股一页纸、个股调研问题大纲)等能力。 Rabyte PaiPai MCP 就是基于这些能力实现的一个基于SSE协议的MCP服务。


# Tools 介绍

| 工具名称 | 描述 | 输入参数 | 必填参数 |
|---------|------|---------|---------|
| qa-text | PaiPai 文本问答,用于查询各类金融投资相关问题 | `isWebSearch`: boolean(是否开启联网搜索)<br>`question`: string(问题) | `question` |
| stock-comment-info | 获取某个股票的点评信息 | `code`: string(股票编码) | `code` |
| quantity-analysis | PaiPai 定量分析, 在行情/指数/财务/估值/基金等数据库中进行类Excel提数与分析 | `question`: string(问题) | `question` |
| stock-one-page | PaiPai 个股/公司一页纸，可以总结个股/公司的核心逻辑 | `stockCode`: string(股票编码)<br>`stockName`: string(股票名称) | `stockName`, `stockCode` |
| stock-survey-outline | PaiPai 个股/公司调研问题大纲，可以生成个股/公司的调用QA List | `stockCode`: string(股票编码)<br>`stockName`: string(股票名称) | `stockName`, `stockCode` |




# 如何使用 Rabyte PaiPai MCP 服务
支持运行 MCP 协议的客户端，如Cursor、Cherry Studio等。  
联系客户经理获取您的API密钥（微信: `huqi83928421`)


## 在Cherry Studio中使用

Cherry Studio 提供了MCP功能，Cherry Studio 将作为MCP服务客户端使用MCP服务，在Cherry Studio 中通过简单的配置就可以完成MCP服务的接入。  
操作路径：【设置】->【MCP 服务器】->【添加服务器】 -> 【从JSON导入】。

## 参考JSON配置
```json
{
  "mcpServers": {
    "rabyte-paipai-mcp-sse": {
      "name": "rabyte-paipai-mcp-sse",
      "type": "sse",
      "description": "",
      "isActive": true,
      "timeout": "300",
      "baseUrl": "https://test-mcp-server.rabyte.cn/paipai/sse",
      "headers": {
        "api-key": "YOUR API Key"
      }
    }
  }
}

```


