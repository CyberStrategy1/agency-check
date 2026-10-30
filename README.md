# Agency Check

**A hosted MCP server that checks what your AI agent is about to do before it acts.**

A second look before your AI agent buys, sends, books, shares, signs up, or connects an app.

- Website: https://agency-check.app
- MCP endpoint (Streamable HTTP): `https://agency-check.app/mcp`
- Official MCP Registry: `io.github.CyberStrategy1/agency-check` — https://registry.modelcontextprotocol.io/v0/servers?search=agency-check

This repository holds documentation only. Agency Check is a hosted service; there is nothing to install or self-host.

## Tools

| Tool | What it does |
|---|---|
| `agency_check` | Check a planned agent action before it runs (counts as one check). |
| `describe_ruleset` | Describe the ruleset Agency Check uses (free). |
| `explain_rule` | Explain a single rule by its ID, e.g. `AC-R-001` (free). |
| `get_receipt` | Fetch a signed receipt for a past check by receipt ID (free). |

## Connect

Sign-in is OAuth (Google). Your MCP client opens a browser window the first time it connects. See [docs/connect.md](docs/connect.md) for Claude, Cursor, ChatGPT, VS Code, and generic clients.

Quick Cursor `mcp.json`:

```json
{
  "mcpServers": {
    "agency-check": { "url": "https://agency-check.app/mcp" }
  }
}
```

## Pricing

- **Free:** 20 checks a month, no card. Sign in with Google.
- **Agency Check Pro:** $9/month or $79/year. Upgrade from https://agency-check.app/account.
- Only `agency_check` calls count; `describe_ruleset`, `explain_rule`, `get_receipt`, and follow-ups answering a Clarify question are free. Allowances reset on the 1st of each month (UTC).
- Details: https://agency-check.app/pricing

## Links

- Privacy: https://agency-check.app/privacy
- Terms: https://agency-check.app/terms
- Support: https://agency-check.app/support

Made by Cyber Strategy Institute. Docs licensed CC BY 4.0.
