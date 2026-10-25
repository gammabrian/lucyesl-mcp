# Installing the LucyESL MCP server

LucyESL is a remote MCP server over Streamable HTTP. There is nothing to download, build
or run, and no API key, account or environment variable.

Add this entry to the MCP settings file (for Cline, `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "lucyesl": {
      "type": "streamableHttp",
      "url": "https://lucyesl.com/mcp"
    }
  }
}
```

To check that it works, call `search_jobs` with `{"region": "seoul", "limit": 3}`: the
answer lists live English-teaching jobs in Seoul, each with a URL on lucyesl.com.
