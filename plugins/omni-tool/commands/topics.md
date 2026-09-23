---
name: omni-tool:topics
description: Browse the local index of 69 GalaChain SDK topics
arguments:
  - name: category
    description: "Optional topic category; omit to show all categories"
    required: false
  - name: format
    description: "Output format: list, detailed, or tree"
    required: false
---

# GalaChain Topics

Browse the local index of 69 topics by category. Fetch current material with `gala_launchpad_explain_sdk_usage`.

The tool’s `topic` enum is the live source of truth. Honor its exact current values, including topics added by a newer server even when this file lags. Do not reject a live topic because it is absent here.

## Topics by category

### AI Moderation

- `ai-moderation`

### API Keys

- `api-key-management`

### Authentication

- `session-auth`

### Balances

- `balances`
- `profile-management`

### Bans

- `ban-management`

### Bridging

- `bridge-operations`
- `wrap-unwrap-operations`

### Chat

- `event-subscriptions`
- `gdex-stream`
- `global-feed-subscription`
- `stream-chat`

### Chat Messages

- `chat-messages`

### Comments

- `comments`

### Content Flags

- `content-flag-management`

### Content Reactions

- `content-reactions`

### DEX

- `advanced-dex-analysis`
- `dex-trading`
- `queued-swap-recovery`

### DEX Analytics

- `fetch-all-dex-seasons`
- `fetch-current-dex-leaderboard`
- `fetch-current-dex-season`
- `fetch-dex-aggregated-volume-summary`
- `fetch-dex-leaderboard-by-season-id`

### DEX Liquidity

- `liquidity-positions`

### DEX Pools

- `dex-token-discovery`
- `fetch-dex-pools`

### Locks

- `locks`

### Messages

- `messages`

### Moderators

- `moderator-invites`

### NFTs

- `nft-collection-management`

### Notifications

- `notifications`

### OEmbed

- `oembed`

### Overseers

- `global-bans`
- `overseer-invites`

### Platform Stats

- `platform-stats`

### Pools

- `fetch-pools`
- `holders`
- `price-history`
- `spot-prices-smart-routing`
- `token-creation`
- `token-details`
- `token-distribution`
- `token-identification`
- `utilities-and-helpers`

### Referrals

- `referral-system`

### Restricted Names

- `restricted-names`

### Streaming

- `streaming`

### Token Bans

- `token-ban-management`

### Trades

- `recent-trades`
- `trade-history`

### Trading

- `buy-tokens`
- `error-handling`
- `local-calculations`
- `mcp-to-sdk-mapping`
- `pool-graduation`
- `sell-tokens`
- `trading-analytics`
- `trading-quotes`

### Transfers

- `transfers`

### Utilities

- `events-tracking`
- `graduation-detection`
- `installation`
- `multi-wallet`
- `token-status`
- `utilities-system`

### Wallet

- `wallet-connect`

### WebSocket Admin

- `websocket-admin`

### Weekly Challenge

- `weekly-challenge`

## Learning paths

- **Token lifecycle:** `token-details` → `token-identification` → `buy-tokens` → `sell-tokens` → `pool-graduation` → `dex-trading`.
- **DEX and liquidity:** `dex-token-discovery` → `fetch-dex-pools` → `dex-trading` → `queued-swap-recovery` → `liquidity-positions`.
- **Community:** `streaming` → `gdex-stream` → `stream-chat` → `chat-messages` → `comments` → `content-flag-management`.
- **Application setup:** `installation` → `wallet-connect` → `multi-wallet` → `mcp-to-sdk-mapping` → `notifications`.

DEX swaps are queued: explain `confirm()` and recovery with `confirmSwap(uniqueKey)`; never resubmit only because confirmation timed out. Launchpad SDK methods are flat, while DEX methods are grouped under `sdk.dex.*`.
