---
name: learning-galachain
description: Comprehensive learning system for GalaChain development with 41 topics and 254+ SDK methods
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

The GalaChain OmniTool includes **41 carefully organized teaching topics** covering:

- **Trading**: Buying, selling, swaps, graduations
- **Liquidity**: Adding positions, collecting fees, managing pools
- **Tokens**: Creating, analyzing, transferring, locking
- **Bridging**: Moving tokens to Ethereum, Solana
- **Streaming**: RTMP, recordings, simulcast
- **Social**: Chat, moderation, community management
- **Advanced**: NFTs, governance, monitoring
- **And more**: 254+ SDK methods fully documented

## The Teaching System

### How It Works

1. **Fetch Content** - Call `gala_launchpad_explain_sdk_usage` with a topic name
2. **Get Examples** - Receive TypeScript code examples for that topic
3. **Learn at Your Level** - Content adapted to your personality preference
4. **Execute Safely** - Use MCP tools to practice what you learned
5. **Build Confidence** - Move from concepts to real applications

### The 41 Topics

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

### 🏪 Path 1: Trading Essentials (3-4 hours)

Learn to buy, sell, and manage tokens on bonding curves and DEX.

1. **Token Basics** - `/galachain:ask token-metadata`
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

4. **Token Distribution** - `/galachain:ask token-holders`
   - Analyze who owns what
   - Whale identification
   - Distribution health

5. **Graduation** - `/galachain:ask token-graduation`
   - Move from bonding curve to DEX
   - Preparation steps
   - What happens after graduation

### 💰 Path 2: Liquidity Management (4-5 hours)

Become an LP (liquidity provider) and earn trading fees.

1. **Pool Discovery** - `/galachain:ask dex-pool-discovery`
   - Find pools by TVL, volume, fees
   - Filter and sort options
   - Risk assessment

2. **Adding Liquidity** - `/galachain:ask liquidity-add-by-price`
   - Concentrated liquidity strategy
   - Price range selection
   - Position initialization

3. **Fee Collection** - `/galachain:ask liquidity-fee-collection`
   - How fees accumulate
   - Collection process
   - Earning optimization

4. **Position Management** - `/galachain:ask liquidity-remove`
   - Closing positions
   - Withdrawal process
   - Partial vs complete exits

5. **Advanced Positioning** - `/galachain:ask liquidity-add-by-tick`
   - Tick-based fine-tuning
   - Advanced strategies
   - Risk management

### 🔄 Path 3: DEX Swapping (2-3 hours)

Trade tokens on the decentralized exchange.

1. **Token Discovery** - `/galachain:ask dex-token-discovery`
   - Find tradeable tokens
   - Check liquidity
   - Verify trading pairs

2. **Exact Input Swaps** - `/galachain:ask dex-swap-exact-input`
   - You know how much input
   - Output is calculated
   - Best for fixed budgets

3. **Exact Output Swaps** - `/galachain:ask dex-swap-exact-output`
   - You know how much output
   - Input is calculated
   - Best for fixed targets

4. **Understanding Slippage** - `/galachain:ask price-impact`
   - What is slippage?
   - Fee implications
   - Tolerance settings

### 🌉 Path 4: Bridging & Cross-Chain (3-4 hours)

Move tokens between GalaChain and other blockchains.

1. **Bridge Fees** - `/galachain:ask bridge-fees`
   - Cost estimation
   - Supported tokens
   - Fee factors

2. **To Ethereum** - `/galachain:ask bridge-to-ethereum`
   - Supported tokens (GALA, GWETH, GUSDC, GUSDT, GWTRX, GWBTC)
   - Bridge process
   - Time and confirmation

3. **From Ethereum** - `/galachain:ask bridge-from-ethereum`
   - Reverse process
   - Wallet setup
   - Verification steps

4. **To Solana** - `/galachain:ask bridge-to-solana`
   - Supported tokens (GALA, GSOL)
   - Different mechanics
   - Solana specifics

5. **From Solana** - `/galachain:ask bridge-from-solana`
   - Bringing back from SOL
   - Confirmation process
   - Troubleshooting

6. **Bridge Monitoring** - `/galachain:ask bridge-status`
   - Track pending bridging
   - Check confirmations
   - Resolve issues

### 📡 Path 5: Streaming & Community (4-5 hours)

Build a streaming community with chat and moderation.

1. **Start Streaming** - `/galachain:ask stream-start-stop`
   - RTMP setup
   - Stream keys
   - Start/stop operations

2. **Live Chat** - `/galachain:ask stream-chat`
   - REST API for history
   - WebSocket for real-time
   - Moderation basics

3. **Video Recording** - `/galachain:ask stream-recordings`
   - Automatic VOD capture
   - Download URLs
   - Deletion policies

4. **Multi-Platform** - `/galachain:ask simulcast-management`
   - Broadcast to YouTube, Twitch, Facebook
   - Simultaneous streaming
   - Failover handling

5. **Community Management** - `/galachain:ask chat-moderation`
   - Ban/unban users
   - Chat cleanup
   - User management

