<img src="logo-400.png" alt="Backlinksbeheer logo" width="96" height="96">

# Backlinksbeheer MCP server

**Read your stored backlinks, link checks and lost-link alerts per domain. Read-only.**

Remote MCP server: `https://backlinksbeheer.nl/mcp` (Streamable HTTP) · Website: [backlinksbeheer.nl](https://backlinksbeheer.nl/)

## What it does

Backlinksbeheer monitors the backlinks to your own websites. Through this MCP server an AI assistant reads what is stored in your account: your domains and link counts, every backlink record, the check history of a link, links whose last check found a problem (dead, error, timeout or redirect) and a summary per domain.

Read-only. The server reports stored check results; it does not start a new crawl or change records.

## Connect

- **Server URL:** `https://backlinksbeheer.nl/mcp`
- **Transport:** Streamable HTTP
- **Authentication:** OAuth with PKCE (S256), dynamic client registration and client ID metadata documents, so MCP clients connect without manual setup. Sign in with your backlinksbeheer.nl account.

**Claude (claude.ai, Desktop):** Settings → Connectors → Add custom connector → paste the server URL.

**Claude Code:**

```bash
claude mcp add --transport http backlinksbeheer https://backlinksbeheer.nl/mcp
```

**Cursor, VS Code, Cline, Windsurf and other clients** (`mcp.json` / `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "backlinksbeheer": {
      "type": "http",
      "url": "https://backlinksbeheer.nl/mcp"
    }
  }
}
```

Cline uses `"type": "streamableHttp"`; see [llms-install.md](llms-install.md).

## Tools

| Tool | What it does |
|---|---|
| `account / list_domains` | Account and monitored domains. |
| `list_backlinks / backlink_details` | Stored backlinks and the check history per link. |
| `link_alerts` | Links with a stored problem status. |
| `domain_report` | Summary per domain. |

## Example prompts

- Which backlinks did I lose this month?
- Show the check history of the link from example.nl.
- Give me a backlink summary for mysite.nl.

## Links

- Website: https://backlinksbeheer.nl/
- Documentation: https://backlinksbeheer.nl/plugin/
- Privacy policy: https://backlinksbeheer.nl/plugin/privacy/
- Terms: https://backlinksbeheer.nl/plugin/terms/
- Support: mailto:info@backlinksbeheer.nl

## Keywords

backlink monitoring, backlink checker, lost link alerts, link audit, SEO monitoring, backlink tracker.

Nederlands: backlinks controleren, backlink monitor, verloren links, linkbuilding bijhouden, backlinks beheren, SEO monitoring.

## More MCP servers by Samautomation

- [Scamchecker.nl](https://scamchecker.nl/): Check a suspicious email, SMS, WhatsApp message or link for scam signals (Netherlands, Belgium). ([listing](https://github.com/smrht/scamchecker-mcp))
- [Klussenbeheer](https://samdesk.nl/klussenbeheer/): Job management for Dutch service companies: jobs, customers, planning, quotes and invoices. ([listing](https://github.com/smrht/klussenbeheer-mcp))
- [Muziek maken met AI](https://muziekmakenmetai.nl/): Make an original song from a prompt or your own lyrics. Two versions per song, MP3 download. ([listing](https://github.com/smrht/muziekmakenmetai-mcp))
- [Beheer je WP](https://beheerjewp.nl/): Manage a WordPress site from your AI assistant: read, search, propose edits, Search Console data. ([listing](https://github.com/smrht/beheerjewp-mcp))
- [UlazAI Media](https://ulazai.com/): Create private AI images with your UlazAI account: pick a model, confirm, generate, download. ([listing](https://github.com/smrht/ulazai-mcp))
- [Backlinkswinkel](https://backlinkswinkel.nl/): Search Dutch websites for backlinks, check metrics and prices, order after confirmation, track. ([listing](https://github.com/smrht/backlinkswinkel-mcp))
- [Samautomation Video](https://samautomation.work/): Render an MP4 from your own images, clips, voice-over and timed captions. JSON to video. ([listing](https://github.com/smrht/samautomation-video-mcp))
- [PDF Samenvoegen](https://pdfsamenvoegen.nl/): Merge your own PDFs in a confirmed order and get one downloadable PDF. ([listing](https://github.com/smrht/pdfsamenvoegen-mcp))
- [Diamond Painting Converter](https://diamondpaintingconverter.com/): Find your purchased diamond painting patterns and download the PDF with DMC colour legend. ([listing](https://github.com/smrht/diamondpaintingconverter-mcp))
- [Nummerschilderen.com shop advisor](https://nummerschilderen.com/): Search paint-by-number kits, get size and price advice for your own photo, shop info. No login. ([listing](https://github.com/smrht/nummerschilderen-mcp))
- [DiamondPaintingWinkel.nl shop advisor](https://diamondpaintingwinkel.nl/): Search diamond painting kits, get size and price advice for your own photo, shop info. No login. ([listing](https://github.com/smrht/diamondpaintingwinkel-mcp))
- [AI Rechtshulp](https://ai-rechtshulp.nl/): Search Dutch and EU case law with ECLI sources and verify quotes against the judgment. ([listing](https://github.com/smrht/ai-rechtshulp-mcp))
- [SamDesk Support](https://samdesk.nl/support/plugin/): Read your SamDesk support inbox, find customer agreements and draft replies. Read-only. ([listing](https://github.com/smrht/samdesk-support-mcp))

## Publisher

Samautomation, Wognum, the Netherlands · https://samautomation.work

This repository holds the public listing (README, `server.json`, install notes). The server itself is hosted by the publisher; there is nothing to install or build.
