# DrugAlpha Claude Code 插件 · 0.2.0

从自建 GitHub 目录安装：

```sh
claude plugin marketplace add max-nobug/drugalpha-mcp
claude plugin install drugalpha@drugalpha
```

重启会话，在 /mcp 中核对插件提供的 DrugAlpha 服务并在浏览器登录授权。已有手动连接时先核对，避免重复连接。

支持当前主站及授权开放的研究查询与Excel，只读。Agent 自身模型承担分析费用，不调用 DrugAlpha AI API。此前手动 MCP 已验证授权与连接，插件模型问答仍待验证。不代表 Anthropic 官方目录审核通过。

撤销连接：https://drugalpha.com/oauth/connections
客服：zmxx00@126.com。不要发送密码、令牌或完整回调链接。

## v0.2 查询范围

接入主站只读资料、原业务结果和板块Excel。具体以当前授权工具列表为准；旧连接需按需重新授权，新增模块客户端问答不以旧催化剂验收代替。用户agent负责研究与计算，平台不调用AI API。完整DCF任务、海外销售及业务写入未开放。

当前上线15查询＋2Excel，独立管线、流行病学、指标解释暂缓。详见仓库README；旧连接按需重新授权。
