# aiomniu — AI-Powered Tech Talent Marketplace

> Connect with vetted developers, designers, and AI specialists for your next project.
> **[aiomniu.top](https://aiomniu.top)**

---

## What We Do

**aiomniu** is an AI-focused freelance platform. Every talent goes through skill verification before being listed — unlike open marketplaces where anyone can sign up. Built-in escrow protects both sides.

What sets us apart:

- **AI-first focus** — we specialize in AI/ML development, not just any freelance work
- **Verified talent only** — skill vetting eliminates noise from your project feed
- **Escrow by default** — funds held until milestones are met
- **Global reach** — serving clients from Australia, US, UK, Singapore, and beyond

---

## How It Works

1. **Post your project** — describe what you need (web app, mobile app, AI integration, e-commerce)
2. **Get matched** — verified talents submit proposals within hours
3. **Fund escrow** — payment held securely until milestone delivery
4. **Review & release** — approve the work, funds released to talent

---

## Why We Built It

Freelance platforms today are optimized for low-barrier volume — throw a job up, get hundreds of proposals, spend hours filtering noise. We wanted the opposite: fewer choices, higher quality, faster outcomes.

The result is **aiomniu**.

---

## Tech That Powers Us

| Layer | Technology | Why |
| --- | --- | --- |
| Frontend | Next.js 15 + TanStack Query | SSR for SEO, client caching for speed |
| Backend | Python 3.12 + FastAPI | Type-safe APIs, async-native |
| Runtime | Pyodide on Cloudflare Workers | Python at the edge, ~50ms TTFB worldwide |
| Database | Cloudflare D1 (SQLite) | SQL we know, global replication, zero-ops |
| Storage | Cloudflare R2 | S3-compatible, zero egress fees |
| Auth | SHA256 + salt + JWT | Stateless auth, no session servers |

### Running Python on the Edge: Pyodide in Production

One of the more unusual pieces of our stack: we run Python via Pyodide inside Cloudflare Workers. It's not trivial — we hit and worked around:

- No threading support → all handlers `async def`
- `__import__` broken in workerd → static imports only
- SQL NULL → `{}` in transit → custom null cleanup layer
- ASGI 1.9.3 pinning → manual bridge for newer versions

We wrote about the full journey: [Dev.to post coming soon].

---

## Traction

As of July 2026:

- **300+** SEO-optimized landing pages live
- **60+** cities and **20+** skill categories covered
- **24** competitor alternative pages (Upwork, Fiverr, etc.)
- Migrated from Vue SPA to Next.js SSR for better crawlability

---

## Links

- Website: [aiomniu.top](https://aiomniu.top)
- Contact: support@aiomniu.top

---

*Built on Cloudflare Workers, FastAPI, and Next.js. Not open source — this repo documents the stack and approach.*
