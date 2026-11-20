# DrugAlpha MCP — Innovative Drug Database

English · [简体中文](README.zh-CN.md)

Connect your AI to the **DrugAlpha Innovative Drug Database** for global drug pipelines, clinical evidence, competitive landscapes, overseas sales, company and drug catalysts, epidemiology, guidelines, valuations, overseas morning briefs, treatment costs, patent expiry and listed-company assets. Supports drug R&D, business development and investment research.

**Endpoint: `https://drugalpha.com/mcp` · Read-only access · Analysis by your AI**

**First-time users:** register an account at the [DrugAlpha Innovative Drug Database](https://drugalpha.com/), then connect with browser authorization or a personal key. Already connected? Start querying directly.

[Connection guide](https://drugalpha.com/connect-ai) · [Manage OAuth connections](https://drugalpha.com/oauth/connections) · [Manage personal keys](https://drugalpha.com/oauth/keys)

## Available data

Updated **2026-11-20**. Availability depends on your account, the current tool list and published data coverage. Examples describe queries, not guaranteed coverage of every drug or market.

| Area | What you can query |
| --- | --- |
| Companies and drugs | Covered company names and tickers; standardized drug names, development codes and aliases |
| Pipelines and catalysts | Company/drug pipelines, targets, indications, stages, trial registrations, upcoming events and sources |
| Competitive landscapes | Normalized targets or indications, retaining modality, population, biomarkers and treatment-line filters |
| Clinical evidence | Covered trials by indication **or drug**, including treatment arms, efficacy, safety and sources |
| Guidelines and epidemiology | Recommendations, eligible populations, geography, years and statistical definitions; clinical metric explanations |
| Overseas sales | Published annual sales by drug, brand, company, target, geography and fiscal year; historical and multi-drug comparisons |
| Valuation and assets | Company valuations and forecast drug peak sales, A/H industry PS, sector valuations/holdings, pipeline portfolios and platform selections |
| Research and morning briefs | Available announcements and report inputs; both published sections of overseas biopharma morning briefs |
| China treatment costs | Chinese prescribing information, drug prices and a cost-estimation framework with explicit assumptions |
| US treatment costs | DailyMed labels/packages, published annual WAC quotes and server-side cost calculation after regimen and duration confirmation |
| China patent expiry | Covered Chinese patent registrations and expiry information, with source and collection date |
| US patent expiry | FDA Orange/Purple Book records and covered company disclosures; product-specific patent and exclusivity information |
| Stock technical analysis | Available dated analysis and daily selection, watch and alert lists, preserving confirmation states and risk notes |

[Bilingual query guide and examples](QUERY-GUIDE.md). Company valuation uses your saved model first, then platform valuation. A patent's expiry is not the end of all protection for a drug. Technical analysis does not promise future returns.

## Connect your AI

### Ask your AI to configure the connection

> Connect me to DrugAlpha MCP. Read this repository's README.md and INSTALL-AGENT.md, preserve my existing client settings, and let me complete authorization in my browser. Then query the first-line pancreatic cancer competitive landscape to verify the connection.

[Agent installation guide](INSTALL-AGENT.md) · [Download the bilingual connection ZIP](https://github.com/max-nobug/drugalpha-mcp/raw/refs/heads/main/downloads/drugalpha-mcp-v0.2.zip)

### OAuth: WorkBuddy, ChatGPT, Codex and Claude Code

Use a client that supports remote HTTP MCP and DrugAlpha browser authorization. Client entry points depend on version, account and plan; adding this repository does not imply inclusion in any official client marketplace.

- **WorkBuddy:** open the connector settings and add a custom MCP connector. In the previously verified 5.7.7 layout: Experts/Skills/Connectors → Connectors → Custom connectors → Add MCP. Merge only the DrugAlpha entry into existing settings, enable it and complete browser authorization.
- **ChatGPT:** use the app/custom-connection entry available to your account, enter the remote endpoint, authorize in the browser and select DrugAlpha in the conversation. Availability depends on your client and plan.
- **Codex:** in a client supporting plugin marketplaces, add this repository with `codex plugin marketplace add max-nobug/drugalpha-mcp`, then install DrugAlpha and authorize. The optional `codex.toml` is a manual configuration reference; check your client's supported fields before merging it.
- **Claude Code:** use its supported plugin/MCP installation and authentication flow. The Claude plugin is in `plugins/drugalpha-claude`; check the installed client's help for its current commands.

For clients using JSON MCP configuration, adapt this to their supported schema:

```json
{
  "mcpServers": {
    "drugalpha": {
      "type": "http",
      "url": "https://drugalpha.com/mcp",
      "timeout": 60000,
      "disabled": false
    }
  }
}
```

Preserve other services and existing working connections. Refresh the tool list or start a new conversation after ordinary updates; reauthorize only when required. Browser authorization and a successful data query are separate checks.

### Personal key: Alpha 派, AlphaEngine and other key-based clients

Personal keys are available at [Manage personal keys](https://drugalpha.com/oauth/keys). Sign in to your own account, name a key (for example, “Alpha 派” or “AlphaEngine”), create it and copy it directly into your trusted client's credential field. The full key is shown only when created.

| Field | Value |
| --- | --- |
| MCP endpoint | `https://drugalpha.com/mcp` |
| Dedicated Key field | Paste the **key only**, without `Bearer` |
| Manually configured header | Header name `Authorization`; value `Bearer <YOUR_PERSONAL_KEY>` |

Do not add `Bearer` to a dedicated Key field: the client may add that prefix itself. See the [website's illustrated guide](https://drugalpha.com/connect-ai) for Alpha 派 and AlphaEngine. After connecting the skill, add/select it in the conversation as required by the client.

Key validity follows your subscription. Unrevoked keys remain usable after renewal; revoked keys do not recover. Keys and OAuth connections coexist, use the account's data permissions and can be revoked independently. Activity is recorded under the account. Never paste real keys, tokens, passwords or cookies into chats, Issues, examples or public files.

## Treatment costs and patent dates: choose the market

- **China:** retrieve Chinese labels and prices, then use the cost framework with confirmed dose, frequency, duration and price basis. This is distinct from the US server-side calculator.
- **US:** select the specific product and packaging, review label regimens, then confirm indication, dose, schedule and duration (and weight/BSA when needed). Calculation requires verified package pricing from the published annual Texas WAC snapshot. Missing or unverified price bases remain explicit gaps; the AI must not invent prices. Annual WAC is not a real-time transaction price or patient out-of-pocket cost.
- **Patents:** state China or US explicitly. Retain product, patent/exclusivity type, source and date. No matching record does not mean no patent protection exists.

## Excel delivery

Sector valuation and sector holdings workbooks are available through the corresponding download tools when authorized. Industry PS trend/comparison exports retain platform export permissions, including administrator requirements where applicable. Use the current tool list to check access. Overseas sales has no separate MCP Excel-download tool.

A temporary authorized file reference is not a public sharing link. Claim delivery only after actually retrieving or saving the file.

## Evidence, language and use

Ask in Chinese or English; replies default to the language of your question unless you request another language. Name matching depends on covered names and aliases; clarify ambiguous results instead of silently changing the company, drug or population.

Retain sources, dates, units, currencies, fiscal periods, populations and coverage gaps. Missing values are not zero; forecasts are not actuals; pipeline rows are not necessarily distinct drugs. Do not split combined sales disclosures or double-count overlapping geographies. Read announcement text before claiming to have reviewed it. Complete DCF generation, platform AI generation and business-data writes are outside this connector's current scope.

Use the service under DrugAlpha's terms for legitimate research. Bulk database copying, mirroring and resale are prohibited. Actual external fetches may be throttled to protect upstream sites; local/cache reads are distinct from external requests. Account/subscription permissions and quotas still apply.

Report client/version, reproduction steps and redacted errors in [Issues](https://github.com/max-nobug/drugalpha-mcp/issues). This repository distributes public connection materials and client plugins, not the DrugAlpha server. Registry metadata is versioned separately; see [Registry notes](REGISTRY.md).
