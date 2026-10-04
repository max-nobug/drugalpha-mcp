# MCP Registry 登记

本仓库的 server.json 只登记远程服务元数据，不分发 DrugAlpha 服务端代码。

- 登记名称：io.github.max-nobug/drugalpha-mcp
- 服务地址：https://drugalpha.com/mcp
- 功能：公司/药物识别、已发布催化剂查询
- 访问要求：用户在 DrugAlpha 网站登录并完成 OAuth 授权

Registry 是 MCP 生态的元数据登记处，不代表通过 OpenAI 官方审核，也不保证被各客户端内置市场收录。

## 维护者发布

使用官方 mcp-publisher 工具，在本仓库目录运行：

```sh
mcp-publisher login github
mcp-publisher validate
mcp-publisher publish
```

在 GitHub 官方页面用 max-nobug 账号完成授权。不要把令牌、认证缓存或私钥提交到仓库。

发布后从 Registry API 核对实际结果：

https://registry.modelcontextprotocol.io/v0.1/servers?search=io.github.max-nobug/drugalpha-mcp

server.json 的版本是登记元数据版本，与各客户端安装包版本分别维护。服务描述或安装元数据变化时递增版本并重新发布；数据内容更新不需要每次登记。当前是否已登记以 Registry API 返回为准。

官方文档：https://modelcontextprotocol.io/registry/remote-servers
