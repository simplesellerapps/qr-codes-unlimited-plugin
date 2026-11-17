# QR Codes Unlimited plugin

Create, style, manage, and download QR codes and explore their scans in Claude
Code or Codex. This package connects to the existing hosted MCP server at
**https://qrcodesunlimited.com/mcp**. It does not install a local server or require
an OpenAI or Anthropic API key.

The packaged connection uses browser sign-in for a standalone QR Codes Unlimited
account. Your account's permissions and plan limits apply. For a Shopify store,
use the API-key instructions below; signing in to a standalone account does not
connect your store.

## Install in Claude Code

Extract the ZIP into a folder named `qr-codes-unlimited`, then run these commands
from its parent directory:

```sh
claude plugin marketplace add ./qr-codes-unlimited
claude plugin install qr-codes-unlimited@qr-codes-unlimited
```

Start a new Claude Code session. Open `/mcp`, choose the plugin's `qrcodes`
connection, and authenticate in your browser. Then ask:

> Use QR Codes Unlimited to confirm which account and plan I am connected to.

For a single session, `claude --plugin-dir ./qr-codes-unlimited` loads the same
package without installing the marketplace.

## Install in Codex

Extract the ZIP into `qr-codes-unlimited`, then register that directory:

```sh
codex plugin marketplace add ./qr-codes-unlimited
```

Restart the desktop app if the new source does not appear. In the plugin
directory, select the **QR Codes Unlimited** marketplace, install its plugin,
and complete browser sign-in. Run its setup workflow or ask it to confirm the
connected account. Start a new chat if the tools have not refreshed.

If your Codex version does not support local plugin marketplaces, the existing
MCP connection works directly:

```sh
codex mcp add qrcodes --url https://qrcodesunlimited.com/mcp
codex mcp login qrcodes
```

Use either the plugin connection or the direct connection for an account to
avoid duplicate tools. Existing connections do not need to be removed to use
the service; install the plugin only if you want its bundled workflows.

## Shopify stores

The OAuth plugin above connects standalone accounts. For a Shopify store, open
**QR Codes Unlimited → Settings → API** and create a store secret key. Use the existing
direct MCP setup guide instead of enabling the OAuth plugin for that store.
The service's Shopify plan requirements still apply.

Follow the account-specific [Connect AI setup guide](https://qrcodesunlimited.com/qr/my/ai_assistants)
or open the Connect AI card inside the Shopify app. Enter the store key only in the
assistant's secure connection settings. Do not paste it into chat or this package.
Confirm the connected Shopify domain before making changes.

## Try it

- “Create a dynamic QR code for https://example.com, make it dark blue, and give me a PNG download.”
- “Find my menu QR code and help me change its destination.”
- “Summarize yesterday's scans in my account's time zone and compare with the day before.”
- “How do I use my own domain for scanned links?”

The server returns image previews and signed downloads. This package does not
add a custom embedded editor; rendering depends on the host. Billing, passwords,
team membership, and cross-account support operations are outside its tools.

## Data use and account access

Your assistant sends requested tool arguments to QR Codes Unlimited and receives
account-scoped results. Depending on the task, those results include account
name and email, QR names and destinations, contact-card content, uploaded files,
Wi-Fi details, and scan analytics. Individual scan records can contain IP-derived
location and device information. Your chosen AI provider processes the arguments
and results under its own policies.

The service stores QR codes, files, settings, and scan records in your account.
It also records the connected assistant, tool name, timestamp, account, and
success status for service usage reporting. This package adds no independent
analytics tracker or local server. Requested remote file and logo imports are
fetched by the hosted service from the supplied public URL.

Only connect an account you intend the assistant to access. Use summary analytics
when you do not need individual scan records. The service's
[privacy policy](https://qrcodesunlimited.com/privacy) describes retention,
service providers, and data-access and deletion requests. This integration is
not intended for children under 18.

## Disconnect

Disconnect standalone OAuth grants from **Settings → API → Connected apps**.
For a store key, revoke the key in that store's API settings. Uninstalling a
plugin from an assistant does not itself revoke the service-side credential.

## License

Plugin manifests, skills, and documentation use the [MIT license](LICENSE).
Brand images and the hosted service retain their existing rights; see [NOTICE](NOTICE).

[Website](https://qrcodesunlimited.com) ·
[Setup guide](https://qrcodesunlimited.com/qr/my/ai_assistants) ·
[Support](mailto:hello@qrcodesunlimited.com) ·
[Privacy](https://qrcodesunlimited.com/privacy) ·
[Terms](https://qrcodesunlimited.com/tos)
