# Internet After Interfaces

A 17-slide keynote manifesto on machine economies, autonomous transactions, and the post.ui web.

Delivered at **ClawCamp Human+Tech Week 2026**, May 11, 2026, The Hibernia Bank, San Francisco.

Speaker: **Rayyan Zahid** ([linkedin.com/in/rayyanzahid](https://linkedin.com/in/rayyanzahid))

Live: [internet-after-interfaces.vercel.app](https://internet-after-interfaces.vercel.app)

## What this is

A single-page HTML deck. Keyboard nav. URL-hash deeplinks. Mobile-responsive. The deck itself is agent-readable (see `/.well-known/ai-agent.json`) — recursive proof of thesis.

Built with the [Controlled Chaos PRO](https://github.com/RayyanZahid/controlled-chaos-pro) methodology. Persona: Scher (scale-as-voice) × Weingart (disciplined rebellion, one off-grid violation on slide 11) × terminal/monospace undercurrent derived from the subject (the agentic web's native typography is `.well-known/` files and HTTP traces). Editorial register. One signature microfeature: a live `fetch()` of immersivecommons.com's `/.well-known/ai-agent.json` on slide 12 with CORS fallback.

## Navigation

- `← / →` — previous / next slide
- `1`–`9`, `0` — jump to slide
- `Home` / `End` — first / last
- `F` — fullscreen toggle
- `O` or `Esc` — overview grid
- swipe on mobile
- URL-hash deeplinks: `/#3` etc.

## Structure

```
internet-after-interfaces/
├── index.html              single-file deck (HTML + CSS + JS inlined)
├── .well-known/
│   ├── ai-agent.json       Aiia agent manifest for this deck
│   └── agent-card.json     A2A agent card
├── robots.txt              agent-aware
├── llms.txt                LLM-friendly site map
├── sitemap.xml             search sitemap
├── og.svg                  open-graph card (1200×630)
├── vercel.json             static deploy + CORS for .well-known
└── README.md
```

Total weight before fonts: ~46 KB.

## Source citations

Numbers and quotes in the deck come from primary sources. See `llms.txt` for the full citation list. The most load-bearing ones:

- Cloudflare · Agent Readiness Score (April 2026) — 200k-site audit numbers (78% / 4% / 3.9% / <15) and the "third language" quote
- Anthropic · MCP donation to Linux Foundation (Dec 9, 2025) — 10,000+ MCP servers
- Linux Foundation · A2A 1-year retrospective (April 2026) — 150+ orgs
- x402.org + Coinbase CDP — HTTP 402 reservation, 69k agents, 165M txns
- a16z · Big Ideas 2026: The Agentic Interface — closing quote
- Amazon Q4 2025 earnings · Walmart · Klarna · Shopify Winter 2026 — production receipts

## Deploy notes

This is a pure static site. Vercel auto-detects. No build step.

```bash
vercel --prod
```

The `vercel.json` sets:
- `Content-Type: application/json` on `/.well-known/*` (so JSON files serve correctly)
- `Access-Control-Allow-Origin: *` on `/.well-known/*` (so agents can fetch cross-origin)
- `text/plain` on `/llms.txt` and `/robots.txt`
- `image/svg+xml` on `/og.svg`
- `X-Robots-Tag: index, follow` on everything

## License

[CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/). Agents welcome to quote with attribution.

## Companion exhibits

- **Immersive Commons** — agent-native venue. `/.well-known/ai-agent.json` + MCP + A2A live at [immersivecommons.com](https://immersivecommons.com)
- **Skew** — supply-side flip, AI landing-page generator. [skew.site](https://skew.site)
- **Lobsterhoney** — honeypots for malicious agents. [lobsterhoney.com](https://lobsterhoney.com)
- **agentify** — 21-point agent-readiness audit, Claude skill. Verify any site at [isitagentready.com](https://isitagentready.com)
