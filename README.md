# AI Media Buyer

**An autonomous performance-marketing engine that turns a Shopify store URL into live, optimized Google Ads campaigns — with zero manual ad creation.**

Give it a store link. It crawls the catalog, researches keywords, generates on-brand product creatives, writes ad copy, launches Responsive Search Ads on Google, and then manages daily budget and bidding decisions on its own — pausing losers and scaling winners based on real performance data.

---

## Why this project matters

Running paid ads for an e-commerce store is normally a full-time job: pulling product data, researching keywords, briefing a designer, writing copy, building campaigns in Google Ads, and then babysitting spend every day. This system replaces that entire workflow with one automated pipeline, so a store owner (or an agency managing dozens of stores) can go from "here's my store" to "ads are live and self-optimizing" in minutes instead of weeks.

It was built as a full end-to-end product — not a script or a proof of concept — with a real dashboard, authentication, role-based access, and production deployment tooling.

---

## What it does, end to end

1. **Catalog discovery** — crawls the store's sitemap and pulls every product page
2. **Product extraction** — scrapes title, price, description, and imagery for each product
3. **Keyword research** — generates seed keywords with AI, expands them with real search volume/CPC data, and filters out anything that isn't profitable
4. **Creative generation** — produces lifestyle product imagery, quality-checks it with AI vision, and exports it in every aspect ratio Google Ads requires
5. **Ad copywriting** — writes multiple headline and description variations per product, validated against Google's character limits
6. **Campaign launch** — assembles and publishes a live Google Ads Responsive Search Ad campaign, fully structured (budget, ad group, keywords, ads)
7. **Ongoing optimization** — a daily job syncs real performance data, automatically pauses underperforming campaigns, and increases budget on winners

Everything above runs unattended once triggered. A human only needs to review results.

---

## What's included

| | |
|---|---|
| **Backend** | Node.js/TypeScript API and automation engine — see [backend/](backend/README.md) |
| **Frontend** | A client dashboard to launch, monitor, and review campaigns — see [frontend/](frontend/README.md) |

The dashboard lets a client (or their team) paste in a store URL, watch the pipeline run in real time, review generated keywords and creatives, and track live campaign performance — no code or Google Ads expertise required.

---

## Tech stack

| Layer | Technology |
|---|---|
| Backend | Node.js 22, TypeScript, Express |
| Frontend | Next.js 14, React, Tailwind CSS, shadcn/ui |
| Database | PostgreSQL with Drizzle ORM |
| Background jobs | BullMQ + Redis (queued, rate-limited pipeline) |
| AI / LLM | GPT-4o for copywriting, keyword generation, and image quality review |
| Ad platform | Google Ads API (live campaign creation & management) |
| Storage | Cloudflare R2 for generated creative assets |
| Infrastructure | AWS EC2, PM2 process management |

---

## Key capabilities that set this apart

- **Fully autonomous, not assistive** — the system makes and executes decisions (which keywords to keep, when to pause a campaign, when to scale budget) rather than just generating suggestions for a human to act on.
- **Financially-aware by design** — every keyword and bidding decision is filtered through a profitability formula (product price × margin × conversion rate), so spend only goes toward keywords that can be profitable.
- **Production-grade, not a demo** — includes authentication, role-based permissions, rate limiting, structured logging, and a deployment pipeline for real usage, not just a local script.
- **Self-correcting** — a daily optimizer continuously reviews live performance and adjusts campaigns without manual intervention.

---

## Project structure

```
ai-media-buyer/
├── backend/     # API, automation pipeline, Google Ads integration, optimizer
└── frontend/    # Client-facing dashboard
```

Detailed setup and configuration instructions for each part live in their own README:
- [backend/README.md](backend/README.md)
- [frontend/README.md](frontend/README.md)

---

## License

This repository is shared publicly for **viewing and reference only**. See [LICENSE](LICENSE) — no part of this code may be copied, reused, or redistributed without written permission.

---

## About

Built by [The Fabcode](https://thefabcode.org) — a development team specializing in AI-driven automation and full-stack product engineering. Interested in a similar system for your business? Get in touch.
