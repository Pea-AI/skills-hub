# Ads3 Skills Hub

Ads3 Skills Hub is an open skills marketplace that gives AI agents native access to Web3 advertising ecosystem. It enables AI-powered management of ad campaigns, traffic monetization, and performance analytics.

## Get Started

Get started in a single command. Works with [OpenClaw](https://github.com/anthropics/open-claw), [Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview), [Codex](https://github.com/openai/codex), and other AI coding agents.

### OpenClaw

```bash
claw install github:Pea-AI/skills-hub
```

### Claude Code

```bash
claude install github:Pea-AI/skills-hub
```

### Codex

```bash
codex install github:Pea-AI/skills-hub
```

### Manual Installation

```bash
# Clone the repository
git clone https://github.com/Pea-AI/skills-hub.git

# Copy skills to your project
cp -r skills-hub/advertiser .claude/skills/
```

## Available Skills

| Skill | Description | Authentication |
|-------|-------------|----------------|
| [advertiser](./advertiser) | Manage ad campaigns, query performance data, create/pause/resume ads | Open API Key |

## Authentication

Before using Ads3 Skills Hub, you need to provide API credentials.

### Getting Your Open API Key

1. Login to [Ads3 Dashboard](https://app.ads3.ai)
2. Navigate to **Account** → **Open API Keys**
3. Click **Create Open API Key**
4. Copy and save your Open API key securely (only shown once)

### Open API Key Format

```
sk_live_xxxx...xxxx
```

### Using the Open API Key

Add the `open-api-key` header to your requests:

```bash
curl -X GET 'https://app.ads3.ai/api/v2/advertiser/campaigns' \
  -H 'open-api-key: sk_live_xxxx...xxxx'
```

## Skills Overview

### Advertiser Skill

Manage your advertising campaigns with AI assistance:

- **Query Campaigns** - Get campaign list with performance metrics (impressions, clicks, conversions, CTR, CVR)
- **Campaign Details** - View detailed campaign configuration and daily summaries
- **Create Campaigns** - Create new ad campaigns with targeting and budget settings
- **Manage Campaigns** - Pause, resume, or end campaigns
- **Performance Analysis** - Analyze campaign performance and get optimization suggestions

**Example Prompts:**
- "Show me all my active campaigns"
- "What's the CTR for my Spring Campaign?"
- "Pause campaign ID xyz123"
- "Create a new CPC campaign targeting Southeast Asia"

## API Base URL

```
https://app.ads3.ai/api/v2
```

## Supported Endpoints

### Advertiser APIs

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

## Compatibility

Ads3 Skills Hub is compatible with:

- [OpenClaw](https://github.com/anthropics/open-claw) by Anthropic
- [Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview) by Anthropic
- [Codex](https://github.com/openai/codex) by OpenAI
- [Cursor](https://cursor.sh/)
- [Gemini CLI](https://github.com/google-gemini/gemini-cli)
- Other AI coding agents supporting the skills format

## Security Notes

- **Never share your Open API Key** - Keep it confidential
- **Open API Keys are shown only once** - Save immediately after creation
- **Revoke compromised keys** - Delete and create new ones if exposed
- **Use environment variables** - Don't hardcode keys in your code

## Contributing

We welcome contributions! Please feel free to submit issues and pull requests.

## Disclaimer

Ads3 Skills Hub is an informational tool only, provided on an "as is" and "as available" basis without warranty. It does not constitute investment, financial, trading, or any other form of advice. Users are responsible for their own decisions and actions when using this tool.

## License

MIT License

## Links

- [Ads3 Dashboard](https://app.ads3.ai)
- [API Documentation](https://docs.ads3.ai/)
- [GitHub Repository](https://github.com/Pea-AI/skills-hub)
