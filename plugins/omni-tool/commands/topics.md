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

Browse the local index of 69 v7 learning topics by category, learning path, or use case. Use `gala_launchpad_explain_sdk_usage` for current content. Its `topic` enum is the live source of truth: honor exact values from the connected server, including topics added after this file was published.

## Usage

```text
/omni-tool:topics
/omni-tool:topics trading
/omni-tool:topics dex --format=detailed
/omni-tool:topics --format=tree
```

`list` is the compact default, `detailed` adds descriptions and related topics, and `tree` groups the full index. If the caller cannot filter locally, show the requested section and direct the user to the live enum for newer entries.

## Topics by category

### AI Moderation
`ai-moderation`

### API Keys
`api-key-management`

### Authentication
`session-auth`

### Balances
`balances`, `profile-management`

### Bans
`ban-management`

### Bridging
`bridge-operations`, `wrap-unwrap-operations`

### Chat
`event-subscriptions`, `gdex-stream`, `global-feed-subscription`, `stream-chat`

### Chat Messages
`chat-messages`

### Comments
`comments`

### Content Flags
`content-flag-management`

### Content Reactions
`content-reactions`

### DEX
`advanced-dex-analysis`, `dex-trading`, `queued-swap-recovery`

### DEX Analytics
`fetch-all-dex-seasons`, `fetch-current-dex-leaderboard`, `fetch-current-dex-season`, `fetch-dex-aggregated-volume-summary`, `fetch-dex-leaderboard-by-season-id`

### DEX Liquidity
`liquidity-positions`

### DEX Pools
`dex-token-discovery`, `fetch-dex-pools`

### Locks
`locks`

### Messages
`messages`

### Moderators
`moderator-invites`

### NFTs
`nft-collection-management`

### Notifications
`notifications`

### OEmbed
`oembed`

### Overseers
`global-bans`, `overseer-invites`

### Platform Stats
`platform-stats`

### Pools
`fetch-pools`, `holders`, `price-history`, `spot-prices-smart-routing`, `token-creation`, `token-details`, `token-distribution`, `token-identification`, `utilities-and-helpers`

### Referrals
`referral-system`

### Restricted Names
`restricted-names`

### Streaming
`streaming`

### Token Bans
`token-ban-management`

### Trades
`recent-trades`, `trade-history`

### Trading
`buy-tokens`, `error-handling`, `local-calculations`, `mcp-to-sdk-mapping`, `pool-graduation`, `sell-tokens`, `trading-analytics`, `trading-quotes`

### Transfers
`transfers`

### Utilities
`events-tracking`, `graduation-detection`, `installation`, `multi-wallet`, `token-status`, `utilities-system`

### Wallet
`wallet-connect`

### WebSocket Admin
`websocket-admin`

### Weekly Challenge
`weekly-challenge`

## Learning paths

All names below are from `topics-v7.tsv`. Follow the connected server's current enum if it adds or renames topics.

### Path 1: Token lifecycle and trading

1. `token-details` → `token-identification` to understand what the app is trading.
2. `buy-tokens` → `sell-tokens` for bonding-curve trades.
3. `trading-quotes` → `trading-analytics` to reason about expected output and activity.
4. `pool-graduation` → `graduation-detection` → `token-status` to follow a token's state.
5. `dex-token-discovery` → `fetch-dex-pools` → `dex-trading` for DEX markets.
6. `queued-swap-recovery` → `error-handling` for uncertain submission outcomes.

### Path 2: DEX and liquidity

1. `dex-token-discovery` → `fetch-dex-pools` to find pools.
2. `spot-prices-smart-routing` → `advanced-dex-analysis` to evaluate price and pool context.
3. `dex-trading` → `queued-swap-recovery` to learn submission, confirmation, and recovery.
4. `liquidity-positions` to understand positions and liquidity workflows.
5. `fetch-current-dex-season` → `fetch-current-dex-leaderboard` → `fetch-dex-aggregated-volume-summary` for current analytics.

### Path 3: Token creation and operation

