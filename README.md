# DrugAlpha MCP — Innovative Drug Database

English · [简体中文](README.zh-CN.md)

Connect your AI to the **DrugAlpha Innovative Drug Database** for global drug pipelines, clinical evidence, competitive landscapes, overseas sales, company and drug catalysts, epidemiology, guidelines, valuations, overseas morning briefs, treatment costs, patent expiry and listed-company assets. Supports drug R&D, business development and investment research.

**Endpoint: `https://drugalpha.com/mcp` · Read-only access · Analysis by your AI**

**First-time users:** register an account at the [DrugAlpha Innovative Drug Database](https://drugalpha.com/), then connect with browser authorization or a personal key. Already connected? Start querying directly.

[Connection guide](https://drugalpha.com/connect-ai) · [Manage OAuth connections](https://drugalpha.com/oauth/connections) · [Manage personal keys](https://drugalpha.com/oauth/keys)

## Available data

Updated **2026-11-20**. Availability depends on your account, the current tool list and published data coverage. Examples describe queries, not guaranteed coverage of every drug or market.

| Query | What you can obtain | Example question |
| --- | --- | --- |
| Company identification | Find covered Chinese/English company names and tickers; identify the specific listed entity. | Find Hengrui Pharmaceuticals and its ticker. |
| Drug identification and aliases | Resolve standardized drug names, development codes and covered aliases to the same drug. | Resolve SKB264 and show its covered aliases. |
| Company pipelines | Retrieve covered drugs, targets, indications, development stages, trial registrations and progress records for a company. | List Keymed Biosciences’ complete covered pipeline by drug, target and stage. |
| Drug development progress | Look up a drug’s covered indications, stage in each indication and development progress. | Show IBI363 development progress and indication coverage. |
| Company catalysts | Find covered upcoming events for a company and time range, with expected dates, date precision and sources. | Find Hengrui’s catalysts over the next 12 months. |
| Drug catalysts | Find a drug’s covered upcoming clinical, regulatory and other events with expected timing and sources. | Find upcoming catalysts for IBI363. |
| Target competitive landscape | Find competing drugs, companies, indications and stages by normalized target; retain modality such as ADC and supported filters. | Compare TROP2 ADC competitors by drug, company and stage. |
| Indication competitive landscape | Find covered competing drugs and stages by disease, treatment line, population and biomarkers. | Show the first-line EGFR-mutated NSCLC competitive landscape. |
| Clinical evidence by indication | Retrieve covered studies, eligibility, regimens, arms, efficacy, safety and sources for AI comparison. | Compare covered first-line gastric cancer trials by PFS, OS and safety. |
| Clinical evidence by drug | Find covered clinical studies for a drug, distinguishing indications, treatment lines and populations. | Find covered SKB264 clinical evidence by indication and treatment line. |
| Treatment guidelines | Find covered guideline populations, recommended regimens and sources, retaining treatment-line criteria. | Find first-line NSCLC guideline recommendations and sources. |
| Disease epidemiology | Retrieve covered epidemiology with geography, year, source and statistical definitions. | Find NSCLC epidemiology with geography, year and definitions. |
| Clinical metric definitions | Retrieve covered clinical metric definitions and interpretation materials. | Explain PFS, OS and HR. |
| Overseas drug sales | Query published annual sales and trends by drug, brand, company, target, geography and fiscal year; compare drugs. | Find historical aflibercept sales with currency, units and geography. |
| Company valuation | Retrieve company valuations and parameters, prioritizing your saved company model with platform valuation as fallback. | Find Hengrui’s valuation results and parameters. |
| Forecast drug peak sales | Read available forecast peak sales from valuation materials, retaining assumptions and distinguishing forecasts from actual sales. | Find forecast peak sales for Hengrui’s core drugs. |
| Industry PS valuation tracking | Query A/H innovative-drug industry price-to-sales levels, historical trends, distributions and company comparisons. | Compare PS for Hengrui, BeOne and Innovent with industry percentiles. |
| Sector valuation potential | Read published sector valuation conclusions, scenarios and data dates; obtain the valuation workbook when authorized. | Find innovative-drug sector valuation potential and obtain the available workbook. |
| Sector holdings analysis | Read the latest published quarterly holdings summary and definitions; obtain the holdings workbook when authorized. | Find the latest published quarterly sector holdings and obtain the available workbook. |
| Pipeline asset overview | Read company asset overviews and available distributions by stage, target and modality. | Show Betta Pharmaceuticals’ pipeline asset overview. |
| Platform company selections | Retrieve published platform company selections and rationales, retaining publication dates. | Show the platform’s current innovative-drug company selections. |
| Company research inputs | Retrieve available company research inputs such as financial consensus for AI company/report analysis; coverage depends on returned materials. | Get Hengrui research inputs and distinguish actual disclosures from forecasts. |
| Announcement and event research inputs | Find available company announcements and text for an event topic, retaining title, date and source for AI analysis after reading. | Find and read Hengrui drug-approval announcements, then analyze the event. |
| Overseas biopharma morning brief | Read the latest or dated published brief, covering company events and market movements separately; identify missing sections. | Read the latest overseas brief, separating company events and market movements. |
| China prescribing information | Retrieve available Chinese label sections for indications, dosing, specifications and precautions. | Find Chinese camrelizumab prescribing information and dosing. |
| China drug prices | Find available drug-price candidates with manufacturer, strength, packaging, geography, price basis and source. | Find Chinese camrelizumab prices by manufacturer, specification and price basis. |
| China treatment costs | Combine Chinese labels, prices and the estimation framework; confirm dose, frequency, duration and price basis for AI calculation. | Find camrelizumab treatment costs in China; first show dosing and pricing assumptions for confirmation. |
| US labels and packaging | Retrieve available DailyMed product labels, dosing and package candidates; distinguish originators, biosimilars and strengths. | Find US Eylea and Eylea HD labels, dosing and packaging. |
| US annual WAC quotes | Find product quotes from the published annual WAC snapshot, including specification, date and pricing-verification status; not transaction or patient payment prices. | Find Eylea annual US WAC by specification, year and verification status. |
| US treatment costs | Confirm product, indication, dose, frequency and duration; use verified annual WAC package pricing for server calculation. Missing prices remain gaps. | Find Keytruda US course and annual costs; first show regimens and package prices for confirmation. |
| China patent expiry | Find covered Chinese drug patent registrations and expiry information with product, source and collection date. | Find Chinese patent registrations and expiry dates for osimertinib. |
| US patent expiry | Query FDA Orange/Purple Book records and covered company disclosures, distinguishing products, patent expiry and regulatory exclusivity. | Find US aflibercept patent expiry and regulatory exclusivity by product. |
| Stock technical analysis | Read available dated stock analysis, distinguishing confirmed patterns, pending structures and risk notes. | Find Hengrui’s latest technical analysis with confirmed and pending structures. |
| Daily technical lists | Read available daily selection, watch and alert lists, preserving categories and data dates. | Show the latest technical selection, watch and alert lists. |

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
