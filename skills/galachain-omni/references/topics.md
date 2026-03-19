# GalaChain Topics

Use this file to map natural-language user requests to GalaChain topics and learning paths.

## Trading

| Topic | Difficulty | Description |
| --- | --- | --- |
| `buy-tokens` | Beginner | Purchase tokens on bonding curves |
| `sell-tokens` | Beginner | Sell tokens on bonding curves |
| `pool-graduation` | Intermediate | Transition a token from bonding curve to DEX |
| `error-handling` | Intermediate | Recover from common GalaChain errors |
| `local-calculations` | Intermediate | Use local computation methods |
| `trading-analytics` | Beginner | Analyze trading behavior and metrics |
| `trading-quotes` | Intermediate | Estimate buy or sell cost |

## Pools And Token Info

| Topic | Difficulty | Description |
| --- | --- | --- |
| `fetch-pools` | Beginner | Query and filter token pools |
| `token-details` | Beginner | Inspect token metadata and verification state |
| `token-distribution` | Beginner | Analyze token holder distribution |
| `price-history` | Beginner | Fetch historical price data |
| `token-identification` | Intermediate | Understand token naming and identifiers |
| `holders` | Beginner | Inspect holder lists and distribution |

## Balances And Accounts

| Topic | Difficulty | Description |
| --- | --- | --- |
| `balances` | Beginner | Query balances and portfolios |
| `profile-management` | Beginner | Work with user profiles |

## Token Operations

| Topic | Difficulty | Description |
| --- | --- | --- |
| `token-creation` | Intermediate | Launch new tokens with bonding curves |
| `token-status` | Beginner | Inspect supply and status |
| `transfers` | Beginner | Send tokens |
| `locks` | Intermediate | Lock and unlock tokens |

## DEX Trading

| Topic | Difficulty | Description |
| --- | --- | --- |
| `dex-trading` | Intermediate | Execute DEX swaps and quotes |
| `dex-token-discovery` | Beginner | Find tokens trading on the DEX |

## DEX Pools And Liquidity

| Topic | Difficulty | Description |
| --- | --- | --- |
| `fetch-dex-pools` | Beginner | Discover DEX pools |
| `liquidity-positions` | Advanced | Manage LP positions |
| `advanced-dex-analysis` | Advanced | Analyze pool data in depth |

## DEX Analytics

| Topic | Difficulty | Description |
| --- | --- | --- |
| `fetch-all-dex-seasons` | Beginner | List all DEX seasons |
| `fetch-current-dex-season` | Beginner | Inspect the current season |
| `fetch-dex-leaderboard-by-season-id` | Beginner | View season leaderboards |
| `fetch-current-dex-leaderboard` | Beginner | View the active leaderboard |
| `fetch-dex-aggregated-volume-summary` | Beginner | Summarize trading volume |
| `weekly-challenge` | Beginner | Inspect weekly challenge leaderboards |

## Bridging

| Topic | Difficulty | Description |
| --- | --- | --- |
| `bridge-operations` | Intermediate | Bridge assets to Ethereum or Solana |
| `wrap-unwrap-operations` | Advanced | Wrap or unwrap cross-channel tokens |

## Streaming And Chat

| Topic | Difficulty | Description |
| --- | --- | --- |
| `streaming` | Beginner | RTMP streaming, recordings, and simulcast |
| `stream-chat` | Beginner | Real-time chat integration |
| `messages` | Intermediate | Unified messages API |

## Community And Moderation

| Topic | Difficulty | Description |
| --- | --- | --- |
| `ban-management` | Intermediate | Ban and unban users |
| `global-bans` | Intermediate | Platform-wide bans |
| `content-flag-management` | Intermediate | Moderate flagged content |
| `content-reactions` | Beginner | Manage reactions |
| `moderator-invites` | Intermediate | Manage moderators |
| `token-ban-management` | Intermediate | Manage token-level bans |
| `ai-moderation` | Advanced | Configure or inspect AI moderation |
| `global-feed-subscription` | Intermediate | Subscribe to platform-wide feeds |

## Governance And Admin

| Topic | Difficulty | Description |
| --- | --- | --- |
| `overseer-invites` | Advanced | Platform governance flows |
| `api-key-management` | Beginner | Manage API credentials |
| `event-subscriptions` | Advanced | Subscribe to real-time events |
| `restricted-names` | Advanced | Administer restricted token names |
| `websocket-admin` | Advanced | Use admin WebSocket emit tools |

## Wallet And Auth

| Topic | Difficulty | Description |
| --- | --- | --- |
| `multi-wallet` | Beginner | Manage multiple wallets |
| `session-auth` | Intermediate | JWT authentication and sessions |

## Utilities And Reference

| Topic | Difficulty | Description |
| --- | --- | --- |
| `installation` | Beginner | SDK and MCP setup guide |
| `spot-prices-smart-routing` | Intermediate | Spot prices and route selection |
| `utilities-and-helpers` | Intermediate | Helper utilities |
| `utilities-system` | Beginner | System utilities |
| `mcp-to-sdk-mapping` | Beginner | Map MCP tools to SDK methods |
| `graduation-detection` | Intermediate | Detect graduation events |
| `platform-stats` | Beginner | Platform-wide metrics |
| `oembed` | Beginner | OEmbed endpoints |
| `events-tracking` | Intermediate | Event batching and analytics ingestion |

## Referrals, Trade History, And NFTs

| Topic | Difficulty | Description |
| --- | --- | --- |
| `referral-system` | Beginner | Track referrals |
| `trade-history` | Beginner | Query trade history |
| `recent-trades` | Beginner | Query recent trades across tokens |
| `nft-collection-management` | Advanced | Create collections and mint NFTs |

## Learning Paths

### Trading Essentials

1. `token-details`
2. `buy-tokens`
3. `sell-tokens`
4. `trading-analytics`
5. `pool-graduation`

### Liquidity Management

1. `fetch-dex-pools`
2. `liquidity-positions`
3. `advanced-dex-analysis`
4. `fetch-all-dex-seasons`

### DEX Swapping

1. `dex-token-discovery`
2. `dex-trading`
3. `spot-prices-smart-routing`

### Bridging

1. `bridge-operations`
2. `wrap-unwrap-operations`

### Streaming And Community

1. `streaming`
2. `stream-chat`
3. `ban-management`
4. `moderator-invites`

### Token Launch

1. `token-creation`
2. `token-status`
3. `token-distribution`
4. `pool-graduation`

## Quick Routing

- "I want to buy or sell a token" -> `buy-tokens`, `sell-tokens`
- "I want to launch a token" -> `token-creation`
- "I want to add liquidity" -> `liquidity-positions`
- "I want to bridge to Ethereum or Solana" -> `bridge-operations`
- "I want streaming with chat" -> `streaming`, `stream-chat`
- "I need moderation or bans" -> `ban-management`, `content-flag-management`, `moderator-invites`
- "I need analytics or leaderboards" -> `trading-analytics`, `fetch-current-dex-leaderboard`, `platform-stats`
