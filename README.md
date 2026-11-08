# Lueira for Claude

Lueira workflows for Claude, on top of the Lueira connector. [Lueira](https://lueira.com/en/) is the booking and
operations platform for activity businesses such as ski schools, surf schools and diving centers.

The plugin adds three skills and connects Claude to the hosted Lueira MCP server:

| Skill | What it does |
|-------|--------------|
| `lueira-business-report` | Business reports on orders, bookings, rental stock and instructors |
| `lueira-customer-management` | Find customers, inspect their orders and booking details, and manage customer records |
| `lueira-catalog-inventory` | Browse and manage products, pricing, partners, instructors and inventory |

Access stays within the connected business and the permissions you grant. Management actions are limited to
the features enabled for your business.

The plugin does not create, change or cancel orders or bookings, register payments, or process purchases.

## Install

In Claude Code:

```
/plugin install lueira --marketplace maladetastudio/lueira-claude-plugin
```

## Requirements

An existing Lueira account with API access. Claude asks you to sign in to Lueira and approve the permissions
when you first use the connector.

## Examples

- "Find a customer and show their orders."
- "Show my rental products and stock items."
- "List my instructors."

## What the plugin runs and sends

- It contains no hooks, scripts, executables or bundled packages: only the skill instructions, the logo and
  this configuration.
- `.mcp.json` declares one remote MCP server, `https://api.lueira.com/api/v1/mcp`. Claude connects to it with
  OAuth, so no password, token or API key is stored in the plugin.
- The skills only guide how Claude uses the tools that server exposes. Data goes to Lueira's servers through
  that connection and nowhere else.

## Support and policies

- Help center: <https://help.lueira.com/en>
- Privacy policy: <https://lueira.com/en/legal/privacy/>
- Terms of service: <https://lueira.com/en/legal/terms/>

## License

Proprietary, see [LICENSE](LICENSE). Use of the Lueira service is covered by the terms above.
