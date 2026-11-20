# Agent installation guide

English · [简体中文](INSTALL-AGENT.zh-CN.md)

Connect to `https://drugalpha.com/mcp`; do not install or run the DrugAlpha server. See [README](README.md) and [query guide](QUERY-GUIDE.md).

For a first-time user without an account, first point them to the [DrugAlpha Innovative Drug Database](https://drugalpha.com/) to register. Existing account holders can sign in; already connected users can query directly. Do not send users through registration or reauthorization on every query.

1. Identify the user's actual client and supported connection method. Reuse an existing working DrugAlpha connection; do not add duplicates.
2. Use the client's supported remote HTTP MCP/plugin entry. WorkBuddy's previously verified 5.7.7 route is Experts/Skills/Connectors → Connectors → Custom connectors → Add MCP. ChatGPT uses its available app/custom-connection entry; Codex and Claude Code use their installed version's plugin/MCP and authentication support.
3. If editing configuration, back it up and merge only the DrugAlpha entry. Preserve other services, models and settings. Check supported fields before using `codex.toml`; do not silently change callback settings.
4. For OAuth, let the user sign in and consent on the DrugAlpha browser page. Do not request passwords, cookies, tokens or complete callback URLs, or consent on their behalf.
5. For a personal key, direct the user to [key management](https://drugalpha.com/oauth/keys) to create and paste it directly into trusted credential settings. A dedicated Key field takes the bare key; a manually configured `Authorization` header takes `Bearer <YOUR_PERSONAL_KEY>`. Never put real keys in chats, command history, shared files, screenshots or packages. Keys are available now and follow the account subscription; independent revocation does not affect OAuth.
6. Refresh tools and perform one read-only query on the user's chosen subject (default: first-line pancreatic cancer competitive landscape). Report connection status and actual query status separately. Browser authorization alone does not prove data access. Describe failures with redacted errors; do not report success without a successful query.

Preserve a working OAuth connection when adding key support. Ordinary tool/data/permission updates usually require only a refresh or new conversation, not reauthorization. Availability varies by client version and account; do not claim compatibility from HTTP support alone.

Answer in the user's language unless requested otherwise. Discover current tool schemas and use identifiers from current results. Do not expose credentials or internal identifiers in final answers. Manage OAuth connections at [My connections](https://drugalpha.com/oauth/connections).
