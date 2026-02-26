---
name: omni-tool:topics
description: List all 59 teaching topics organized by category
arguments:
  - name: category
    description: "Filter by category (trading, pools, balances, token-ops, dex, dex-pools, dex-analytics, bridge, streaming, community, governance, wallet, utils, referrals, trades, nft, or 'all'). Includes messages, holders, restricted-names, websocket-admin, platform-stats, oembed, ai-moderation, weekly-challenge."
    required: false
  - name: format
    description: "Output format: list (default), detailed, or tree"
    required: false
---

# GalaChain Topics Command

Browse all 59 teaching topics organized by domain. Each topic includes:
- **Description** - What this feature does
- **Difficulty** - Beginner, intermediate, or advanced
- **Prerequisites** - Recommended topics to learn first
- **MCP Tools** - Number of available MCP tools for this topic

## Usage

```bash
# List all topics
/omni-tool:topics

# Filter by category
/omni-tool:topics trading
/omni-tool:topics dex-pools
/omni-tool:topics bridge

# Different formats
/omni-tool:topics --format=detailed
/omni-tool:topics --format=tree
/omni-tool:topics trading --format=detailed
```

## All Topics by Category

### 🏪 Trading (6 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `buy-tokens` | Beginner | Purchase tokens on bonding curves | 2 |
| `sell-tokens` | Beginner | Sell tokens on bonding curves | 2 |
| `pool-graduation` | Intermediate | Transition from bonding curve to DEX | 2 |
| `error-handling` | Intermediate | Error recovery patterns | 1 |
| `local-calculations` | Intermediate | Local computation methods | 4 |
| `trading-analytics` | Beginner | Trading analytics and metrics | 2 |

### 🔍 Pools & Token Info (6 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `fetch-pools` | Beginner | Query and filter token pools | 9 |
| `token-details` | Beginner | Token metadata and verification | 1 |
| `token-distribution` | Beginner | Token holder analysis | 2 |
| `price-history` | Beginner | Historical price data | 2 |
| `token-identification` | Intermediate | Token format concepts (tokenName vs tokenClassKey) | 3 |
| `holders` | Beginner | Token holder lists and distribution | 3 |

### 💰 Balances & Accounts (3 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `balances` | Beginner | Balance queries and portfolio | 5 |
| `profile-management` | Beginner | User profile operations | 4 |
| `account-management` | Beginner | Account registration and management | 1 |

### 🎫 Token Operations (4 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `token-creation` | Intermediate | Launch new tokens with bonding curves | 3 |
| `token-status` | Beginner | Token supply and status | 3 |
| `transfers` | Beginner | Send tokens to addresses | 2 |
| `locks` | Intermediate | Lock/unlock tokens | 3 |

### 🔄 DEX Trading (2 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `dex-trading` | Intermediate | DEX swaps and quotes | 6 |
| `dex-token-discovery` | Beginner | Find tokens trading on DEX | 2 |

### 💧 DEX Pools & Liquidity (3 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `fetch-dex-pools` | Beginner | DEX pool discovery | 2 |
| `liquidity-positions` | Advanced | LP position management | - |
| `advanced-dex-analysis` | Advanced | Advanced pool analysis | 1 |

### 📊 DEX Analytics (6 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `fetch-all-dex-seasons` | Beginner | All DEX seasons data | 1 |
| `fetch-current-dex-season` | Beginner | Current season info | 1 |
| `fetch-dex-leaderboard-by-season-id` | Beginner | Season leaderboards | 1 |
| `fetch-current-dex-leaderboard` | Beginner | Current leaderboard | 1 |
| `fetch-dex-aggregated-volume-summary` | Beginner | Volume analytics | 1 |
| `weekly-challenge` | Beginner | Weekly challenge leaderboards and token history | 3 |

### 🌉 Bridging (2 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `bridge-operations` | Intermediate | All bridge operations (Ethereum, Solana, fees, status) | 15 |
| `wrap-unwrap-operations` | Advanced | Cross-channel token wrapping | 10 |

### 📡 Streaming & Chat (3 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `streaming` | Beginner | RTMP streaming, recordings, simulcast | 14 |
| `stream-chat` | Beginner | Real-time chat integration (REST + WebSocket) | 7 |
| `messages` | Intermediate | Unified messages API (fetch, create, update, pin) | 5 |

### 🛡️ Community & Moderation (6 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `ban-management` | Intermediate | Ban/unban users | 5 |
| `content-flag-management` | Intermediate | Content moderation | 5 |
| `content-reactions` | Beginner | Reaction management | 6 |
| `moderator-invites` | Intermediate | Moderator management | 6 |
| `token-ban-management` | Intermediate | Token-level bans | 5 |
| `ai-moderation` | Advanced | AI content moderation config and results | 4 |

### ⚡ Governance & Admin (5 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `overseer-invites` | Advanced | Platform governance | 8 |
| `api-key-management` | Beginner | API credentials | 6 |
| `event-subscriptions` | Advanced | Real-time event monitoring | 4 |
| `restricted-names` | Advanced | Restricted token name management (admin) | 4 |
| `websocket-admin` | Advanced | WebSocket admin emit tools | 4 |

