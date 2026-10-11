# FORMA MCP

**A real browser for any MCP-compatible agent.** FORMA MCP brings Playwright-based page inspection and UI/UX evidence to IDEs, coding agents, and chat clients through the standard Model Context Protocol.

[![npm version](https://img.shields.io/npm/v/@forma-ai/forma-mcp)](https://www.npmjs.com/package/@forma-ai/forma-mcp) [![License: MIT](https://img.shields.io/badge/License-MIT-8a8c70.svg)](./LICENSE) [![Node.js 20+](https://img.shields.io/badge/Node.js-20%2B-43853d)](https://nodejs.org/)

## Connect an MCP client

Run the package over MCP stdio and provide the FORMA vision endpoint and token as environment variables:

```json
{
  "command": "npx",
  "args": ["-y", "@forma-ai/forma-mcp"],
  "env": {
    "FORMA_URL": "https://your-kaggle-tunnel.trycloudflare.com",
    "FORMA_TOKEN": "your-bearer-token"
  }
}
```

Add this server configuration to any MCP host that supports local stdio servers. The host supplies the consent interface for tool calls. FORMA does not provide an unauthenticated public HTTP MCP endpoint.

## Browser capabilities

- Navigate pages and capture desktop, tablet, and mobile screenshots.
- Read DOM snapshots, heading and landmark structure, forms, and links.
- Inspect console errors, failed requests, page crashes, fonts, and performance signals.
- Run axe accessibility checks, Lighthouse, contrast, spacing, tap-target, and visual-hierarchy scans.
- Inspect computed colors and styles, hover states, CSS motion metadata, and usability signals.
- Scroll, hover, click, and type in the page through host-approved browser actions.
- Capture visual diffs and send a screenshot with measured context to the FORMA audit endpoint.

Tools provide automated signals and measurements. They do not replace keyboard, screen-reader, or human usability testing. Analytics detection reports common script signatures; it cannot access private heatmaps, session recordings, or analytics dashboards.

## Browser isolation and permissions

On first use, Playwright installs or launches its own Chromium browser. Headed mode opens a separate visible Chromium process. FORMA does not attach to your regular browser profile or access its cookies, passwords, or history. Browser interaction changes page state and should be approved by the MCP host. Only inspect pages you are authorized to access.

Screenshots and image artifacts are saved under `.forma/artifacts/` in the active project.

## Requirements

- Node.js 20 or newer
- An MCP-compatible client with local stdio server support
- A running FORMA vision endpoint for screenshot audits

## Links

- [GitHub repository](https://github.com/EgoisticCoder/Forma_MCP)
- [npm package](https://www.npmjs.com/package/@forma-ai/forma-mcp)
- [FORMA CLI](https://github.com/EgoisticCoder/Forma_CLI)
- [FORMA MCP website](https://forma-mcp-website.vercel.app/)
- [FORMA project](https://github.com/EgoisticCoder/Forma)

## License

MIT. See [LICENSE](./LICENSE).
