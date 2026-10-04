# 给安装 Agent 的指引

目标：帮助用户连接 https://drugalpha.com/mcp，不安装或运行 DrugAlpha 服务端。

1. 先识别客户端及实际使用的版本。当前仅 Codex 0.159.2 完成实测。WorkBuddy 可按 README 的“接入验证”尝试 HTTP + OAuth 自动注册，不复用 Codex 客户端身份或固定端口；先识别实际配置入口，备份并仅合并 drugalpha 项，然后由用户在客户端发起授权，按第 5～8 步的验证原则检查。以下第 2～4 步只适用于 Codex。Claude Code 仍待独立实测，不宣称所有客户端兼容。
2. Codex：检查实际可执行文件的 mcp add --help 是否支持 --oauth-client-id；不支持时告诉用户需要兼容版本，不要擅自升级或覆盖系统安装。
3. 找到客户端配置后，仅检查 drugalpha 相关配置。先备份，再合并随包 codex.toml。保留其他服务器、模型及用户设置；如同名配置有冲突，先展示该服务的差异再询问用户。不输出其他配置中的密钥。
4. 核对固定本地回调端口 8900 可用；不要修改服务端要求的 client_id、回调路径或端口。
5. 运行同一版本的 codex mcp login drugalpha，让用户在浏览器自行登录及同意。不要收集密码、Cookie 或令牌，不自动点击授权，不要求用户粘贴授权回调 URL。
6. 浏览器显示成功后，仍需核对 CLI 登录成功。连接列表显示“已授权”不等于客户端已完成换码。失败时如实报告原因。
7. 重新加载客户端 MCP 或开启新会话。先调用 resolve_entities 查询用户指定公司（可用恒瑞医药作示例）；再按实际 get_catalysts schema 用本次返回的标识查询。只读，不修改账号、内容或平台数据，不调用 DrugAlpha AI API。
8. 报告登录和查询各自结果，保留来源版本和时间精度；测试失败不能写成安装成功。撤销入口为 https://drugalpha.com/oauth/connections。

服务当前只有实体识别与催化剂查询。不要声称具备其他投研模块或所有 Agent 的兼容性。