### 🔑 Wallet & Auth (2 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `multi-wallet` | Beginner | Multi-wallet management | 1 |
| `session-auth` | Intermediate | JWT authentication | 8 |

### 🔧 Utilities & Reference (8 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `installation` | Beginner | SDK setup guide | 1 |
| `spot-prices-smart-routing` | Intermediate | Price routing | 1 |
| `utilities-and-helpers` | Intermediate | Helper functions | 8 |
| `utilities-system` | Beginner | System utilities | 8 |
| `mcp-to-sdk-mapping` | Beginner | MCP-to-SDK method mapping | 1 |
| `graduation-detection` | Intermediate | Detect token graduation | 4 |
| `platform-stats` | Beginner | Platform-wide statistics and metrics | 2 |
| `oembed` | Beginner | OEmbed embeds for pools, profiles, home | 3 |

### 🎁 Referrals (1 topic)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `referral-system` | Beginner | Referral tracking | 4 |

### 📜 Trade History (1 topic)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `trade-history` | Beginner | Trade history queries | 1 |

### 🎨 NFTs (1 topic)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `nft-collection-management` | Advanced | NFT collections and minting | 10 |

## Learning Paths

### Path 1: Token Trading Essentials
1. Start: `token-details` - Understand what tokens are
2. Learn: `buy-tokens` - How to purchase
3. Learn: `sell-tokens` - How to exit
4. Learn: `trading-analytics` - Analyze trades
5. Advanced: `pool-graduation` - Move to DEX

### Path 2: Liquidity Management
1. Start: `fetch-dex-pools` - Find DEX pools
2. Learn: `liquidity-positions` - Add LP positions
3. Learn: `advanced-dex-analysis` - Analyze pool data
4. Advanced: `fetch-all-dex-seasons` - Seasonal analytics

### Path 3: DEX Swapping
1. Start: `dex-token-discovery` - Find tokens
2. Learn: `dex-trading` - Execute swaps
3. Advanced: `spot-prices-smart-routing` - Price routing

### Path 4: Cross-Chain Bridging
1. Start: `bridge-operations` - Bridge to Ethereum & Solana
2. Advanced: `wrap-unwrap-operations` - Token wrapping

### Path 5: Live Streaming & Community
1. Start: `streaming` - Begin streaming (RTMP, recordings, simulcast)
2. Learn: `stream-chat` - Add live chat
3. Learn: `ban-management` - Manage community
4. Advanced: `moderator-invites` - Build mod team

### Path 6: Platform Master
Complete all paths 1-5, then:
1. `token-creation` - Create your own token
2. `nft-collection-management` - Add NFT support
3. `overseer-invites` - Governance
4. `event-subscriptions` - Real-time analytics

## Quick Reference by Use Case

**"I want to trade tokens"**
→ `buy-tokens` → `sell-tokens` → `dex-trading` → `trading-analytics`

**"I want to provide liquidity"**
→ `fetch-dex-pools` → `liquidity-positions` → `advanced-dex-analysis`

**"I want to bridge tokens"**
→ `bridge-operations` → `wrap-unwrap-operations`

**"I want to launch a token"**
→ `token-creation` → `token-details` → `pool-graduation` → `dex-trading`

**"I want to stream live"**
→ `streaming` → `stream-chat` → `ban-management` → `moderator-invites`

**"I want complete mastery"**
→ Start with Path 1 → Continue to Path 5 → Master with Path 6

## Difficulty Levels Explained

### Beginner
- Core concepts and common operations
- Simple 1-3 parameter operations
- Read-only or basic write operations
- No special error handling needed
- Perfect for your first time with GalaChain

### Intermediate
- More complex workflows
- 3-5 parameters with interdependencies
- Requires understanding of related concepts
- Some error conditions to handle
- Good next step after mastering basics

### Advanced
- Complex strategies and optimization
- 5+ parameters with subtle interactions
- Requires deep understanding of DeFi
- Multiple error conditions and recovery paths
- For expert developers building sophisticated apps

## Tips for Learning

### Get Started
1. Pick a use case that excites you
2. Find the recommended learning path
3. Start with beginner topics
4. Use `/omni-tool:ask [topic]` to learn

### Practice
1. After learning theory, execute with MCP tools
2. Start small (small amounts, testnet if available)
3. Debug errors using the auto-explain system
4. Experiment with parameters

### Go Deeper
1. Related topics are always suggested
2. Advanced topics unlock advanced strategies
3. Combine topics for complex workflows
4. Share what you learn with others

## Commands to Get More Info

```bash
# Learn about a specific topic
/omni-tool:ask buy-tokens

# See more advanced topics in a category
/omni-tool:topics governance --format=detailed

# Get the full teaching system
/omni-tool:topics --format=tree

# Set your learning preferences
/omni-tool:setup
```

## Next Steps

- Pick a learning path that matches your goals
- Ask about the first topic: `/omni-tool:ask [topic-name]`
- Set your personality mode for personalized teaching
- Join the community to share what you build!

Let's build amazing things on GalaChain! 🚀
