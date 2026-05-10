# Flutter Developer Case Study — Crypto Tracker

## Objective

Build a Flutter application that lists cryptocurrency markets and updates prices in real-time.

The app should fetch market data via REST API and optionally update prices in real-time through a WebSocket connection.

### Evaluated Competencies

- Flutter fundamentals and widget usage
- State management with Provider
- Application architecture design
- Asynchronous data management
- Code organisation and readability

> **Note:** Real-time WebSocket updates are **optional**. The core evaluation is based on the REST API market list and detail screens.

## API

### REST API (Binance Public API)

Returns 24-hour market data for all trading pairs. No API key required.

```
GET https://api.binance.com/api/v3/ticker/24hr
```

Docs: https://binance-docs.github.io/apidocs/spot/en/

### WebSocket Stream

Streams real-time price updates for all trading pairs:

```
wss://stream.binance.com:9443/ws/!miniTicker@arr
```

## Required Features

### 1. Market List

- Display a list of cryptocurrency markets
- Each row must show: **trading pair**, **current price**, **24h price change %**

### 2. Market Search

- Search by trading pair symbol (e.g. `btc` → BTCUSDT, BTCBUSD)
- Filter the list based on user input

### 3. Market Detail Screen

When a market is selected, display:

| Field | API Key |
|-------|---------|
| Trading pair | `symbol` |
| Current price | `lastPrice` |
| 24h price change | `priceChange` |
| 24h change % | `priceChangePercent` |
| 24h high | `highPrice` |
| 24h low | `lowPrice` |
| 24h volume | `volume` |
| Best bid | `bidPrice` |
| Best ask | `askPrice` |

> If WebSocket is implemented, `lastPrice` should update in real-time.

### 4. Real-Time Updates (Optional)

- Market list rows should update live
- Open detail screen should auto-update

### 5. Loading & Error States

- Show a loading indicator while fetching data
- Display clear error messages on API/WebSocket failures
- Provide a retry mechanism (optional)

## Delivery

- GitHub repository with source code
- README with: setup instructions, architecture overview, technical decisions, screenshots
