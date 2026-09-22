---
description: >-
  Connect an AI agent to Lid over MCP: create a key in Settings, point the agent
  at mcp.lid.pro/mcp, make the first calls, publish a product.
---

# Connect an agent

In plain words: this page gets an AI agent from zero to its first call on Lid. If you sell or share on Lid through the app, you never need it.

Lid speaks MCP (Model Context Protocol), the standard most agent frameworks already understand. One key, one address, and the agent has the same tools a person has in the dashboard.

## 1. Create a key

In the app: **Settings → Developer → Create key**. One key per agent, labeled. The key is shown once and starts with `lpmcp_`.

Treat keys like money: one key per agent, revoke what you do not recognize.

## 2. Point the agent at Lid

Endpoint: `https://mcp.lid.pro/mcp` (Streamable HTTP). The key goes in the Authorization header as a bearer token.

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

The same tools are available over REST at `https://api.lid.pro/api/v1/agent/*`, with the same bearer key, for scripts that do not speak MCP. A discovery file lives at `https://lid.pro/.well-known/mcp.json`.

{% hint style="info" %}
Send a User-Agent header that names your agent. Default script user agents can be refused at the edge.
{% endhint %}

## 3. Make the first three calls

1. `api_health`: confirms the API is reachable. Returns `{ "status": "ok" }`.
2. `my_agent_wallet`: who this key acts as. The user id, the real wallet where revenue goes, and the agent wallet the agent acts from.
3. `get_my_usage`: creation caps, what is left today, and the agent wallet balances. Free to call.

## 4. Run the loop

A first product in four calls:

1. `upload_file` with `gated: true` for the content buyers pay for. It returns a `key`.
2. `create_product` with `name`, `priceUsdc` (human units, `"5"` is five dollars), `maxSupply`, and the commission you offer sharers (`affiliateCommissionBps`, `1000` is 10%).
3. `update_product` with `extraFiles: [{ key, title }]`. A paid product with no file stays a draft; attaching the file publishes it.
4. `my_products` to read it back: product address, price, supply, status.

Every sale then settles like a human sale: the split is one transaction, flat 3%, and revenue lands in the key owner's real wallet.

## What to read next

* [Tool reference](tools.md): every tool, grouped by job.
* [Webhooks and events](webhooks.md): get called when a sale, a prize or a conversion happens.
* [Usage and limits](limits.md): caps and quotas.

Building something on this? Email [alberto@lid.pro](mailto:alberto@lid.pro) with what you are making. Early builders shape what comes next.
