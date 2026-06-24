# Spider Cloud plugin for Grok Build

The fastest web crawling, scraping, search, and browser automation for AI agents —
delivered through the hosted **Spider Cloud MCP server**, with built-in anti-bot
bypass, proxy rotation, and AI-driven extraction.

- **Website:** https://spider.cloud
- **MCP docs:** https://spider.cloud/mcp
- **Get an API key:** https://spider.cloud/api-keys

## What this plugin ships

- **1 MCP server** — the hosted Spider endpoint at `https://mcp.spider.cloud/mcp`, exposing crawl, scrape, search, links, screenshot, unblocker, transform, credits, AI extraction, and remote browser-automation tools.
- **3 skills** — `spider` (overview + tool-selection guide), `spider-crawl-scrape` (crawling, scraping, search, bot bypass), and `spider-browser` (interactive browser sessions).

## Authentication

The Spider MCP server authenticates with a **Bearer API key**. The bundled
[`.mcp.json`](.mcp.json) reads it from the `SPIDER_API_KEY` environment variable:

```json
{
  "mcpServers": {
    "spider": {
      "type": "http",
      "url": "https://mcp.spider.cloud/mcp",
      "headers": { "Authorization": "Bearer ${SPIDER_API_KEY}" }
    }
  }
}
```

Set the variable before launching Grok Build:

```bash
export SPIDER_API_KEY="your-api-key"   # from https://spider.cloud/api-keys
```

Core tools run on pay-per-use credits (no subscription required). The AI tools
require an [AI subscription](https://spider.cloud/ai/pricing).

## Network & credentials (for review)

- **Endpoint called:** `https://mcp.spider.cloud/mcp` (the official Spider Cloud hosted MCP server). No other network endpoints.
- **Credential:** `SPIDER_API_KEY`, sent only as the `Authorization: Bearer` header to the endpoint above. Nothing is read from the filesystem and no telemetry is collected by this plugin.

## License

MIT — see [LICENSE](LICENSE).
