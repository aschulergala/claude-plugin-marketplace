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
/omni-tool:setup --environment=staging
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
- Requires: `GALACHAIN_PRIVATE_KEY` environment variable

### 3. Environment (Default: production)

**Production**
- Real GalaChain network
- Real tokens and transactions
- Real money (⚠️ careful!)
- Most features available

**QA1**
- QA environment for pre-release testing
- Mirrors production contracts
- Safe for integration testing
- Use when testing against latest builds

**Staging**
- Test network with unlimited fake tokens
- Practice trading safely
- Same API contracts as production
- Perfect for testing workflows

**Development**
- Local backend at localhost:4000
- Requires backend service running
- For SDK and MCP server development

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
>       "args": ["-y", "@gala-chain/launchpad-mcp-server"],
>       "env": { "ENVIRONMENT": "production" }
>     }
>   }
> }
> ```
> After restarting Claude Code, run `/omni-tool:setup` again.

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
   → Production (real GalaChain network)
   → QA1 (pre-release QA environment)
   → Staging (test network, unlimited fake tokens)
   → Development (localhost:4000)
   [Current: production]

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

The `ENVIRONMENT` value maps directly to the chosen environment:
- `production` → `"ENVIRONMENT": "production"`
- `qa1` → `"ENVIRONMENT": "qa1"`
- `staging` → `"ENVIRONMENT": "staging"`
- `development` → `"ENVIRONMENT": "development"`

Example result for qa1:
```json
{
  "mcpServers": {
    "gala-launchpad": {
      "command": "npx",
      "args": ["-y", "@gala-chain/launchpad-mcp-server"],
      "env": { "ENVIRONMENT": "qa1" }
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
# private_key: ${GALACHAIN_PRIVATE_KEY}

# Environment: production, qa1, staging, development
environment: production

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

### Production/Staging Access
```bash
# Required for full-access mode
export GALACHAIN_PRIVATE_KEY=your_private_key_hex

# Optional: override environment
export GALACHAIN_ENVIRONMENT=staging
```

### Development (localhost)
```bash
# Backend service must be running
export LAUNCHPAD_API_URL=http://localhost:4000

# Optional wallet for testing
export GALACHAIN_PRIVATE_KEY=your_test_key
```

## Configuration Examples

### Beginner Learning Setup
```bash
/omni-tool:setup
# Select: Tutor, Read-Only, Production
# Enable all learning options
```

→ Result: Patient teaching with examples, no risk of transactions

### Experienced Trader Setup
```bash
/omni-tool:setup
# Select: Expert, Full-Access, Production
# Disable redundant explanations
```

→ Result: Fast guidance, execute trades immediately

### QA1 Integration Testing Setup
```bash
/omni-tool:setup
# Select: Expert, Full-Access, QA1
# Show advanced topics and error handling
```

→ Result: Full access against QA1 pre-release environment for integration testing

### Safe Testing Setup
```bash
/omni-tool:setup
# Select: Pragmatist, Full-Access, Staging
# Enable all learning options
```

→ Result: Practical examples with unlimited fake tokens for testing

### Developer Setup
```bash
/omni-tool:setup
# Select: Expert, Full-Access, Development
# Show advanced topics and error handling
```

→ Result: Direct API interaction with localhost backend

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
Environment: Production
Learning: All enabled
Auto: All enabled
```
Perfect for beginners.

### ⚡ Trader Mode
```
Personality: Expert
Wallet: Full-Access
Environment: Production
Learning: Minimal
Auto: Error explanations only
```
Fast and direct for experienced traders.

### 🔬 QA Mode
```
Personality: Expert
Wallet: Full-Access
Environment: QA1
Learning: Advanced only
Auto: Errors and examples
```
Integration testing against pre-release builds.

### 🧪 Testing Mode
```
Personality: Pragmatist
Wallet: Full-Access
Environment: Staging
Learning: All enabled
Auto: All enabled
```
Safe practice with real operations.

### 🛠️ Developer Mode
```
Personality: Expert
Wallet: Full-Access
Environment: Development
Learning: Advanced only
Auto: Errors and examples
```
Direct localhost backend access.

## Troubleshooting Setup

### "I can't find the configuration file"
- Setup creates `.claude/galachain-omnitool.local.md`
- Check if `.claude/` directory exists in your project
- Run setup again to recreate

### "Private key isn't being recognized"
- Check `GALACHAIN_PRIVATE_KEY` environment variable
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

### "Staging or QA1 seems broken"
- Staging/QA1 backends may occasionally be under maintenance
- Check `/omni-tool:topics` to verify MCP connection
- Try switching to `production` with `/omni-tool:setup` if blocked

## Next Steps

1. **Run setup**: `/omni-tool:setup`
2. **Choose your personality**: Pick what feels right
3. **Try a question**: `/omni-tool:ask token-creation`
4. **Browse topics**: `/omni-tool:topics`
5. **Build something**: Ask the agent to help you create your first token or trade!

Welcome to GalaChain development! 🚀
