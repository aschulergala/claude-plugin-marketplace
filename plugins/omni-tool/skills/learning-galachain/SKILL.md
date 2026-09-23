---
name: learning-galachain
description: Learn to build on GalaChain with the v7 SDK and indexed topics
triggers:
  - "How do I learn GalaChain?"
  - "Teach me about GalaChain"
  - "What can I build with GalaChain?"
  - "How does this teaching system work?"
  - "I want to learn GalaChain from scratch"
  - "Show me the learning roadmap"
  - "What are all the things I can do?"
---

# Learning GalaChain

Use `gala_launchpad_explain_sdk_usage` to get current SDK methods, examples, corresponding MCP tools, pitfalls, and related topics. Its `topic` enum is the live source of truth for topic names. Follow the live enum when it contains topics newer than this local index. `/omni-tool:topics` and `/omni-tool:ask` are local guides and do not override the connected server.

The local index includes 69 topics across trading, pools, balances, token operations, DEX, DEX analytics, bridging, streaming and chat, community moderation, governance, wallet and auth, utilities, referrals, trade history, and NFTs.

## Learning paths

### Trading and token lifecycle

1. Start with `token-details` and `token-identification`.
2. Learn `buy-tokens`, `sell-tokens`, `trading-quotes`, and `trading-analytics`.
3. Follow `pool-graduation` and `graduation-detection` to choose the correct trading surface.
4. Use `dex-trading` and `queued-swap-recovery` for DEX trades and uncertain outcomes.

### DEX and liquidity

1. Discover markets with `dex-token-discovery` and `fetch-dex-pools`.
2. Learn `dex-trading`, `liquidity-positions`, and `advanced-dex-analysis`.
3. Use `spot-prices-smart-routing` and DEX analytics topics for price and activity context.

### Build and operate tokens

1. Study `token-creation`, `token-status`, `transfers`, and `locks`.
2. Review `balances`, `token-distribution`, `holders`, and `price-history`.
3. Use `bridge-operations` or `wrap-unwrap-operations` when workflows cross networks.

### Streaming and community

1. Start with `streaming`, `gdex-stream`, and `stream-chat`.
2. Explore `chat-messages`, `comments`, and `messages` for community content.
3. Learn `content-flag-management`, `content-reactions`, `ban-management`, and `moderator-invites` for moderation.

### Application integration

Start with `installation`, `wallet-connect`, `multi-wallet`, and `mcp-to-sdk-mapping`. Continue with `event-subscriptions`, `notifications`, `utilities-and-helpers`, and `error-handling` as needed.

## v7 SDK patterns

Launchpad methods are flat on the SDK, including `sdk.buy()`, `sdk.sell()`, `sdk.launchToken()`, and `sdk.transferToken()`. GSwap is grouped under `sdk.dex.quoting`, `sdk.dex.swaps`, `sdk.dex.positions`, `sdk.dex.pools`, `sdk.dex.assets`, and `sdk.dex.symbols`.

A DEX `swap()` queues a submission. Call its `confirm()` to resolve the result. After a timeout or restart, call `confirmSwap(uniqueKey)` with the original key; do not submit a second swap only because confirmation is uncertain. Use live examples for exact signatures and result handling.

## Learn safely

Explore with read-only examples first. Before any write, explain its effect and confirm the user intends it. Keep private keys outside source code and config. Follow the live example's transaction confirmation and recovery flow.

## Commands

- `/omni-tool:ask [question or topic]` fetches focused teaching content.
- `/omni-tool:topics` browses the local topic index.
- `/omni-tool:setup` configures the MCP connection and learning preferences.
