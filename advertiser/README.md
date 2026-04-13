# Ads3 Advertiser Skill — v1.0.0

Manage your Ads3 advertising campaigns with AI assistance. Query campaign performance, create new ads, and control campaign lifecycle — all through natural language.

## Overview

[Ads3](https://app.ads3.ai) is a Web3 advertising platform that connects advertisers with a wide-ranging network of publishers. The Advertiser Skill gives AI agents native access to your Ads3 account, enabling you to manage campaigns, analyze performance, and optimize spend without leaving your AI coding environment.

## Key Features

- **Query Campaigns** — List all campaigns with real-time metrics (impressions, clicks, conversions, CTR, CVR, cost)
- **Campaign Details** — View detailed campaign configuration and daily performance summaries
- **Create Campaigns** — Launch new ad campaigns with targeting, budget, and bidding settings
- **Manage Campaigns** — Pause, resume, or end campaigns instantly
- **Performance Analysis** — Identify optimization opportunities based on CTR and CVR benchmarks

## Get Started

### Step 1 — Install the Skill

**OpenClaw**
```bash
claw install github:Pea-AI/skills-hub/advertiser
```

**Claude Code**
```bash
claude install github:Pea-AI/skills-hub/advertiser
```

**Manual**
```bash
git clone https://github.com/Pea-AI/skills-hub.git
cp -r skills-hub/advertiser .claude/skills/
```

### Step 2 — Get Your Open API Key

1. Login to [Ads3 Dashboard](https://app.ads3.ai)
2. Navigate to **Account** → **Open API Keys**
3. Click **Create Open API Key**
4. Copy and save your Open API key securely — **it is only shown once**

Open API Key format:
```
sk_live_xxxx...xxxx
```

### Step 3 — Use It

Once the skill is installed, just ask naturally:

- "Show me all my active campaigns"
- "What's the CTR for my Spring Campaign this week?"
- "Pause campaign ID xyz123"
- "Create a new CPC campaign targeting Southeast Asia with a $50 daily budget"
- "Show me the daily breakdown for my top campaign"

---

## Advertising on Ads3

### Targeting Options

| Option | Description |
|--------|-------------|
| Geolocation | Target users by region or country |
| Language | Deliver ads in selected languages |
| Platform | iOS, Android, or All |
| Telegram Premium | Target Telegram Premium subscribers only |
| High Value Users | Target users with Web3 wallet connections |
| TON Wallet | Target users with a linked TON wallet |

### Bidding Strategies

| Type | Description |
|------|-------------|
| CPC | Cost Per Click — pay when users click |
| CPM | Cost Per Mille — pay per 1000 impressions |
| CPA | Cost Per Action — pay per conversion |
| oCPC | Optimized CPC — smart bidding for clicks |
| oCPM | Optimized CPM — smart bidding for impressions |

### Ad Formats

**Image & Text Ads**
- Main image: 1:1 ratio, 800×800px recommended, max 1MB (GIF max 2MB)
- Project icon: 1:1 ratio, 100×100px recommended, max 100KB
- Ad text: up to 50 characters
- Brand name: 1–40 characters
- Button text: 1–20 characters

**Video Ads** — Coming Soon

### Payment & Deposit

Deposit USDT to your account via on-chain transfer. Supported blockchains:

- **Arbitrum**
- **BNB Chain**
- Tron *(Coming Soon)*
- TON Network *(Coming Soon)*

Deposits typically confirm within 10 minutes.

---

## Campaign Status Reference

| Status | Description |
|--------|-------------|
| onGoing | Running |
| paused | Paused by user |
| systemPaused | Paused by system (e.g. insufficient balance) |
| ended | Ended |
| auditing | Under review |
| reject | Review rejected |
| pending | Pending start |
| readyToStart | Ready to start |
| fail | Creation failed |

> **Need urgent ad review?** Contact our official review specialist on Telegram: [@juna_CC](https://t.me/juna_CC)

---

## Supported API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/advertiser/campaigns` | List campaigns with metrics |
| GET | `/advertiser/campaign/summary/:id` | Daily campaign summary |
| GET | `/ad/campaign/:id` | Campaign details |
| POST | `/ad/campaign` | Create campaign |
| PATCH | `/ad/campaign/:id` | Update campaign |
| PATCH | `/ad/campaign/:id/pause` | Pause campaign |
| PATCH | `/ad/campaign/:id/resume` | Resume campaign |
| POST | `/ad/campaign/end` | End campaign |

**API Base URL**: `https://app.ads3.ai/api/v2`

---

## Metrics Reference

| Metric | Formula |
|--------|---------|
| CTR (Click-Through Rate) | clicks / impressions × 100% |
| CVR (Conversion Rate) | conversions / clicks × 100% |
| CPC (Cost Per Click) | cost / clicks |
| CPA (Cost Per Action) | cost / conversions |

> **Tip**: If CTR < 1%, consider improving your ad creative or refining targeting. If CVR < 5%, review your landing page or conversion flow.

---

## Glossary

- **Campaign** — A promotional activity featuring specific ad creatives and targeting settings
- **Impressions** — Number of times an ad is displayed (counted after 2+ seconds with 50%+ viewability)
- **Clicks** — Number of times an ad is clicked
- **Conversions** — Number of completed target actions
- **Daily Budget** — Maximum spend per day in USDT
- **USDT** — Stablecoin pegged 1:1 to USD, used for all transactions on Ads3

---

## Security

- **Never share your Open API Key** — Keep it confidential
- **Keys are shown only once** — Save immediately after creation
- **Revoke compromised keys** — Delete and create a new one if exposed

---

## Links

- [Ads3 Dashboard](https://app.ads3.ai)
- [API Documentation](https://docs.ads3.ai/)
- [Advertiser Introduction](https://docs.ads3.ai/advertiser/introduction.html)
- [GitHub Repository](https://github.com/Pea-AI/skills-hub)
- [Support — Telegram: @juna_CC](https://t.me/juna_CC) — Need to expedite ad review? Contact our official review specialist through this account

---

## Changelog

### v1.0.0 — 2026-04-13

- Initial release
- Campaign list with performance metrics (impressions, clicks, conversions, CTR, CVR, cost)
- Daily campaign summary
- Campaign details view
- Create, update, pause, resume, and end campaigns
- Open API Key authentication via `open-api-key` header