6. **Content Moderation** - `/galachain:ask content-moderation`
   - Flag inappropriate content
   - Automatic detection
   - Manual flagging

7. **Moderator Team** - `/galachain:ask moderator-management`
   - Invite moderators
   - Role assignment
   - Invite management

### 🎫 Path 6: Token Creation (3-4 hours)

Launch your own token with bonding curves.

1. **Create Token** - `/galachain:ask token-creation`
   - Token parameters
   - Bonding curve configuration
   - Initial setup

2. **Token Metadata** - `/galachain:ask token-metadata`
   - Set token details
   - Verification
   - Image/description

3. **Monitor Supply** - `/galachain:ask token-supply`
   - Check circulation
   - Track total supply
   - Holder analysis

4. **Price History** - `/galachain:ask token-price-history`
   - Historical data access
   - Charting data
   - Analytics

5. **Token Graduation** - `/galachain:ask token-graduation`
   - Transition to DEX
   - Liquidity requirements
   - Next steps after graduation

### ⚡ Path 7: Advanced Features (2-3 hours)

Expert-level capabilities for sophisticated applications.

1. **NFT Collections** - `/galachain:ask nft-collections`
   - Create collections
   - Mint NFTs
   - Manage inventory

2. **Wrapped Tokens** - `/galachain:ask wrapped-tokens`
   - Cross-channel wrapping
   - MUSIC ↔ GMUSIC example
   - Channel bridge operations

3. **API Management** - `/galachain:ask api-keys`
   - Create API credentials
   - Secure storage
   - Rotation policies

4. **Event Monitoring** - `/galachain:ask monitoring-events`
   - Real-time subscriptions
   - Event filtering
   - Event-driven architecture

5. **Governance** - `/galachain:ask overseer-system`
   - Platform-wide controls
   - Oversight functions
   - Admin operations

### 👑 Path 8: Mastery (8-10 hours)

Complete all 41 topics and build a sophisticated application.

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
1. /galachain:ask token-metadata
2. /galachain:ask buy-tokens
3. /galachain:ask sell-tokens
4. Start trading with confidence!
```

### "I want to be an LP and earn fees"
```
1. /galachain:ask dex-pool-discovery
2. /galachain:ask liquidity-add-by-price
3. /galachain:ask liquidity-fee-collection
4. /galachain:ask liquidity-remove
```

### "I want to create a token"
```
1. /galachain:ask token-creation
2. /galachain:ask token-metadata
3. /galachain:ask token-holders (to track distribution)
4. /galachain:ask token-graduation (next phase)
```

### "I want to stream with chat"
```
1. /galachain:ask stream-start-stop
2. /galachain:ask stream-chat
3. /galachain:ask chat-moderation
4. /galachain:ask stream-recordings
```

### "I want to bridge tokens to Ethereum"
```
1. /galachain:ask bridge-fees
2. /galachain:ask bridge-to-ethereum
3. /galachain:ask bridge-status
```

## How to Learn Effectively

### ✅ Do This

1. **Follow learning paths** - Concepts build on each other
2. **Ask one topic at a time** - Deep understanding beats breadth
3. **Practice what you learn** - Use MCP tools to execute operations
4. **Start small** - Small amounts before large positions
5. **Experiment** - Try different strategies and observe results
6. **Ask follow-up questions** - Each response suggests related topics
7. **Build projects** - Combine topics into complete applications

### ❌ Avoid This

1. **Jumping around randomly** - Learn dependencies first
2. **Large trades without practice** - Start small, scale up
3. **Ignoring error messages** - Errors teach you important lessons
4. **Skipping documentation** - The teaching system is your friend
5. **Trying advanced topics first** - Build foundations first
6. **Not verifying assumptions** - Always check before large operations

## The MCP Tool Equivalence

For every topic, we show you:

1. **SDK code** - TypeScript examples using the SDK
2. **MCP tool** - Equivalent command using the 247-tool MCP server

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
- `/galachain:topics` - Browse all 41 topics
- `/galachain:setup` - Configure your preferences

### Agent
- `galachain-builder` - Ask the agent for help building apps

### Teaching Content
- 41 comprehensive topics
- 254+ SDK methods documented
- Hundreds of code examples
- 247 MCP tools available

## Next Steps

1. **Pick a learning path** that matches your goals
2. **Ask the first topic**: `/galachain:ask [topic-name]`
3. **Explore related topics** as suggested
4. **Practice with MCP tools** to build confidence
5. **Build your first project** combining multiple concepts
6. **Master all 41 topics** and become a GalaChain expert

## Pro Tips

💡 **Mix learning and doing** - Read 5 minutes, practice 10 minutes
💡 **Use the agent** - Ask `galachain-builder` for guidance
💡 **Start with what interests you** - Motivation is fuel
💡 **Join the community** - Share what you build
💡 **Revisit basics** - Solid foundations enable advanced work
💡 **Automate with MCP** - Use MCP tools for repetitive tasks

---

**Ready to start?**

Pick your first topic and run:
```bash
/galachain:ask [your-chosen-topic]
```

Let's build the future of GalaChain together! 🚀
