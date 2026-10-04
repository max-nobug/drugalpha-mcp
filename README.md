# DrugAlpha MCP 接入包 · v0.1

让你自己的 AI 查询 DrugAlpha 已发布投研数据。服务运行在线上，无需部署本地服务器，不消耗 DrugAlpha AI API。

- 服务地址：https://drugalpha.com/mcp
- 协议：Streamable HTTP；授权：OAuth + PKCE
- 账号：拥有 DrugAlpha 正式内容阅读权限的账号
- 本版本功能：公司/药物识别、按公司或已确认关联药物查询催化剂
- 已验证：Codex 桌面内置 CLI 0.159.2，浏览器授权与真实查询（2026-10-04）
- 已验证：WorkBuddy 5.5.6，浏览器授权、药物识别与催化剂真实查询（2026-10-04，用户实测确认）
- Claude Code：尚未完成独立实测。已验证范围不代表所有版本、系统和客户端均兼容。

## 让 AI 帮你配置

将本文件夹交给你的 Agent，发送：“请阅读 INSTALL-AGENT.md，按步骤帮我连接 DrugAlpha MCP。”

也可以直接把下面这段话交给 Agent：

> 请读取公共仓库 https://github.com/max-nobug/drugalpha-mcp 中的 README.md 和 INSTALL-AGENT.md，按照指引帮我配置 DrugAlpha MCP。保留已有客户端设置，由我在浏览器完成登录授权，最后验证真实查询是否成功。

## 获取接入包

- 公共仓库：https://github.com/max-nobug/drugalpha-mcp
- ZIP 下载：https://github.com/max-nobug/drugalpha-mcp/raw/refs/heads/main/downloads/drugalpha-mcp-v0.1.zip
- Git 拉取：`git clone https://github.com/max-nobug/drugalpha-mcp.git`

无需克隆投研平台代码或安装服务端。下载 ZIP 后解压，或直接让 Agent 阅读仓库中的安装指引即可。

## WorkBuddy 配置

服务端已开放标准 OAuth 动态注册，无需使用 Codex 的客户端身份或固定回调端口。WorkBuddy 5.5.6 已完成真实查询验证；以下为客户端手动配置示例。市场连接器包使用另一种配置格式，不要混用。

```json
{"mcpServers":{"drugalpha":{"type":"http","url":"https://drugalpha.com/mcp"}}}
```

请让 Agent 确认 WorkBuddy 实际生效的 MCP 配置位置，备份后只合并 drugalpha 项，保留其他连接。然后在 WorkBuddy 中发起连接，由用户自行完成浏览器登录授权。看到工具列表并真实执行公司识别、催化剂查询后，才能报告连接成功；如失败，反馈脱敏后的错误提示，不发送令牌或完整回调链接。

## Codex 手动配置

1. 将 codex.toml 中的配置合并到 Codex 用户配置，通常是 ~/.codex/config.toml。不要覆盖现有文件；同名服务存在时先核对。
2. 使用支持预注册 OAuth 客户端的 Codex。运行 codex mcp add --help，确认存在 --oauth-client-id。旧版命令行可能不支持，桌面版内置 CLI 与系统 PATH 中版本也可能不同。
3. 使用同一个 Codex 可执行文件运行：codex mcp login drugalpha。
4. 在浏览器登录 DrugAlpha，点击“允许连接”。密码只在 DrugAlpha 网站输入，不发给 AI。
5. 浏览器跳至 http://127.0.0.1:8900/callback 是本机 Codex 接收授权结果，MCP 服务仍在线上。看到 Authentication complete 且命令行确认成功后，重新加载 MCP 或打开新的 Codex 会话。

8900 端口须空闲；发生占用不要任意修改回调地址，先关闭先前的授权窗口/进程或联系平台。远程开发机、容器和跨设备浏览器尚未验证。

## 试问

- 恒瑞医药未来 12 个月有哪些催化剂？请注明时间精度和数据来源。
- 查找某药物，再列出与它已确认关联的后续催化剂。

Agent 应先解析公司/药物，再使用本次返回的标识查询，不编造标识。结果按正式发布范围呈现；没有查询结果不等于没有相关事件。年度、季度等区间不可伪装成确定日期，研究预期不可写成事实。

## 管理连接

https://drugalpha.com/oauth/connections 可查看并撤销授权。退出网站不会撤销 Agent 授权。初期已开放模块不限业务额度，但 Agent 自身的模型费用由对应服务计算。

## 功能边界

临床数据对比、竞争格局、估值/峰值销售、疾病知识库、晨报、DCF、治疗费用及股票技术分析尚未接入本版本。

本包只包含公开配置和指引，不含密钥或服务端代码。各平台市场条目尚未发布，不影响已验证客户端通过此接入包连接。

如需反馈问题，请在公共仓库的 Issues 中描述客户端版本、操作步骤及脱敏后的错误提示。不要上传密码、令牌、Cookie、完整客户端配置或授权回调链接。
