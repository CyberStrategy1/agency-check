# Connecting to Agency Check

Endpoint: `https://agency-check.app/mcp` (Streamable HTTP). Auth: OAuth 2.1 with Google sign-in; clients that support remote MCP OAuth will open a browser to sign in on first use.

## Claude (Claude.ai and Claude Desktop)
Settings → Connectors → **Add custom connector**. Name: `Agency Check`, URL: `https://agency-check.app/mcp`. Click **Connect** and sign in with Google.

## Cursor
Add to `~/.cursor/mcp.json` (or `.cursor/mcp.json` in a project):
```json
{
  "mcpServers": {
    "agency-check": { "url": "https://agency-check.app/mcp" }
  }
}
```
Then enable it in Settings → MCP and sign in when prompted.

## ChatGPT
With developer mode enabled: Settings → Apps & Connectors → **Create**. Enter the URL `https://agency-check.app/mcp`, choose OAuth, and sign in.

## VS Code (GitHub Copilot agent mode)
Add to `.vscode/mcp.json`:
```json
{
  "servers": {
    "agency-check": { "type": "http", "url": "https://agency-check.app/mcp" }
  }
}
```

## Any other remote MCP client
Point it at `https://agency-check.app/mcp` using the Streamable HTTP transport. An unauthenticated request returns `401` with a `WWW-Authenticate` header pointing to the OAuth metadata; OAuth authorization-server metadata is at `https://agency-check.app/.well-known/oauth-authorization-server`.

For clients that only support stdio, use a bridge such as `npx mcp-remote https://agency-check.app/mcp`.
