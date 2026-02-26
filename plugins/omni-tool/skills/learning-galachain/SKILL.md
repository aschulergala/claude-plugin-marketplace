---
name: learning-galachain
description: Comprehensive learning system for GalaChain development with 59 topics and 307 SDK methods
triggers:
  - "How do I learn GalaChain?"
  - "Teach me about GalaChain"
  - "What can I build with GalaChain?"
  - "How does this teaching system work?"
  - "I want to learn GalaChain from scratch"
  - "Show me the learning roadmap"
  - "What are all the things I can do?"
---

# Learning GalaChain: Comprehensive Developer Guide

Welcome! This skill teaches you everything about GalaChain development using our built-in teaching system.

## What You'll Learn

The GalaChain OmniTool includes **59 carefully organized teaching topics** covering:

- **Trading**: Buying, selling, graduation, analytics, error handling
- **Pools & Info**: Pool discovery, token details, price history, distribution
- **Balances**: Balance queries, profiles, account management
- **Token Operations**: Creating, status, transfers, locks
- **DEX**: Swaps, token discovery, pool analysis, liquidity positions
- **DEX Analytics**: Seasons, leaderboards, volume summaries
- **Bridging**: Cross-chain operations, token wrapping
- **Streaming & Chat**: RTMP, recordings, simulcast, real-time chat
- **Community**: Bans, content flags, reactions, moderators, token bans, AI moderation
- **Governance**: Overseers, API keys, event subscriptions, restricted names, WebSocket admin
- **Wallet & Auth**: Multi-wallet, JWT sessions
- **Utilities**: Installation, helpers, system utils, MCP mapping, platform stats, OEmbed
- **Streaming & Chat**: RTMP, recordings, simulcast, real-time chat, unified messages
- **Pools & Token Info**: Pool discovery, token details, price history, distribution, holders
- **DEX Analytics**: Seasons, leaderboards, volume summaries, weekly challenges
- **And more**: 307 SDK methods fully documented

## The Teaching System

### How It Works

1. **Fetch Content** - Call `gala_launchpad_explain_sdk_usage` with a topic name
2. **Get Examples** - Receive TypeScript code examples for that topic
3. **Learn at Your Level** - Content adapted to your personality preference
4. **Execute Safely** - Use MCP tools to practice what you learned
5. **Build Confidence** - Move from concepts to real applications

### The 59 Topics

All topics are accessible via `/galachain:ask [topic]`:

**See topics list**: `/galachain:topics`

Each topic includes:
- Concept explanation
- Step-by-step guide
- Code examples
- MCP tool equivalents
- Common mistakes to avoid
- Related topics for deeper learning

## Learning Paths

### 🏪 Path 1: Trading Essentials

Learn to buy, sell, and manage tokens on bonding curves and DEX.

1. **Token Basics** - `/galachain:ask token-details`
   - What tokens are
   - How to verify them
   - Metadata importance

2. **Buying Tokens** - `/galachain:ask buy-tokens`
   - Bonding curve mechanics
   - Purchase process
   - Price calculation

3. **Selling Tokens** - `/galachain:ask sell-tokens`
   - Exit strategies
   - Fee implications
   - Timing considerations

4. **Trading Analytics** - `/galachain:ask trading-analytics`
   - Analyze trade history
   - Metrics and trends
   - Performance tracking

5. **Graduation** - `/galachain:ask pool-graduation`
   - Move from bonding curve to DEX
   - Preparation steps
   - What happens after graduation

### 💰 Path 2: Liquidity Management

Become an LP (liquidity provider) and earn trading fees.

1. **DEX Pool Discovery** - `/galachain:ask fetch-dex-pools`
   - Find DEX pools
   - Filter and sort options
   - Risk assessment

2. **LP Positions** - `/galachain:ask liquidity-positions`
   - Concentrated liquidity strategy
   - Position management
   - Adding and removing liquidity

3. **Advanced Analysis** - `/galachain:ask advanced-dex-analysis`
   - Composite pool data
   - Deep analytics
   - Strategy optimization

