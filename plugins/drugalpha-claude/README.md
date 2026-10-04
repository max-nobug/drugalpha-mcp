# DrugAlpha Claude Code 插件 · 0.1.1

从自建 GitHub 目录安装：

```sh
claude plugin marketplace add max-nobug/drugalpha-mcp
claude plugin install drugalpha@drugalpha
```

重启会话，在 /mcp 中核对插件提供的 DrugAlpha 服务并在浏览器登录授权。已有手动连接时先核对，避免重复连接。

当前支持公司/药物识别与已发布催化剂查询，只读。Agent 自身模型承担分析费用，不调用 DrugAlpha AI API。此前手动 MCP 已验证授权与连接，插件模型问答仍待验证。不代表 Anthropic 官方目录审核通过。

撤销连接：https://drugalpha.com/oauth/connections
客服：zmxx00@126.com。不要发送密码、令牌或完整回调链接。
