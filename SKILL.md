---
name: ig-trading
description: Trade stocks, forex, indices, and commodities through natural language. Get market data, manage positions, place orders, analyze portfolios, and monitor account activity on the IG Trading Platform. Use this skill when the user wants to check market prices, research trading instruments, open or close positions, set stop-losses, view account balances, analyze trading performance, or execute any trading-related task.
license: MIT
compatibility: Requires IG Trading account (DEMO or LIVE). Node.js 18+. Works with Claude Desktop via MCP protocol.
metadata:
  version: "1.0.0"
  author: "IG Public API MCP Team"
  category: "finance"
  tags: "trading stocks forex indices commodities markets positions orders portfolio"
---

# IG Trading Skill

Trade financial markets through natural language using the IG Trading Platform API.

## What You Can Do

### Market Research
- **Search markets**: Find trading instruments by name, symbol, or category
- **Get market details**: View spreads, margin requirements, trading hours, and specifications
- **Check prices**: Get real-time bid/ask prices for any instrument
- **View sentiment**: See how other traders are positioned (% long vs short)
- **Historical data**: Retrieve price history for technical analysis

### Position Management
- **View positions**: See all open trades with P&L, margin, and details
- **Close positions**: Exit trades by deal ID or close all positions
- **Modify positions**: Update stop-loss and take-profit levels
- **Partial closes**: Close a portion of an existing position

### Order Execution
- **Place market orders**: Buy or sell at current market price
- **Limit orders**: Set entry price for automatic execution
- **Stop orders**: Enter positions when price reaches a level
- **Confirm trades**: Verify execution with deal references

### Account Management
- **View accounts**: List all trading accounts and balances
- **Check balance**: See available funds, margin, and equity
- **Activity history**: Review recent account activity
- **Transaction history**: Detailed record of all transactions

### Portfolio Analysis
- **Performance metrics**: Calculate returns, win rate, profit factor
- **Risk analysis**: Assess exposure, drawdown, and diversification
- **Position breakdown**: Analyze allocation by market and asset class

## Trading Examples

### Research a Market
```
User: "What's the current price of Tesla?"
→ Searches for TSLA, returns bid/ask price, spread, and daily change

User: "Show me details for Gold"
→ Returns GOLD epic, margin requirements, trading hours, contract specs

User: "What's the sentiment on Bitcoin?"
→ Shows % of traders long vs short, helping gauge market positioning
```

### Execute Trades
```
User: "Buy 1 share of Apple"
→ Places market order for AAPL.US, returns deal confirmation

User: "Set a limit order to buy EUR/USD at 1.0850"
→ Creates working order that triggers when price is reached

User: "Close my Tesla position"
→ Finds and closes the TSLA position, shows realized P&L
```

### Manage Risk
```
User: "Add a stop loss at $150 to my Apple position"
→ Updates the position with a protective stop

User: "What are my open positions?"
→ Lists all trades with entry price, current P&L, and margin used

User: "Move my Bitcoin take-profit to $75,000"
→ Modifies the limit order on the existing position
```

### Account Monitoring
```
User: "What's my account balance?"
→ Shows available funds, margin in use, total equity, and P&L

User: "Show my recent trades"
→ Displays activity history with timestamps and outcomes

User: "Analyze my portfolio performance"
→ Calculates returns, win rate, average trade, and risk metrics
```

## Available Tools

| Tool | Purpose |
|------|---------|
| `get_accounts` | List all trading accounts with balances |
| `get_markets` | Search for markets by term or EPIC code |
| `get_market_details` | Get detailed specs for a specific market |
| `get_market_sentiment` | View trader positioning data |
| `get_positions` | List all open positions |
| `close_position` | Close a position by deal ID |
| `update_position` | Modify stop-loss or take-profit |
| `get_orders` | View pending working orders |
| `place_order` | Execute market, limit, or stop orders |
| `confirm_trade` | Verify trade execution status |
| `get_activity_history` | Recent account activity |
| `get_transaction_history` | Detailed transaction records |
| `get_price_history` | Historical OHLC price data |
| `analyze_portfolio` | Portfolio performance metrics |

## Market EPICs Reference

Common market identifiers (EPICs) for quick access:

**Forex**
- `CS.D.EURUSD.CFD.IP` - EUR/USD
- `CS.D.GBPUSD.CFD.IP` - GBP/USD
- `CS.D.USDJPY.CFD.IP` - USD/JPY

**Indices**
- `IX.D.SPTRD.IFE.IP` - S&P 500
- `IX.D.DOW.IFE.IP` - Dow Jones
- `IX.D.NASDAQ.IFE.IP` - NASDAQ 100
- `IX.D.FTSE.CFD.IP` - FTSE 100

**Commodities**
- `CS.D.USCGC.TODAY.IP` - Gold
- `CS.D.USCSI.TODAY.IP` - Silver
- `CC.D.CL.UNC.IP` - Crude Oil

**Stocks** (search by company name or ticker)
- US stocks: `{TICKER}.US` format
- AU stocks: `{TICKER}.AU` format

## Important Guidelines

### Safety First
- **Always use DEMO environment** for testing and learning
- **Confirm large orders** before execution
- **Set stop-losses** to manage risk on every position
- **Check market hours** - some markets are closed on weekends

### Order Confirmation
When placing trades, always confirm:
1. The correct instrument (EPIC)
2. Direction (BUY or SELL)
3. Size (number of contracts/shares)
4. Order type (market, limit, stop)
5. Stop-loss and take-profit levels

### Error Handling
- **Insufficient funds**: Check available margin before trading
- **Market closed**: Verify trading hours for the instrument
- **Invalid size**: Ensure order size meets minimum requirements
- **Rate limits**: IG API has request limits (handled automatically)

## Environment Modes

### DEMO Mode (Recommended for Learning)
- Virtual money trading
- Real market prices
- No financial risk
- Full feature access

### LIVE Mode (Real Money)
- Actual trading with real funds
- All profits and losses are real
- Requires verified IG account
- Use with caution

## Session Management

- Sessions automatically refresh every 5 minutes
- Credentials are encrypted with AES-256-GCM
- Multi-layer rate limiting protects against overuse
- Session tokens cached for performance

## Getting Help

If a trade fails or you encounter issues:
1. Check your account balance and available margin
2. Verify the market is open for trading
3. Confirm the EPIC code is correct
4. Review any error messages for specific guidance

For IG platform issues, visit: https://labs.ig.com/
