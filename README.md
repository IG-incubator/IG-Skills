# IG Skills

Structured skill definitions for AI agents to interact with the IG Trading Platform REST API.

## Overview

This repository contains skill specifications that enable AI agents to interpret natural language requests and execute corresponding IG API operations.

```
Input:    "Buy 1 share of Tesla"
Skill:    spot
Endpoint: POST /positions/otc
Payload:  {epic: "TSLA.US", direction: "BUY", size: 1}
Output:   "Bought 1 Tesla share at $248.50"
```

## Available Skills

| Skill | Description |
|-------|-------------|
| [spot](skills/ig/spot/) | Position and order management |
| [market-data](skills/ig/market-data/) | Market search, pricing, and sentiment |
| [account](skills/ig/account/) | Account balances and transaction history |
| [watchlist](skills/ig/watchlist/) | Watchlist management |

## Repository Structure

```
skills/ig/
├── spot/
│   ├── SKILL.md
│   └── LICENSE.md
├── market-data/
├── account/
└── watchlist/
```

Each `SKILL.md` contains:
- YAML frontmatter (name, description, version, author)
- Tool definitions with corresponding API endpoints
- Parameter specifications and types
- Usage examples

## Example Mappings

The `market-data` skill translates the following:

| Natural Language | API Endpoint |
|------------------|--------------|
| "What is the price of Gold?" | `GET /markets?searchTerm=Gold` |
| "Show EUR/USD details" | `GET /markets/CS.D.EURUSD.CFD.IP` |
| "Get daily candles for Bitcoin" | `GET /prices/{epic}/DAY` |
| "What is sentiment on the S&P 500?" | `GET /clientsentiment/{marketId}` |

## Integration

Refer to [AGENTS.md](AGENTS.md) for:
- Authentication procedures
- Framework integration (MCP, LangChain, CrewAI)
- Security requirements
- Rate limits and error handling

## Requirements

- IG Trading account ([Demo](https://www.ig.com/au/demo-account) or Live)
- API credentials from [IG Labs](https://labs.ig.com/)

## Contributing

1. Fork the repository and create a feature branch
2. Add `SKILL.md` and `LICENSE.md` to a new skill folder
3. Follow the existing skill format and naming conventions
4. Submit a pull request for review

## Disclaimer

This repository is provided for informational purposes only and does not constitute financial advice. Trading CFDs and spread bets carries risk. Users are solely responsible for their trading decisions. Refer to [IG.com](https://www.ig.com) for full terms and risk disclosures.

## License

MIT