1. `restricted-names` → `token-creation` for name checks and launch.
2. `token-details` → `token-status` → `fetch-pools` for discovery.
3. `balances` → `token-distribution` → `holders` for ownership views.
4. `transfers` → `locks` for token operations.
5. `pool-graduation` → `graduation-detection` → `dex-trading` for the post-graduation transition.

### Path 4: Bridge and wrap

1. `bridge-operations` for bridge routes, fees, and tracking.
2. `wrap-unwrap-operations` for cross-channel wrapping.
3. `wallet-connect` → `error-handling` for signer and failure context.

Check bridge requirements in the live topic. Solana paths may require `SOLANA_PRIVATE_KEY`; the MCP server also supports optional `ETHEREUM_RPC_URL` and `SOLANA_RPC_URL` overrides.

### Path 5: Streaming and community

1. `streaming` → `gdex-stream` for stream lifecycle and updates.
2. `stream-chat` → `chat-messages` → `messages` for conversation features.
3. `comments` → `content-reactions` → `content-flag-management` for community content.
4. `ban-management` → `token-ban-management` → `moderator-invites` for moderation.
5. `ai-moderation` → `global-feed-subscription` for moderation and event context.

### Path 6: Application integration

1. `installation` → `mcp-to-sdk-mapping` for server and method orientation.
2. `wallet-connect` → `multi-wallet` → `session-auth` for account handling.
3. `event-subscriptions` → `notifications` → `events-tracking` for event-driven features.
4. `api-key-management` → `websocket-admin` for privileged integration needs.
5. Continue with `platform-stats`, `oembed`, `referral-system`, and `nft-collection-management` where they fit the product.

## Quick reference by use case

- **Trade a token:** `token-identification` → `buy-tokens` / `sell-tokens` → `pool-graduation` → `dex-trading`.
- **Provide liquidity:** `fetch-dex-pools` → `advanced-dex-analysis` → `liquidity-positions`.
- **Recover an uncertain swap:** `queued-swap-recovery` → `error-handling`.
- **Launch a token:** `restricted-names` → `token-creation` → `token-details` → `pool-graduation`.
- **Bridge assets:** `bridge-operations` → `wrap-unwrap-operations`.
- **Build community features:** `streaming` → `stream-chat` → `chat-messages` → `comments` → `content-flag-management`.

## How to read a topic answer

A focused topic answer should provide:

- **What it does** and where it fits in the GalaChain lifecycle.
- **When to use it**, including network, identity, and wallet prerequisites.
- **How it works**, preferably as ordered steps.
- **SDK example** from the live tool when examples are requested, with the equivalent MCP tool names.
- **Key parameters and trade-offs**, such as amount type, fees, slippage, token identifier, or position range.
- **Common pitfalls and recovery**, including v7-specific behavior.
- **Related topics** using exact values from the live enum.

For DEX swaps, explain that `swap()` queues work, `confirm()` resolves it, and `confirmSwap(uniqueKey)` recovers the original operation after interruption. Do not recommend submitting another swap to resolve uncertainty. Launchpad methods are flat, while GSwap DEX methods are grouped under `sdk.dex.*`; use the live v7 example for exact signatures.

## Difficulty guide

- **Beginner:** core ideas and read workflows; start with `installation`, `token-details`, `fetch-pools`, and `balances`.
- **Intermediate:** multiple related concepts or a write workflow; continue to `buy-tokens`, `token-creation`, `bridge-operations`, or `liquidity-positions`.
- **Advanced:** recovery, analysis, or privileged capabilities; study `queued-swap-recovery`, `advanced-dex-analysis`, `websocket-admin`, and `api-key-management` as needed.

## Use the index

Choose a learning path, then ask `/omni-tool:ask [topic]` for current content. Start with read topics and use `stage` when trying a workflow. The server accepts only `prod` or `stage`, defaults to `prod` when unset, and requires `PRIVATE_KEY` in its process environment for writes. The live topic enum wins whenever this local index is behind.
