# IG REST API Reference

## Base URLs

| Environment | URL |
|-------------|-----|
| DEMO | `https://demo-api.ig.com/gateway/deal` |
| LIVE | `https://api.ig.com/gateway/deal` |

## Authentication

All requests require:
- `X-IG-API-KEY`: Your API key
- `CST`: Client session token
- `X-SECURITY-TOKEN`: Account session token

## Endpoints

### Session

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/session` | Create session |
| DELETE | `/session` | Logout |

### Accounts

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/accounts` | List accounts |
| GET | `/accounts/preferences` | Account preferences |

### Markets

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/markets?searchTerm={term}` | Search markets |
| GET | `/markets/{epic}` | Market details |
| GET | `/clientsentiment/{marketId}` | Market sentiment |

### Positions

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/positions` | List positions |
| POST | `/positions/otc` | Open position |
| PUT | `/positions/otc/{dealId}` | Update position |
| DELETE | `/positions/otc/{dealId}` | Close position |

### Working Orders

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/workingorders` | List orders |
| POST | `/workingorders/otc` | Create order |
| PUT | `/workingorders/otc/{dealId}` | Update order |
| DELETE | `/workingorders/otc/{dealId}` | Delete order |

### History

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/history/activity` | Activity history |
| GET | `/history/transactions` | Transaction history |

### Prices

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/prices/{epic}` | Historical prices |

## Rate Limits

- Trading: 1 request per second
- Non-trading: 30 requests per minute

## Documentation

Full API documentation: https://labs.ig.com/rest-trading-api-reference
