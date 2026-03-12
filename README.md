# Aiqaramba MCP Server

AI-powered browser testing as an MCP tool. Give it a URL and instructions — it opens a real browser, navigates pages, fills forms, clicks buttons, and reports what it finds.

<a href="https://glama.ai/mcp/servers/alex-ai-eu/aiqaramba-mcp">
  <img width="380" height="200" src="https://glama.ai/mcp/servers/alex-ai-eu/aiqaramba-mcp/badge" alt="Aiqaramba MCP server" />
</a>

## What it does

Aiqaramba runs AI agents in real browsers (Chrome, Firefox) to test web applications from an end-user perspective. No selectors, no scripts — describe what to test in plain language.

### Tools

| Tool | What it does | Typical time |
|------|-------------|-------------|
| `create_agent` | Run a targeted test — navigate to a URL, perform actions, verify outcomes | 30–90s |
| `run_discovery` | Explore an entire site — map pages, find issues, generate test journeys | 3–15min |
| `get_agent` | Check agent status and read results (auto-summarizes completed agents) | instant |
| `list_agents` | List all agents in a project | instant |
| `list_projects` | List available projects | instant |

### Example usage

```
"Navigate to https://mysite.com/checkout, fill the payment form with
test card 4242424242424242, click submit, and verify the confirmation
page shows an order number."
```

The agent opens a real browser, executes the flow, takes screenshots at each step, and returns a structured report with pass/fail status.

## Setup

Connect directly to the hosted MCP endpoint. Nothing to download.

**Claude Code / Cursor / VS Code:**

```json
{
  "mcpServers": {
    "aiqaramba": {
      "type": "streamable-http",
      "url": "https://mcp.aiqaramba.com/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_API_KEY"
      }
    }
  }
}
```

## Configuration

| Environment variable | Default | Description |
|---------------------|---------|-------------|
| `AIQARAMBA_API_KEY` | (required) | Your API key from [app.aiqaramba.com](https://app.aiqaramba.com) |

## Get an API key

1. Sign up at [app.aiqaramba.com](https://app.aiqaramba.com)
2. Go to Settings > API Keys
3. Create a new key

Or [book a demo](https://outlook.office.com/bookwithme/user/ecce23b18694424a8898f7842a474697@alex-ai.eu/meetingtype/88YUJXiafkOpjY494rH-6A2?anonymous&ismsaljsauthenabled&ep=mlink) to get started with a guided setup.

## Requirements

- URLs must be publicly reachable (not localhost). For local apps, use a tunnel like ngrok.
- The agent needs to be able to navigate to the page without VPN or IP restrictions.

## Terms

By using the Aiqaramba API, you agree to our [Terms of Service](https://aiqaramba.com/terms). The API returns terms at `GET /api/v1/terms` and via the `X-Terms-URL` response header.

## Links

- [Documentation](https://app.aiqaramba.com/docs)
- [Privacy Policy](https://aiqaramba.com/privacy)
- [Data Processing Agreement](https://aiqaramba.com/dpa)
- [Website](https://aiqaramba.com)