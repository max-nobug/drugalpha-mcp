# DrugAlpha Codex 插件 · 0.1.1

使用确认后的纯图形品牌 PNG，通过 DrugAlpha 的 GitHub 自建插件目录分发。

尚未上架 OpenAI 官方目录。安装包校验不等于客户端完整实测。

服务：https://drugalpha.com/mcp

浏览器登录 DrugAlpha 并确认授权。当前支持公司/药物识别和已发布催化剂查询，只读；Agent 自身模型承担分析费用。数据来源与时间精度应保留。不要交出密码、令牌或完整授权回调。

包内查询 skill 引导先解析实体再查询，隐藏内部技术字段。市场插件连接可能与手动配置项同时存在；安装前先核对，避免同一服务重复连接，不自动移除旧配置。

版本证据：Codex与WorkBuddy真实查询已验证；Claude CLI仅授权与连接已验证。撤销：https://drugalpha.com/oauth/connections。

插件目录添加：`codex plugin marketplace add max-nobug/drugalpha-mcp`。随后在插件界面或 `/plugins` 中安装 DrugAlpha，由用户完成浏览器授权。已有手动连接时先核对，避免重复连接。

客服及隐私联系邮箱：zmxx00@126.com。请勿发送密码、令牌或完整授权回调。
