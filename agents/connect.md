---
description: >-
  Connect an AI agent to Lid over MCP: create a key in Settings, point the agent
  at mcp.lid.pro/mcp, make the first calls, publish a product.
---

# Connect an agent

In plain words: this page gets an AI agent from zero to its first call on Lid. If you sell or share on Lid through the app, you never need it.

## How does an AI agent connect to Lid?

Over MCP (Model Context Protocol), with one API key and one address. Lid runs an MCP server at `https://mcp.lid.pro/mcp` (Streamable HTTP); the agent sends its key as a bearer token and gets the same tools a person has in the dashboard.

{% stepper %}
{% step %}
### Create a key

In the app: **Settings → Developer → Create key**. One key per agent, labeled. The key is shown once and starts with `lpmcp_`. Treat keys like money: one key per agent, revoke what you do not recognize.
{% endstep %}

{% step %}
### Point the agent at Lid

{% tabs %}
{% tab title="Claude Code" %}
```bash
claude mcp add --transport http lid https://mcp.lid.pro/mcp \
  --header "Authorization: Bearer lpmcp_YOUR_KEY"
```
{% endtab %}

{% tab title="Cursor" %}
In `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "lid": {
      "url": "https://mcp.lid.pro/mcp",
      "headers": { "Authorization": "Bearer lpmcp_YOUR_KEY" }
    }
  }
}
```
{% endtab %}

{% tab title="Claude Desktop" %}
In `claude_desktop_config.json`, through the `mcp-remote` bridge:

```json
{
  "mcpServers": {
    "lid": {
      "command": "npx",
      "args": [
        "-y", "mcp-remote", "https://mcp.lid.pro/mcp",
        "--header", "Authorization: Bearer lpmcp_YOUR_KEY"
      ]
    }
  }
}
```
{% endtab %}

{% tab title="Any MCP client" %}
```json
{
  "mcpServers": {
    "lid": {
      "url": "https://mcp.lid.pro/mcp",
      "headers": { "Authorization": "Bearer lpmcp_YOUR_KEY" }
    }
  }
}
```
{% endtab %}

{% tab title="REST" %}
The same tools answer over REST at `https://api.lid.pro/api/v1/agent/*`, one route per tool, with the same bearer key:

```bash
curl -H "Authorization: Bearer lpmcp_YOUR_KEY" \
     -H "User-Agent: my-agent/1.0" \
     https://api.lid.pro/api/v1/agent/<tool>
```

The route list is on the Developer page of your dashboard.
{% endtab %}
{% endtabs %}

A discovery file lives at `https://lid.pro/.well-known/mcp.json`.

{% hint style="info" %}
Send a User-Agent header that names your agent. Default script user agents can be refused at the edge.
{% endhint %}
{% endstep %}

{% step %}
### Make the first three calls

1. `api_health`: confirms the API is reachable. Returns `{ "status": "ok" }`.
2. `my_agent_wallet`: who this key acts as. The user id, the real wallet where revenue goes, and the agent wallet the agent acts from.
3. `get_my_usage`: creation caps, what is left today, and the agent wallet balances. Free to call.
{% endstep %}

{% step %}
### Publish a first product

1. `upload_file` with `gated: true` for the content buyers pay for. It returns a `key`.
2. `create_product` with `name`, `priceUsdc` (human units, `"5"` is five dollars), `maxSupply`, and the commission you offer sharers (`affiliateCommissionBps`, `1000` is 10%).
3. `update_product` with `extraFiles: [{ key, title }]`. A paid product with no file stays a draft; attaching the file publishes it.
4. `my_products` to read it back: product address, price, supply, status.
{% endstep %}
{% endstepper %}

## What can an agent do once it is connected?

Everything a person does from the dashboard except spend production money: create and publish products, share other people's products, run challenges and campaigns, review results, read sales and analytics, and receive signed webhooks. Purchases from the agent's own balance are in preview. Every sale settles like a human sale: one transaction, flat 3%, revenue in the key owner's real wallet.

## What to read next

* [Tool reference](tools.md): every tool, grouped by job.
* [Webhooks and events](webhooks.md): get called when a sale, a prize or a conversion happens.
* [Usage and limits](limits.md): caps and quotas.

Building something on this? Email [alberto@lid.pro](mailto:alberto@lid.pro) with what you are making. Early builders shape what comes next.
