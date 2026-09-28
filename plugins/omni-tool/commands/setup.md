---
name: omni-tool:setup
description: Interactive setup wizard for configuring the GalaChain OmniTool plugin
arguments: []
---

# GalaChain Setup Command

Interactive wizard to configure the GalaChain OmniTool plugin for your workflow.

## Usage

```bash
# Run the interactive setup
/omni-tool:setup

# Or configure specific setting directly
/omni-tool:setup --personality=expert
/omni-tool:setup --environment=stage
/omni-tool:setup --wallet-mode=full-access
```

## Configuration Options

### 1. Agent Personality (Default: tutor)

How Claude teaches and interacts with you:

**🎓 Tutor Mode**
- Patient and thorough
- Explains everything in detail
- Includes best practices
- Suggests related topics
- Best for: Beginners and learning

**⚡ Expert Mode**
- Fast and direct
- Assumes DeFi knowledge
- Focuses on optimization
- Advanced patterns
- Best for: Experienced developers

**⚙️ Pragmatist Mode**
- Balanced approach
- Explains key concepts
- Shows working code immediately
- Practical examples
- Best for: Getting things done

**❓ Socratic Mode**
- Asks questions first
- Guides discovery
- Builds understanding gradually
- Encourages experimentation
- Best for: Deep learning

### 2. Wallet Configuration (Default: read-only)

**Read-Only Mode**
- Browse tokens, pools, prices
- Query balances and holdings
- No wallet required
- No transactions possible
- Best for: Testing and learning

**Full-Access Mode**
- Execute trades and transfers
- Create and manage tokens
- Add liquidity positions
- Bridge tokens
- Requires: `PRIVATE_KEY` environment variable

### 3. Environment (Default: stage)

The MCP server supports exactly two environments — anything else fails to start.

**Stage** (default — recommended for testing)
- GalaChain's test network
- Same API contracts as production
- Safe to try things: browse, trade, create tokens
- Perfect for learning and testing workflows

**Prod**
- Real GalaChain network
- Real tokens and transactions
- Real money (⚠️ careful!)

### 4. Learning Preferences

**Show Advanced Topics**
- Include advanced complexity options
- Show optimization techniques
- Suggest expert patterns
- Default: true

**Include Best Practices**
- Security recommendations
- Error handling patterns
- Performance tips
- Default: true

**Include Error Handling**
- Common mistakes explained
- How to debug errors
- Recovery strategies
- Default: true

**Code Style**
- TypeScript (default)
- JavaScript alternatives
- Pseudocode option
- Default: TypeScript

### 5. Auto Features

**Auto-Explain Errors**
- When MCP tools fail, automatically provide guidance
- Fetches relevant teaching content
- Shows common fixes
- Default: true

**Auto-Suggest Examples**
- Automatically provide code examples
- Multiple approaches shown
- Relevant patterns highlighted
- Default: true

## Step 0: Verify MCP Connection

Before configuring preferences, verify the MCP server is reachable:

1. Attempt `gala_launchpad_explain_sdk_usage` with topic `installation`
2. **Success** → "✅ MCP server connected (310 tools available)" — proceed to Step 1
3. **Failure** (unknown tool / not found) → Show installation instructions and STOP:

> ❌ **MCP server not found.**
>
> The GalaChain MCP server needs to be added to your Claude Code config before setup can complete.
>
> Add to `~/.claude.json`:
> ```json
> {
>   "mcpServers": {
>     "gala-launchpad": {
>       "command": "npx",
>       "args": ["-y", "@gala-chain/launchpad-mcp-server@beta"],
>       "env": { "ENVIRONMENT": "stage" }
>     }
>   }
> }
> ```
> `ENVIRONMENT` accepts only `"stage"` (test network) or `"prod"` (real GalaChain). After restarting Claude Code, run `/omni-tool:setup` again.

## Interactive Setup Flow

```
Welcome to GalaChain OmniTool! 👋

Let's configure your experience.

1. Agent Personality
   Select your preferred teaching style:
   → Tutor (patient, thorough)
   → Expert (fast, direct)
   → Pragmatist (balanced)
   → Socratic (questions first)
   [Current: tutor]

2. Wallet Configuration
   How do you want to interact with GalaChain?
   → Read-Only (browse, query only)
   → Full-Access (requires PRIVATE_KEY env var)
   [Current: read-only]

3. Environment
   Which network should we connect to?
   → Stage (test network, safe to try things)
   → Prod (real GalaChain network)
   [Current: stage]

4. Learning Preferences
   How should Claude teach you?
   ☑ Show advanced topics
   ☑ Include best practices
   ☑ Include error handling
   [Code style: TypeScript]

5. Auto Features
   ☑ Auto-explain errors from MCP tools
   ☑ Auto-suggest code examples

✅ MCP server config written to ~/.claude.json
✅ Plugin preferences saved to .claude/galachain-omnitool.local.md
⚠️  Restart Claude Code to activate the MCP server
```

## Writing the MCP Server Config

After collecting preferences, **automatically write the MCP server config** to `~/.claude.json`:

1. Read the file if it exists (to preserve other MCP server entries)
2. Merge or add the `gala-launchpad` entry with the chosen environment
3. Write the file back

The `ENVIRONMENT` value maps directly to the chosen environment (only these two are valid; anything else fails to start):
- `stage` → `"ENVIRONMENT": "stage"`
- `prod` → `"ENVIRONMENT": "prod"`

