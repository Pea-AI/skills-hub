# Ads3 Publisher Skill — v1.0.0

Manage your Ads3 publisher account with AI assistance. Query platform and block performance, track earnings, check balance, and submit withdrawals — all through natural language.

## Overview

[Ads3](https://app.ads3.ai) is a Web3 advertising platform that connects publishers with a wide-ranging network of advertisers. The Publisher Skill gives AI agents native access to your Ads3 publisher account, enabling you to monitor monetization, analyze ad placement performance, and manage withdrawals without leaving your AI coding environment.

## Key Features

- **Query Platforms** — List all your platforms with real-time metrics (impressions, clicks, conversions, earnings)
- **Platform Details** — View platform configuration and status
- **Query Blocks** — List ad placements (blocks) per platform with performance metrics
- **Block Daily Summary** — View daily revenue and event breakdowns per block
- **Publisher Balance** — Check your current USDT earnings balance
- **Transaction History** — View deposit and withdrawal records
- **Withdraw Earnings** — Submit withdrawals to your external wallet (min 10 USDT, currently free)

## Get Started

### Step 1 — Install the Skill

**OpenClaw**
```bash
claw install github:Pea-AI/skills-hub/publisher
```

**Claude Code**
```bash
claude install github:Pea-AI/skills-hub/publisher
```

**Manual**
```bash
git clone https://github.com/Pea-AI/skills-hub.git
cp -r skills-hub/publisher .claude/skills/
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

- "Show me all my platforms"
- "What's the revenue for my Telegram bot this week?"
- "Show me the daily breakdown for block xyz"
- "What's my current balance?"
- "Withdraw 50 USDT to my Arbitrum wallet"

---

## Publisher on Ads3

### Platform Types

Publishers register platforms (Telegram bots, web apps, etc.) and create ad placements (blocks) within each platform. Ads3 serves ads into these blocks and pays publishers based on the agreed billing model.

### Billing Allocation Modes

| Mode | Description |
|------|-------------|
| dynamic | Percentage share of ad revenue (e.g. 70% of CPC/CPA earnings) |
| fixed | Fixed USDT amount per impression (CPM) |

### Revenue Settlement

- Revenue is settled **T+1**: today's earnings are credited to your account the following day
- Minimum withdrawal: **10 USDT**
- Current withdrawal fee: **0 USDT** (free)

### Supported Withdrawal Chains

- **Arbitrum**
- **BNB Chain**
- **Tron**
- **TON Network**

---

## Platform Status Reference

| Status | Description |
|--------|-------------|
| onGoing | Running, receiving ads |
| paused | Paused by user |
| auditing | Under review |
| fail | Review failed |

---

## Supported API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/publisher/platforms` | List platforms with metrics |
| GET | `/publisher/platform/:id` | Platform details |
| GET | `/publisher/blocks` | List blocks for a platform |
| GET | `/publisher/block/summary/:id` | Daily block performance |
| GET | `/user/asset/publisher` | Publisher earnings balance |
| GET | `/user/asset/advertiser/flow` | Transaction history (deposit/withdraw) |
| POST | `/withdraw/basic` | Withdrawal config (min, fee, chains) |
| POST | `/withdraw` | Submit a withdrawal |

**API Base URL**: `https://app.ads3.ai/api/v2`

---

## Metrics Reference

| Metric | Formula |
|--------|---------|
| CTR (Click-Through Rate) | clicks / impressions × 100% |
| CVR (Conversion Rate) | conversions / clicks × 100% |
| eCPM (Effective CPM) | earn / impressions × 1000 |

> **Tip**: If CTR < 1%, consider optimizing your ad placement position or size. If eCPM is low, try joining higher-value marketplaces.

---

## Glossary

- **Platform** — Your Telegram bot, web app, or other channel registered on Ads3
- **Block** — An individual ad placement slot within a platform
- **Impressions** — Number of times an ad is displayed (counted after 2+ seconds with 50%+ viewability)
- **Clicks** — Number of times an ad is clicked
- **Earn** — Revenue earned in USDT
- **T+1 Settlement** — Today's revenue is credited to your account tomorrow

---

## Security

- **Never share your Open API Key** — Keep it confidential
- **Keys are shown only once** — Save immediately after creation
- **Revoke compromised keys** — Delete and create a new one if exposed

---

## Links

- [Ads3 Dashboard](https://app.ads3.ai)
- [API Documentation](https://docs.ads3.ai/)
- [Publisher Introduction](https://docs.ads3.ai/publisher/introduction.html)
- [GitHub Repository](https://github.com/Pea-AI/skills-hub)
- [Support — Telegram: @juna_CC](https://t.me/juna_CC) — Need to expedite your withdrawal? Contact our official specialist through this account

---

## Changelog

### v1.0.0 — 2026-04-14

- Initial release
- Platform list with performance metrics (impressions, clicks, conversions, earnings)
- Block list with daily summary
- Publisher earnings balance query
- Transaction history (deposit and withdrawal records)
- Withdrawal submission with config lookup
- Open API Key authentication via `open-api-key` header
