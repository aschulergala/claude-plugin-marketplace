---
name: galachain:topics
description: List all 41 teaching topics organized by category
arguments:
  - name: category
    description: "Filter by category (trading, liquidity, tokens, bridge, streaming, advanced, or 'all')"
    required: false
  - name: format
    description: "Output format: list (default), detailed, or tree"
    required: false
---

# GalaChain Topics Command

Browse all 41 teaching topics organized by domain. Each topic includes:
- **Description** - What this feature does
- **Difficulty** - Beginner, intermediate, or advanced
- **Prerequisites** - Recommended topics to learn first
- **MCP Tools** - Number of available MCP tools for this topic

## Usage

```bash
# List all topics
/galachain:topics

# Filter by category
/galachain:topics trading
/galachain:topics liquidity
/galachain:topics bridge

# Different formats
/galachain:topics --format=detailed
/galachain:topics --format=tree
/galachain:topics trading --format=detailed
```

## All Topics by Category

### 🏪 Trading (8 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `buy-tokens` | Beginner | Purchase tokens on bonding curves | 3 |
| `sell-tokens` | Beginner | Sell tokens back to bonding curves | 3 |
| `token-graduation` | Intermediate | Transition tokens from bonding curve to DEX | 4 |
| `dex-swap-exact-input` | Beginner | Trade with fixed input amount | 3 |
| `dex-swap-exact-output` | Intermediate | Trade with fixed output amount | 3 |
| `price-impact` | Intermediate | Understanding slippage and fees | 2 |
| `token-holders` | Beginner | Analyze token distribution and holders | 2 |
| `token-metadata` | Beginner | Token details and verification | 2 |

### 💰 Liquidity & DEX (8 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `dex-pool-discovery` | Beginner | Find and filter liquidity pools by TVL/volume/fees | 4 |
| `liquidity-add-by-price` | Intermediate | Add concentrated LP positions by price range | 5 |
| `liquidity-add-by-tick` | Advanced | Advanced tick-based LP position management | 4 |
| `liquidity-remove` | Intermediate | Close positions and withdraw liquidity | 3 |
| `liquidity-fee-collection` | Intermediate | Collect earned trading fees from positions | 3 |
| `dex-leaderboard` | Beginner | Top traders and pools rankings | 2 |
| `dex-volume-summary` | Beginner | Trading volume analytics and metrics | 2 |
| `dex-token-discovery` | Beginner | Find tokens trading on DEX | 3 |

### 🎫 Token Management (7 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `token-creation` | Intermediate | Launch new tokens with bonding curves | 4 |
| `token-supply` | Beginner | Check total supply and circulation | 2 |
| `token-price-history` | Beginner | Historical price data and analysis | 3 |
| `token-transfers` | Beginner | Send tokens to addresses | 2 |
| `token-locks` | Intermediate | Lock tokens for vesting or escrow | 4 |
| `token-unlocks` | Intermediate | Release locked tokens | 3 |
| `wrapped-tokens` | Advanced | Cross-channel token wrapping (MUSIC ↔ GMUSIC) | 4 |

### 🌉 Bridging (6 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `bridge-to-ethereum` | Intermediate | Move tokens to Ethereum | 4 |
| `bridge-from-ethereum` | Intermediate | Import tokens from Ethereum | 4 |
| `bridge-to-solana` | Intermediate | Move tokens to Solana | 4 |
| `bridge-from-solana` | Intermediate | Import tokens from Solana | 4 |
| `bridge-fees` | Beginner | Estimate bridge costs | 2 |
| `bridge-status` | Intermediate | Track bridge transaction status | 3 |

### 📡 Streaming & Social (8 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `stream-start-stop` | Beginner | Manage RTMP streaming (start/stop) | 4 |
| `stream-key-management` | Beginner | Reset and manage stream keys | 2 |
| `stream-recordings` | Beginner | Record and manage video-on-demand (VODs) | 5 |
| `simulcast-management` | Intermediate | Broadcast to multiple platforms simultaneously | 5 |
| `stream-chat` | Beginner | Real-time chat integration (REST + WebSocket) | 6 |
| `chat-moderation` | Intermediate | Ban/unban users and manage chat | 4 |
| `content-moderation` | Intermediate | Flag inappropriate content | 3 |
| `moderator-management` | Intermediate | Invite and manage moderators | 5 |

