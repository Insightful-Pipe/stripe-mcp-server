# Stripe MCP Server by Insightful Pipe

[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue)](https://insightfulpipe.com/mcp-servers/stripe)
[![Insightful Pipe](https://img.shields.io/badge/Insightful_Pipe-MCP_Servers-purple)](https://insightfulpipe.com/mcp-servers)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Connect Stripe to AI assistants: read-only payments, subscriptions, invoices and revenue data.**

Part of the [Insightful Pipe MCP Server Collection](https://insightfulpipe.com/mcp-servers) — use Stripe from Claude, ChatGPT, Cursor, and other AI assistants through the Model Context Protocol (MCP).

<img src="images/stripe-icon.svg" alt="Stripe MCP Server" width="64" height="64">

## MCP Server URL

```
https://stripe.insightfulmcp.com/
```

## What is Stripe MCP?

Stripe MCP is a **remote Model Context Protocol server** hosted by InsightfulPipe. Access payments, subscriptions, invoices, customers, charges, refunds, and financial data from your Stripe account.

## Installation

### Claude

1. Copy the MCP Server URL: `https://stripe.insightfulmcp.com/`
2. Open [Claude Connectors Settings](https://claude.ai/settings/connectors)
3. Scroll to the bottom and click **Add custom connector**
4. Paste the URL and click **Add**
5. Click **Connect** on the connector to start authorization
6. Click **Authorize access** in the browser to complete the connection

### ChatGPT

Custom MCP servers are added through ChatGPT's **Developer mode**. Availability depends on your ChatGPT plan, and workspace admins may need to allow it.

1. Turn on **Developer mode** in ChatGPT settings
2. Create a new app for a remote MCP server and paste the URL: `https://stripe.insightfulmcp.com/`
3. Authorize with your InsightfulPipe account

See OpenAI's guide: [Developer mode and MCP apps in ChatGPT](https://help.openai.com/en/articles/12584461-developer-mode-and-mcp-apps-in-chatgpt)

### Claude Code

```bash
claude mcp add --transport http stripe https://stripe.insightfulmcp.com/
```

### Cursor

Add the server to `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "stripe": {
      "url": "https://stripe.insightfulmcp.com/"
    }
  }
}
```

Then authorize the connection when Cursor prompts you.

## Available Actions

41 actions: 41 read, 0 write.

### Read Actions (41)

<details>
<summary>Show all 41 read actions</summary>

| Action | Description |
|--------|-------------|
| `get_account` | Retrieve the current account details |
| `get_accounts` | List all connected accounts (Stripe Connect) |
| `get_application_fees` | List all application fees collected from connected accounts (Connect) |
| `get_balance` | Retrieve the current account balance (available, pending, and connect reserved amounts by currency) |
| `get_balance_transactions` | List balance transactions (funds movements: charges, refunds, transfers, payouts, etc.) |
| `get_charge` | Retrieve a specific charge by ID |
| `get_charges` | List all charges |
| `get_checkout_sessions` | List all Checkout Sessions |
| `get_coupons` | List all coupons |
| `get_credit_notes` | List all credit notes |
| `get_customer` | Retrieve a specific customer by ID |
| `get_customers` | List all customers |
| `get_dispute` | Retrieve a specific dispute by ID |
| `get_disputes` | List all disputes (chargebacks) |
| `get_early_fraud_warnings` | List all early fraud warnings from Radar |
| `get_events` | List events (webhooks log) |
| `get_file_links` | List all file links |
| `get_files` | List all files uploaded to Stripe (dispute evidence, identity documents, etc.) |
| `get_invoice` | Retrieve a specific invoice by ID |
| `get_invoice_items` | List all invoice items (line items that can be added to invoices) |
| `get_invoices` | List all invoices |
| `get_payment_intent` | Retrieve a specific payment intent by ID |
| `get_payment_intents` | List all payment intents |
| `get_payment_methods` | List payment methods for a specific customer |
| `get_payout` | Retrieve a specific payout by ID |
| `get_payouts` | List all payouts |
| `get_plans` | List all plans (legacy pricing model, prefer Prices) |
| `get_prices` | List all prices |
| `get_product` | Retrieve a specific product by ID |
| `get_products` | List all products |
| `get_promotion_codes` | List all promotion codes |
| `get_refund` | Retrieve a specific refund by ID |
| `get_refunds` | List all refunds |
| `get_reviews` | List all Radar reviews |
| `get_setup_intents` | List all setup intents |
| `get_shipping_rates` | List all shipping rates |
| `get_subscription` | Retrieve a specific subscription by ID |
| `get_subscription_schedules` | List all subscription schedules |
| `get_subscriptions` | List all subscriptions |
| `get_top_ups` | List all top-ups |
| `get_transfers` | List all transfers |

</details>

## Control What Your AI Can Do

You decide what AI agents can do with each connected account:

- **Turn individual actions on or off** for every connected account, so agents only see the actions you allow.
- **Connect as Read-only or Read & Write.** A read-only connection can only enable read actions.
- **Destructive actions stay off by default.** Actions such as deletes are disabled until an admin enables them.
- **Team access per account.** Restricted team members only use the accounts they are granted, with the read actions enabled on them.

## Usage Examples

```
"What is my current Stripe balance?"
```

```
"How many active subscriptions do we have?"
```

```
"List failed payments from the last 7 days"
```

## Pricing

The Stripe MCP server is included in every InsightfulPipe plan, together with all other MCP servers and the CLI. Plans start at $29.99/month with a 7-day free trial. See [insightfulpipe.com/pricing](https://insightfulpipe.com/pricing) for current plans.

## Explore More MCP Servers by Insightful Pipe

Visit **[insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)** to discover our full collection of MCP servers.

- [Shopify MCP](https://insightfulpipe.com/mcp-servers/shopify)
- [WooCommerce MCP](https://insightfulpipe.com/mcp-servers/woocommerce)

**[View All MCP Servers →](https://insightfulpipe.com/mcp-servers)**

## Resources

- [Documentation](https://insightfulpipe.com/docs)
- [Video Tutorial](https://www.youtube.com/playlist?list=PLJNzvjxzI5Xwe__BJJLAelSF0ewO3mEFk)
- [InsightfulPipe Blog](https://insightfulpipe.com/blog)

## Support

- **Documentation**: [insightfulpipe.com/docs](https://insightfulpipe.com/docs)
- **All MCP Servers**: [insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)
- **Email**: support@insightfulpipe.com

---

**[Insightful Pipe](https://insightfulpipe.com)** — AI-powered marketing analytics through MCP servers. [Explore all integrations →](https://insightfulpipe.com/mcp-servers)

## License

MIT License - see [LICENSE](LICENSE) for details.
