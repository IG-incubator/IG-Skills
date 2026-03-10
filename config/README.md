# MCP Setup

## 1. Get IG Credentials

1. Create account at [IG](https://www.ig.com/au/demo-account)
2. Get API key from [IG Labs](https://labs.ig.com/)

## 2. Configure Claude Desktop

Add to your Claude Desktop config:

**macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`

```json
{
  "mcpServers": {
    "ig-trading": {
      "command": "node",
      "args": ["path/to/ig-trading-mcp/dist/index.js"],
      "env": {
        "IG_API_KEY": "your-api-key",
        "IG_USERNAME": "your-username",
        "IG_PASSWORD": "your-password",
        "IG_ACCOUNT_ID": "your-account-id",
        "IG_ENVIRONMENT": "DEMO"
      }
    }
  }
}
```

## 3. Test

Restart Claude Desktop and ask: "What accounts do I have on IG?"

## Environment Variables

| Variable | Description |
|----------|-------------|
| `IG_API_KEY` | Your IG Labs API key |
| `IG_USERNAME` | IG account username |
| `IG_PASSWORD` | IG account password |
| `IG_ACCOUNT_ID` | Trading account ID |
| `IG_ENVIRONMENT` | `DEMO` or `LIVE` |

Always start with `DEMO` for testing.