4. **Seasonal Analytics** - `/galachain:ask fetch-all-dex-seasons`
   - DEX season data
   - Leaderboard tracking
   - Volume trends

### 🔄 Path 3: DEX Swapping

Trade tokens on the decentralized exchange.

1. **Token Discovery** - `/galachain:ask dex-token-discovery`
   - Find tradeable tokens
   - Check liquidity
   - Verify trading pairs

2. **DEX Trading** - `/galachain:ask dex-trading`
   - Execute swaps (exact input and output)
   - Get swap quotes
   - Manage slippage

3. **Price Routing** - `/galachain:ask spot-prices-smart-routing`
   - Spot prices
   - Smart routing
   - Optimal execution

### 🌉 Path 4: Bridging & Cross-Chain

Move tokens between GalaChain and other blockchains.

1. **Bridge Operations** - `/galachain:ask bridge-operations`
   - Bridge to Ethereum and Solana
   - Estimate fees
   - Track bridge status
   - Supported tokens and networks

2. **Token Wrapping** - `/galachain:ask wrap-unwrap-operations`
   - Cross-channel wrapping
   - Wrap/unwrap fees
   - Wrappable token discovery

### 📡 Path 5: Streaming & Community

Build a streaming community with chat and moderation.

1. **Start Streaming** - `/galachain:ask streaming`
   - RTMP setup and stream keys
   - Start/stop operations
   - Recordings and VODs
   - Simulcast to multiple platforms

2. **Live Chat** - `/galachain:ask stream-chat`
   - REST API for history
   - WebSocket for real-time
   - Chat status and engagement

3. **Ban Management** - `/galachain:ask ban-management`
   - Ban/unban users
   - List and check bans
   - Active user tracking

4. **Content Moderation** - `/galachain:ask content-flag-management`
   - Flag inappropriate content
   - Review and action flags
   - Global flag management

5. **Moderator Team** - `/galachain:ask moderator-invites`
   - Invite moderators
   - Role assignment
   - Invite management

### 🎫 Path 6: Token Creation

Launch your own token with bonding curves.

1. **Create Token** - `/galachain:ask token-creation`
   - Token parameters
   - Bonding curve configuration
   - Initial setup

2. **Token Status** - `/galachain:ask token-status`
   - Check graduation status
   - Monitor supply
   - Track events

3. **Token Distribution** - `/galachain:ask token-distribution`
   - Analyze who owns what
   - Holder context
   - Distribution health

4. **Price History** - `/galachain:ask price-history`
   - Historical data access
   - Charting data
   - Analytics

5. **Token Graduation** - `/galachain:ask pool-graduation`
   - Transition to DEX
   - Graduation detection
   - Next steps after graduation

### ⚡ Path 7: Advanced Features

Expert-level capabilities for sophisticated applications.

1. **NFT Collections** - `/galachain:ask nft-collection-management`
   - Create collections
   - Mint NFTs
   - Manage inventory

2. **Token Wrapping** - `/galachain:ask wrap-unwrap-operations`
   - Cross-channel wrapping
   - Fee estimation
   - Wrappable token discovery

3. **API Management** - `/galachain:ask api-key-management`
   - Create API credentials
   - Secure storage
   - Rotation policies

4. **Event Monitoring** - `/galachain:ask event-subscriptions`
   - Real-time subscriptions
   - Event filtering
   - Event-driven architecture

5. **Governance** - `/galachain:ask overseer-invites`
   - Platform-wide controls
   - Oversight functions
   - Admin operations

### 👑 Path 8: Mastery

Complete all 59 topics and build a sophisticated application.

Recommended order:
1. Complete Path 1: Trading Essentials
2. Complete Path 2: Liquidity Management
3. Complete Path 3: DEX Swapping
4. Complete Path 4: Bridging
5. Complete Path 5: Streaming
6. Complete Path 6: Token Creation
7. Complete Path 7: Advanced Features
8. **Build your project** combining multiple paths

