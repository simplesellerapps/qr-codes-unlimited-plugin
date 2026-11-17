---
name: connect
description: Connect or troubleshoot the QR Codes Unlimited plugin and verify the selected QR account. Use for plugin setup or connection errors, not QR creation or edits.
---

Connect the user's intended QR Codes Unlimited account through the plugin's
remote MCP server at https://qrcodesunlimited.com/mcp.

- For a standalone account, use the host's OAuth browser sign-in. Let the user
  complete sign-in and consent. Do not ask for a password or API key in chat.
- Shopify stores use the existing API-key connection instead of standalone
  OAuth. Follow the Shopify section in [the installation guide](../../README.md).
  Keep the key in secure connection settings or a protected environment variable.
- Preserve other connections. If the same account is already connected, use that
  connection rather than adding another. If the host cannot configure connections,
  give its setup steps from the installation guide.
- After authentication, discover the connection's tools and call `get_account`.
  Report the returned account name, platform, and plan. Only say the connection
  works after this call succeeds. If it is the wrong account, resolve that before
  using write tools.

Setup uses read-only account information. Do not create a demonstration code,
change settings, delete data, or upgrade a subscription as part of connecting.
For a denied or expired connection, explain the returned error and the available
reconnection or account-management link.
