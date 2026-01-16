---
name: galachain:ask
description: Ask about any GalaChain topic - accepts natural language questions or topic names
arguments:
  - name: query
    description: "Your question or topic name (e.g., 'how do I buy tokens?' or 'buy-tokens')"
    required: true
  - name: examples
    description: "Show code examples? (yes/no, default: yes)"
    required: false
  - name: personality
    description: "Personality mode override: tutor, expert, pragmatist, socratic (default: from settings)"
    required: false
---

# GalaChain Ask Command

Ask any question about GalaChain development. The system automatically maps your question to the 41 built-in teaching topics and provides comprehensive answers.

## Usage Examples

```bash
# Natural language question
/galachain:ask how do I buy tokens?
/galachain:ask what's the difference between swaps and graduations?
/galachain:ask I need to create a token and enable trading

# Direct topic name (faster)
/galachain:ask buy-tokens
/galachain:ask dex-pool-discovery
/galachain:ask bridge-to-ethereum

# With options
/galachain:ask token-creation --examples=no
/galachain:ask stream-start-stop --personality=expert
```

## Supported Topics

The system recognizes all 41 teaching topics:

### Trading (8)
buy-tokens, sell-tokens, token-graduation, dex-swap-exact-input, dex-swap-exact-output, price-impact, token-holders, token-metadata

### Liquidity (8)
dex-pool-discovery, liquidity-add-by-price, liquidity-add-by-tick, liquidity-remove, liquidity-fee-collection, dex-leaderboard, dex-volume-summary, dex-token-discovery

### Tokens (7)
token-creation, token-supply, token-price-history, token-transfers, token-locks, token-unlocks, wrapped-tokens

### Bridging (6)
bridge-to-ethereum, bridge-from-ethereum, bridge-to-solana, bridge-from-solana, bridge-fees, bridge-status

### Streaming (8)
stream-start-stop, stream-key-management, stream-recordings, simulcast-management, stream-chat, chat-moderation, content-moderation, moderator-management

### Advanced (4)
nft-collections, overseer-system, api-keys, monitoring-events

## How It Works

1. **Parse your input** - Understand if you asked a question or stated a topic
2. **Match to topics** - Use fuzzy matching for natural language, exact for topic names
3. **Fetch teaching content** - Call `gala_launchpad_explain_sdk_usage` to get comprehensive content
4. **Personalize response** - Adapt explanation style based on your personality preference
5. **Offer next steps** - Suggest related topics or MCP tool execution

## Response Format

Each response includes:

- **Concept explanation** - What this feature does and why it matters
- **When to use** - Real-world scenarios and use cases
- **Code example** - Working TypeScript example with your SDK
- **MCP Tool equivalent** - How to use the 247-tool MCP server
- **Key parameters** - Important options and what they do
- **Common pitfalls** - Things people get wrong
- **Related topics** - Suggested follow-up learning
- **Ready to execute?** - Offer to run the operation for you

## Fuzzy Matching

The command uses smart fuzzy matching for natural language questions:

```
Question: "How do I create a new token?"
→ Matches: token-creation

Question: "I want to bridge to Ethereum"
→ Matches: bridge-to-ethereum

Question: "What's the difference between buy and sell?"
→ Suggests: buy-tokens, sell-tokens (both relevant)

Question: "Tell me about fees on swaps"
→ Matches: price-impact (which covers fees)
```

## Personality Modes

Override the default personality for this response:

```bash
# Expert mode - fast and direct
/galachain:ask dex-pool-discovery --personality=expert

# Socratic mode - learn through questions
/galachain:ask token-creation --personality=socratic

# Tutor mode - patient and thorough
/galachain:ask bridge-to-ethereum --personality=tutor

# Pragmatist mode - balanced approach
/galachain:ask liquidity-add-by-price --personality=pragmatist
```

## Integration with Agent

When you're using the `galachain-builder` agent, this command runs automatically under the hood. You can:

- Ask the agent directly: "How do I add liquidity?"
- Agent calls `/galachain:ask` internally
- Get comprehensive teaching response
- Continue the conversation naturally

## Integration with Skill

The `learning-galachain` skill uses this command to teach you:

- Structured learning paths with prerequisites
- Progressive difficulty (basic → advanced)
- Hands-on practice with examples
- Self-paced learning modules

## Pro Tips

- **Learn progressively** - Start with basic topics, build up complexity
- **Practice what you learn** - Use MCP tools to execute operations
- **Ask follow-ups** - Each response has suggested related topics
- **Change personality mid-session** - Different modes for different moods
- **Mix and match** - Combine topics to understand complete workflows

## Examples

### Example 1: Basic Token Purchase
```bash
$ /galachain:ask how do I buy tokens?

→ Fetches: buy-tokens topic
→ Explains: Bonding curve token purchases
→ Shows: Code example with SDK
→ Offers: Execute a purchase for you
```

### Example 2: Complex Liquidity Strategy
```bash
$ /galachain:ask liquidity-add-by-price --personality=expert

→ Fetches: liquidity-add-by-price topic
→ Fast-paced: Assumes DEX knowledge
→ Shows: Advanced parameters and optimization
→ Offers: Set up position now
```

### Example 3: Bridging to Ethereum
```bash
$ /galachain:ask I want to move GALA to Ethereum

→ Fuzzy matches: bridge-to-ethereum
→ Explains: What bridging is and why
→ Shows: Code for Ethereum bridge
→ Lists: Fees, supported tokens, requirements
→ Offers: Execute bridge transaction
```

## Next Steps

- Try `/galachain:topics` to browse all 41 topics
- Run `/galachain:setup` to configure your preferences
- Ask the agent directly: "Help me build a trading bot"
- Explore complete workflows with the skill: `learning-galachain`

Let's keep learning! 🚀