## Quick Reference: Common Scenarios

### "I want to trade"
```
1. /galachain:ask token-details
2. /galachain:ask buy-tokens
3. /galachain:ask sell-tokens
4. Start trading with confidence!
```

### "I want to be an LP and earn fees"
```
1. /galachain:ask fetch-dex-pools
2. /galachain:ask liquidity-positions
3. /galachain:ask advanced-dex-analysis
```

### "I want to create a token"
```
1. /galachain:ask token-creation
2. /galachain:ask token-details
3. /galachain:ask token-distribution (to track distribution)
4. /galachain:ask pool-graduation (next phase)
```

### "I want to stream with chat"
```
1. /galachain:ask streaming
2. /galachain:ask stream-chat
3. /galachain:ask ban-management
4. /galachain:ask moderator-invites
```

### "I want to bridge tokens to Ethereum"
```
1. /galachain:ask bridge-operations
2. /galachain:ask wrap-unwrap-operations
```

## How to Learn Effectively

### Do This

1. **Follow learning paths** - Concepts build on each other
2. **Ask one topic at a time** - Deep understanding beats breadth
3. **Practice what you learn** - Use MCP tools to execute operations
4. **Start small** - Small amounts before large positions
5. **Experiment** - Try different strategies and observe results
6. **Ask follow-up questions** - Each response suggests related topics
7. **Build projects** - Combine topics into complete applications

### Avoid This

1. **Jumping around randomly** - Learn dependencies first
2. **Large trades without practice** - Start small, scale up
3. **Ignoring error messages** - Errors teach you important lessons
4. **Skipping documentation** - The teaching system is your friend
5. **Trying advanced topics first** - Build foundations first
6. **Not verifying assumptions** - Always check before large operations

## The MCP Tool Equivalence

For every topic, we show you:

1. **SDK code** - TypeScript examples using the SDK
2. **MCP tool** - Equivalent command using the 307-tool MCP server

Example for "buy-tokens":
```typescript
// SDK approach
const result = await sdk.buyTokens({
  tokenName: 'anime',
  amount: '100',
  type: 'native'
});

// MCP tool equivalent
gala_launchpad_buy_tokens tokenName=anime amount=100 type=native
```

This dual approach helps you understand:
- SDK is for building applications
- MCP tools are for one-off operations or Claude interactions
- They're equivalent - choose based on your use case

## Configuration for Your Learning

Customize the learning system:

```bash
# Set your personality preference
/galachain:setup --personality=tutor

# Or run full setup wizard
/galachain:setup
```

Options:
- **Tutor**: Patient, thorough, best for beginners
- **Expert**: Fast, direct, best for experienced traders
- **Pragmatist**: Balanced, practical approach
- **Socratic**: Questions first, discovery-focused

## Resources Available

### Commands
- `/galachain:ask [topic]` - Learn about any topic
- `/galachain:topics` - Browse all 59 topics
- `/galachain:setup` - Configure your preferences

### Agent
- `galachain-builder` - Ask the agent for help building apps

### Teaching Content
- 59 comprehensive topics
- 307 SDK methods documented
- Hundreds of code examples
- 307 MCP tools available

## Next Steps

1. **Pick a learning path** that matches your goals
2. **Ask the first topic**: `/galachain:ask [topic-name]`
3. **Explore related topics** as suggested
4. **Practice with MCP tools** to build confidence
5. **Build your first project** combining multiple concepts
6. **Master all 59 topics** and become a GalaChain expert

## Pro Tips

- **Mix learning and doing** - Read 5 minutes, practice 10 minutes
- **Use the agent** - Ask `galachain-builder` for guidance
- **Start with what interests you** - Motivation is fuel
- **Join the community** - Share what you build
- **Revisit basics** - Solid foundations enable advanced work
- **Automate with MCP** - Use MCP tools for repetitive tasks

---

**Ready to start?**

Pick your first topic and run:
```bash
/galachain:ask [your-chosen-topic]
```

Let's build the future of GalaChain together! 🚀
