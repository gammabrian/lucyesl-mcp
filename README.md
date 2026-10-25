<img src="logo.png" alt="LucyESL" width="80" height="80" align="right">

# LucyESL MCP server

Live English-teaching jobs in South Korea, with the salary, disclosure and by-region
figures [LucyESL](https://lucyesl.com) computes from the same adverts. A remote MCP
server: read-only, no account and no key.

```
https://lucyesl.com/mcp
```

This repository holds the connection settings and the documentation. The server itself
runs at the address above; its source is not published here. Full terms, limits and the
JSON views of the same data: [lucyesl.com/developers](https://lucyesl.com/developers).

## Connect

| Client | How |
|---|---|
| Claude (claude.ai, Desktop, mobile) | LucyESL is in Claude's connector directory: search for it under Connectors. |
| Claude Code | `claude mcp add --transport http lucyesl https://lucyesl.com/mcp`, or `/plugin marketplace add gammabrian/lucyesl-mcp` then `/plugin install lucyesl@lucyesl` |
| ChatGPT | Plugins → Add → Add custom MCP server, with the URL above. |
| Gemini CLI | `gemini extensions install https://github.com/gammabrian/lucyesl-mcp` |
| VS Code | `code --add-mcp '{"name":"lucyesl","type":"http","url":"https://lucyesl.com/mcp"}'` |
| Codex CLI | In `~/.codex/config.toml`: `[mcp_servers.lucyesl]` then `url = "https://lucyesl.com/mcp"` |
| Cursor | In `~/.cursor/mcp.json`: `{"mcpServers": {"lucyesl": {"url": "https://lucyesl.com/mcp"}}}` |
| Cline | See [llms-install.md](llms-install.md). |
| Any other client | Streamable HTTP at the URL above, no authentication. |

## Tools

<!-- tools:start -->
| Tool | What it does |
|---|---|
| `search` | Search live English-teaching jobs in South Korea on LucyESL with a plain-language query. Words for a region, student age, housing, schedule, visa or direct hire are read as filters. Returns up to 20 matches, each an id, a title with the employer, and the listing URL. |
| `fetch` | Fetch one live LucyESL job listing by its id as a document with its title, its URL and a plain-text body giving the employer, pay, hours, housing, visas, benefits, dates and the facts the advert left unstated. An id that has closed or expired returns an error naming it. |
| `search_jobs` | Filter the live LucyESL board of English-teaching jobs in South Korea: region, student age, housing, visa, schedule, contract, setting, direct hire, minimum salary, free text. Returns the number that match and a page of structured records; pay in KRW per month unless stated otherwise; null means the advert did not say. |
| `get_job` | Get one live LucyESL job listing by its numeric id as a structured record: employer and employer type, region, pay in KRW, teaching and on-site hours, housing, visas, benefits, contract length, start date, dates, and the facts the advert left unstated (null means not stated). An id that has closed or expired returns an error naming it. |
| `salary_stats` | English-teacher salary statistics for South Korea computed from the live listings: median, quartiles, by region, by employer type, effective pay per teaching hour, disclosure rates, housing. Each median comes with the number of adverts behind it. CC BY 4.0. |
| `disclosure_stats` | How many live Korean ESL job adverts state the salary, hours, severance, pension, insurance, airfare, vacation and split shifts: for each, the number that state it, out of how many, and the percentage. CC BY 4.0. |
| `market_stats` | Live English-teaching job adverts in South Korea counted by region: how many in each, direct hire against recruiters, how many state total on-site hours, and the median advertised salary where the sample allows. Counts of adverts, not of employers. CC BY 4.0. |
<!-- tools:end -->

Every tool is read-only and says so in its annotations.

## Things to ask

- "Find kindergarten English teaching jobs in Seoul with housing."
- "Which direct-hire jobs in Busan pay at least ₩2.6 million a month?"
- "What is the median advertised salary for English teachers in Korea, by region?"
- "How many Korean ESL job adverts state the teaching hours, severance and health insurance?"
- "Where in Korea are most of the English teaching jobs right now?"

## What the data is

- **Listing records are LucyESL's extracted facts**: title, employer, region, pay, hours,
  visas, housing, benefits, dates, and the facts the advert left unstated. Never the
  advert's text, a contact route or a source board's URL. `null` always means the advert
  did not state it, never zero.
- **Most listings are copied from other public job boards** and are marked
  `"source": "copied"`; LucyESL has not verified those employers. A listing posted on
  LucyESL by the employer is `"first_party"`, and `"verified_employer": true` means its
  Korean business registration and contact were checked.
- **The statistics are CC BY 4.0.** Credit "LucyESL, https://lucyesl.com" and link the
  page they come from.
- **600 requests an hour per address**, then HTTP 429 with a `Retry-After`.
- **No position in an answer is paid for.**

## Discovery

- Protocol: the stateless 2026-07-28 revision, and 2025-03-26 to 2025-11-25 with `initialize`
- Official MCP Registry: `com.lucyesl/jobs`
- MCP Server Card: https://lucyesl.com/mcp/server-card
- AI Catalog: https://lucyesl.com/.well-known/ai-catalog.json

## Contact

hello@lucyesl.com. Security reports: https://lucyesl.com/.well-known/security.txt.
[Privacy](https://lucyesl.com/privacy) · [Terms](https://lucyesl.com/terms)

The files in this repository are MIT-licensed.