### ⚡ Advanced Features (4 topics)

| Topic | Difficulty | Description | MCP Tools |
|-------|-----------|-------------|-----------|
| `nft-collections` | Advanced | Manage NFT collections and minting | 6 |
| `overseer-system` | Advanced | Platform-wide governance and oversight | 3 |
| `api-keys` | Beginner | Manage API credentials | 3 |
| `monitoring-events` | Advanced | Real-time event subscriptions and monitoring | 8 |

## Learning Paths

### Path 1: Token Trading Essentials (3-4 hours)
1. Start: `token-metadata` - Understand what tokens are
2. Learn: `buy-tokens` - How to purchase
3. Learn: `sell-tokens` - How to exit
4. Learn: `token-holders` - Analyze distribution
5. Advanced: `token-graduation` - Move to DEX

### Path 2: Liquidity Management (4-5 hours)
1. Start: `dex-pool-discovery` - Find pools
2. Learn: `liquidity-add-by-price` - Add LP positions
3. Learn: `liquidity-fee-collection` - Collect earnings
4. Learn: `liquidity-remove` - Close positions
5. Advanced: `liquidity-add-by-tick` - Advanced strategies

### Path 3: DEX Swapping (2-3 hours)
1. Start: `dex-token-discovery` - Find tokens
2. Learn: `dex-swap-exact-input` - Fixed input swaps
3. Learn: `dex-swap-exact-output` - Fixed output swaps
4. Advanced: `price-impact` - Slippage and fees

### Path 4: Cross-Chain Bridging (3-4 hours)
1. Start: `bridge-fees` - Understand costs
2. Learn: `bridge-to-ethereum` - Move to ETH
3. Learn: `bridge-from-ethereum` - Bring back
4. Advanced: `bridge-to-solana` - SOL chain
5. Expert: `wrapped-tokens` - Internal wrapping

### Path 5: Live Streaming & Community (4-5 hours)
1. Start: `stream-start-stop` - Begin streaming
2. Learn: `stream-chat` - Add live chat
3. Learn: `stream-recordings` - Record VODs
4. Learn: `chat-moderation` - Manage community
5. Advanced: `simulcast-management` - Multi-platform
6. Expert: `moderator-management` - Team building

### Path 6: Platform Master (8-10 hours)
Complete all paths 1-5, then:
1. `token-creation` - Create your own token
2. `nft-collections` - Add NFT support
3. `overseer-system` - Governance
4. `monitoring-events` - Real-time analytics
5. `api-keys` - Secure integrations

## Quick Reference by Use Case

**"I want to trade tokens"**
→ `buy-tokens` → `sell-tokens` → `dex-swap-exact-input` → `price-impact`

**"I want to provide liquidity"**
→ `dex-pool-discovery` → `liquidity-add-by-price` → `liquidity-fee-collection`

**"I want to bridge tokens"**
→ `bridge-fees` → `bridge-to-ethereum` → `bridge-status`

**"I want to launch a token"**
→ `token-creation` → `token-metadata` → `token-graduation` → `dex-swap-exact-input`

**"I want to stream live"**
→ `stream-start-stop` → `stream-chat` → `simulcast-management` → `stream-recordings`

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
4. Use `/galachain:ask [topic]` to learn

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
/galachain:ask buy-tokens

# See more advanced topics in a category
/galachain:topics advanced --format=detailed

# Get the full teaching system
/galachain:topics --format=tree

# Set your learning preferences
/galachain:setup
```

## Next Steps

- Pick a learning path that matches your goals
- Ask about the first topic: `/galachain:ask [topic-name]`
- Set your personality mode for personalized teaching
- Join the community to share what you build!

Let's build amazing things on GalaChain! 🚀
