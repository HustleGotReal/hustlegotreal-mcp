# Hustle Got Real MCP Server

Connect Codex, Claude or any MCP client to Hustle Got Real (HGR). Analyze store data, review listings, monitor stock and prices, and manage dropshipping workflows across eBay, Amazon, Shopify and more with live account context.

- **Endpoint:** `https://mcp.hustlegotreal.com/` (Streamable HTTP)
- ChatGPT compatibility endpoint: `https://mcp.hustlegotreal.com/mcp`.
- **Auth:** OAuth, sign in with your Hustle Got Real account
- **Website:** https://hustlegotreal.com/mcp/
- **Official MCP Registry:** `com.hustlegotreal/mcp`

## What you can do

- Find products and sources, and list them to your sales channels in bulk.
- Review listings, listing quality, and price and stock history; relist, update or end listings.
- Manage pricing rules and Price Warrior repricing.
- Work through orders: auto-ordering, purchase status, dispatch, tracking IDs and shipping details.
- Read dashboards, sales, analytics and notifications.
- Run AI publisher agents and AI listing optimization.
- Manage channels, templates, business policies, virtual assistants, support tickets and the affiliate dashboard.

## Connect

The server uses OAuth. Your client opens a browser window, you sign in with your Hustle Got Real account and approve access. You do not copy an API key.

### Claude (claude.ai and Claude Desktop)

Open **Settings → Connectors → Add custom connector**, enter `https://mcp.hustlegotreal.com/` and select **Connect**.

### Claude Code

```bash
claude mcp add --transport http hgr https://mcp.hustlegotreal.com/
```

Then run `/mcp` in Claude Code and authenticate `hgr`.

### Codex CLI

```bash
codex mcp add hgr --url https://mcp.hustlegotreal.com/
codex mcp login hgr
```

### Cursor

Add this to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "hgr": { "url": "https://mcp.hustlegotreal.com/" }
  }
}
```

### VS Code

```bash
code --add-mcp '{"name":"hgr","type":"http","url":"https://mcp.hustlegotreal.com/"}'
```

### Gemini CLI

```bash
gemini mcp add --transport http hgr https://mcp.hustlegotreal.com/
```

### ChatGPT and other clients

Add a custom connector (in ChatGPT, developer mode) with the URL `https://mcp.hustlegotreal.com/`. Any client that supports Streamable HTTP and MCP OAuth works.

## Tools

The server exposes about 170 tools. Your client gets the current list and schemas from `tools/list`. Examples:

- **Listings:** `hgr_get_listings`, `hgr_get_active_listings`, `hgr_get_listing_price_history`, `hgr_get_listing_stock_history`, `hgr_update_listing`, `hgr_relist_listing`, `hgr_terminate_listing`
- **Pricing:** `hgr_get_pricing_rules`, `hgr_add_pricing_rule`, `hgr_update_pricing_rule`, `hgr_get_price_warrior`, `hgr_update_price_warrior_settings`
- **Orders:** `hgr_get_sales`, `hgr_search_orders`, `hgr_process_order_lines`, `hgr_mark_order_lines_as_purchased`, `hgr_generate_tracking_id`, `hgr_get_autoordering_configuration`
- **AI agents:** `hgr_get_ai_agent_dashboard`, `hgr_create_ai_publisher_agent`, `hgr_get_ai_publisher_history`, `hgr_post_ai_publishnow`
- **Account and support:** `hgr_get_authenticated_user`, `hgr_get_subscription_summary`, `hgr_list_channels`, `hgr_list_support_tickets`, `hgr_create_support_ticket`

## Authentication and account

OAuth 2.1 with dynamic client registration, tied to your HGR account. No shared public token.

You need a Hustle Got Real account. See the plans on hustlegotreal.com.

## Links

- Website: https://hustlegotreal.com
- MCP setup page: https://hustlegotreal.com/mcp/
- Privacy policy: https://hustlegotreal.com/privacy/

## About this repository

This repository is the public home of the hosted Hustle Got Real MCP server. It holds this setup guide and the registry metadata (`server.json` for the official MCP Registry, `glama.json` for Glama). The server runs as a hosted service at `https://mcp.hustlegotreal.com/`. Its source code is not in this repository.

Found a problem or have a question? Open an issue.

## License

The contents of this repository are available under the [MIT License](LICENSE).