Example result for stage:
```json
{
  "mcpServers": {
    "gala-launchpad": {
      "command": "npx",
      "args": ["-y", "@gala-chain/launchpad-mcp-server@beta"],
      "env": { "ENVIRONMENT": "stage" }
    }
  }
}
```

After writing, remind the user to **restart Claude Code** for the MCP server to activate.

## Generated Plugin Preferences File

The setup also creates `.claude/galachain-omnitool.local.md`:

```yaml
---
# GalaChain OmniTool Configuration

# Agent personality: tutor, expert, pragmatist, socratic
agent_personality: tutor

# Wallet configuration: read-only or full-access
wallet_mode: read-only
# private_key: ${PRIVATE_KEY}

# Environment: stage or prod (only these two are valid)
environment: stage

# Learning preferences
show_advanced_topics: true
include_best_practices: true
include_error_handling: true
code_style: typescript

# Auto features
auto_explain_errors: true
auto_suggest_examples: true
---

# Your custom notes...
```

## Environment Variables

### Full-Access Mode (stage or prod)
```bash
# Required for full-access mode (omit for read-only)
export PRIVATE_KEY=your_private_key_hex

# Optional: override environment (only "stage" or "prod" are valid)
export ENVIRONMENT=stage

# Optional: Solana bridge operations, custom RPC endpoints, streaming config
export SOLANA_PRIVATE_KEY=your_solana_key
export ETHEREUM_RPC_URL=https://your-rpc-endpoint
export SOLANA_RPC_URL=https://your-solana-rpc-endpoint
```

There is no local/development mode — the MCP server always talks to stage or prod.

## Configuration Examples

### Beginner Learning Setup
```bash
/omni-tool:setup
# Select: Tutor, Read-Only, Stage
# Enable all learning options
```

→ Result: Patient teaching with examples, no risk of transactions, safe test network

### Full Testing Setup
```bash
/omni-tool:setup
# Select: Pragmatist, Full-Access, Stage
# Enable all learning options
```

→ Result: Real trades, token creation, and liquidity ops against GalaChain's stage network — nothing here touches real funds

### Experienced Trader Setup
```bash
/omni-tool:setup
# Select: Expert, Full-Access, Prod
# Disable redundant explanations
```

→ Result: Fast guidance, execute real trades immediately (⚠️ real money)

## After Setup

> ⚠️ **Restart Claude Code** after setup to activate the MCP server. The 310 tools won't be available until you restart.

Once configured, you can:

1. **Ask questions naturally**
   - "How do I buy tokens?"
   - Agent responds in your chosen personality style

2. **Use commands with confidence**
   - `/omni-tool:ask buy-tokens`
   - `/omni-tool:topics`
   - Explanations match your preferences

3. **Execute operations**
   - Agent offers to run MCP tools
   - Follows your wallet mode
   - Uses configured environment

4. **Get personalized help**
   - Errors explained with your code style
   - Advanced topics if enabled
   - Best practices included if selected

## Changing Configuration Later

You can:

1. **Re-run setup**
   ```bash
   /omni-tool:setup
   ```

2. **Edit directly**
   - Edit `.claude/galachain-omnitool.local.md`
   - Changes take effect immediately

3. **Override temporarily**
   - `/omni-tool:ask topic --personality=expert`
   - Overrides setting for that query only

## Quick Configuration Presets

### 🎓 Learning Mode
```
Personality: Tutor
Wallet: Read-Only
Environment: Stage
Learning: All enabled
Auto: All enabled
```
Perfect for beginners — no risk of a real transaction.

### 🧪 Full Testing Mode
```
Personality: Pragmatist
Wallet: Full-Access
Environment: Stage
Learning: All enabled
Auto: All enabled
```
Real trades, token creation, liquidity ops — all against GalaChain's stage network, nothing here touches real funds. This is the recommended way to fully exercise the plugin.

### ⚡ Trader Mode
```
Personality: Expert
Wallet: Full-Access
Environment: Prod
Learning: Minimal
Auto: Error explanations only
```
Fast and direct for experienced traders (⚠️ real money).

## Troubleshooting Setup

### "I can't find the configuration file"
- Setup creates `.claude/galachain-omnitool.local.md`
- Check if `.claude/` directory exists in your project
- Run setup again to recreate

### "Private key isn't being recognized"
- Check the `PRIVATE_KEY` environment variable (not `GALACHAIN_PRIVATE_KEY`)
- Verify it's a valid hex string (0x... or just hex)
- Make sure it's set before running operations

### "I want to reset everything"
- Delete `.claude/galachain-omnitool.local.md`
- Run `/omni-tool:setup` again
- All defaults will be reapplied

### "MCP tools aren't available after setup"
- You need to **restart Claude Code** after setup writes the config
- Verify `~/.claude.json` contains the `gala-launchpad` entry
- Re-run `/omni-tool:setup` to rewrite the config if needed

### "Stage seems broken"
- Stage may occasionally be under maintenance
- Check `/omni-tool:topics` to verify MCP connection
- Try switching to `prod` with `/omni-tool:setup` if blocked

## Next Steps

1. **Run setup**: `/omni-tool:setup`
2. **Choose your personality**: Pick what feels right
3. **Try a question**: `/omni-tool:ask token-creation`
4. **Browse topics**: `/omni-tool:topics`
5. **Build something**: Ask the agent to help you create your first token or trade!

Welcome to GalaChain development! 🚀
