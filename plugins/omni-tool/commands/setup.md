---
name: omni-tool:setup
description: Configure the GalaChain OmniTool plugin and MCP server
arguments: []
---

# GalaChain Setup

Use `/omni-tool:setup` to connect the GalaChain MCP server and choose how explanations should be taught. The server configuration and plugin preferences are separate: `~/.claude.json` configures the process and its environment, while `.claude/galachain-omnitool.local.md` stores presentation preferences only.

## Usage

```text
/omni-tool:setup
```

Setup checks the MCP connection first. If the teaching tool is unavailable, stop MCP calls and show the installation entry below. After a configuration change, restart Claude Code so the MCP process is recreated with the new environment.

## 1. Check the MCP connection

Call `gala_launchpad_explain_sdk_usage` with the `installation` topic. If the tool is unknown or missing, do not retry it. Explain that the MCP server is not connected and show this `~/.claude.json` entry, keeping all unrelated JSON and MCP server entries intact:

```json
{
  "mcpServers": {
    "gala-launchpad": {
      "command": "npx",
      "args": ["-y", "@gala-chain/launchpad-mcp-server@^7.0.0"],
      "env": { "ENVIRONMENT": "prod" }
    }
  }
}
```

The server accepts exactly two `ENVIRONMENT` values:

- `prod` — the production GalaChain network. Writes affect the real network and may move assets.
- `stage` — the staging test network, for trying workflows against test infrastructure.

The server defaults to `prod` when `ENVIRONMENT` is unset. For setup, ask the user to choose `prod` or `stage`, then write that exact value. Do not write any other environment string; the v7 server rejects anything except `prod` and `stage`.

After the entry is merged into `~/.claude.json`, remind the user to restart Claude Code. When connected, report that the server exposes 323 tools and the local learning index covers 69 topics. The live `gala_launchpad_explain_sdk_usage` topic enum is authoritative if the local index differs.

## 2. Choose wallet access

If the user is deciding between modes, map the choice to the task rather than presenting it as an account tier:

| Task | Starting point | Why |
|---|---|---|
| Read docs, inspect tokens, or learn SDK concepts | Read-only on `stage` | No signing key is needed for the lesson. |
| Build a screen using current token and pool data | Read-only | Read workflows can be validated before adding writes. |
| Try a signed workflow | Full-access on `stage` | Uses a test environment, but still requires a protected signer. |
| Submit an intended real transaction | Full-access on `prod` | Real-network effects; review each transaction before execution. |

The environment and wallet mode answer different questions. A `stage` server without a key remains read-only; a `prod` server with a key can sign real operations.


Ask about the user's immediate task before recommending a mode. A tutorial, read dashboard, or token lookup usually needs no signer. A workflow that submits a transaction needs a configured signer, but that does not mean every request should be executed automatically.

When helping configure the server, describe the distinction plainly: `ENVIRONMENT` selects which network the MCP process connects to, while `PRIVATE_KEY` determines whether it can sign. Choosing `stage` does not create or fund a test wallet, and choosing a full-access preference does not itself grant signing ability.


### Read-only (recommended while learning)

No signing wallet is configured. Users can explore read topics such as `token-details`, `fetch-pools`, `balances`, `price-history`, and `fetch-dex-pools`. Write actions cannot be signed. This is a good default for learning, dashboards, and checking an unfamiliar workflow.

### Full-access

Full-access requires the Ethereum-format private key in the MCP server process environment variable `PRIVATE_KEY`. Without it, the server remains read-only. Store it in the `env` block of the `gala-launchpad` entry in `~/.claude.json`, or provide it in the shell environment that launches Claude Code:

```json
{
  "mcpServers": {
    "gala-launchpad": {
      "command": "npx",
      "args": ["-y", "@gala-chain/launchpad-mcp-server@^7.0.0"],
      "env": {
        "ENVIRONMENT": "stage",
        "PRIVATE_KEY": "0x..."
      }
    }
  }
}
```

A key placed here is a secret in `~/.claude.json`; protect that file, do not commit or share it, and use a wallet with only the funds and permissions needed for the work. Never put keys in the plugin preferences file, project source, examples, chat, or a repository `.env` that could be committed.

Optional environment variables:

- `SOLANA_PRIVATE_KEY` — needed for Solana bridge operations when that path requires a Solana signer.
- `ETHEREUM_RPC_URL`, `SOLANA_RPC_URL` — optional RPC overrides for bridge operations.
- `STREAM_WEBSOCKET_URL`, `STREAM_ADMIN_API_KEY`, `USER_API_KEY` — optional streaming, administration, and API-key feature configuration.
- `TIMEOUT` — request timeout in milliseconds; default is `30000`.
- `DEBUG=true` — verbose server logs for troubleshooting.

Only configure optional credentials for features the user intends to use. Treat all key and API-key values as secrets.

## 3. Select teaching preferences

Ask one choice at a time when the user is unsure. A useful setup conversation can follow this order:

1. Confirm the MCP connection and explain the selected network.
2. Ask whether the user wants read-only learning or expects to sign transactions.
3. If signing is needed, explain where the process reads `PRIVATE_KEY` and the secret-handling consequence before they configure it.
4. Ask which explanation style and learning options are useful.
5. Save only preferences in the local preferences file, summarize the selected server environment, and remind them to restart if MCP configuration changed.


Explain what each preference changes, then record the user's choices in `.claude/galachain-omnitool.local.md`:

### Personality

- **Tutor** (default): patient, thorough explanations; defines terms, includes practical cautions, and suggests a next topic. Good for a first project or learning a new part of the SDK.
- **Expert**: concise and technically dense; assumes familiarity with DeFi and focuses on parameters, trade-offs, and edge cases.
- **Pragmatist**: balanced explanations with a short rationale and a usable next step. Good when building and learning at the same time.
- **Socratic**: asks focused questions to help the user reason through a design. Use when the user wants to explore options before choosing.

### Wallet mode preference

Record `read-only` or `full-access` as the user's intended workflow. This is a preference, not a security boundary: actual signing ability depends on whether `PRIVATE_KEY` is present in the MCP process environment. Explain that read-only is the safe learning default and that writes need a signer and explicit user intent.

### Learning preferences

- **Show advanced topics** (default `true`): include optimization and deeper follow-up material once the core concept is clear.
- **Include best practices** (default `true`): mention security, validation, safe defaults, and maintainability where relevant.
- **Include error handling** (default `true`): explain likely failure points and recovery behavior, especially for queued DEX swaps.
- **Code style** (default `typescript`): prefer TypeScript examples; the live topic response is the source for exact SDK method signatures.

### Automatic help

- **Auto-explain errors** (default `true`): when a tool fails, explain the error and consult the most relevant live topic, unless the MCP server itself is missing.
- **Auto-suggest examples** (default `true`): include relevant examples without requiring a separate request.

## 4. Preferences file template

Treat these values as guidance for how the assistant presents material, not as server enforcement. For example, `wallet_mode: read-only` tells the assistant to prefer read workflows; it cannot remove a key already configured in the MCP process. Conversely, `wallet_mode: full-access` cannot enable writes when the server has no signer.


Generate or update `.claude/galachain-omnitool.local.md` with the selected teaching preferences. Do not put network credentials or private keys here. Environment and wallet access are established by the MCP process environment, not by this preferences document.

```yaml
---
# GalaChain OmniTool teaching preferences
agent_personality: tutor # tutor, expert, pragmatist, socratic
wallet_mode: read-only # preference only; actual writes also require PRIVATE_KEY in MCP env
show_advanced_topics: true
include_best_practices: true
include_error_handling: true
code_style: typescript
auto_explain_errors: true
auto_suggest_examples: true
---

# Your custom notes...
```

Preserve custom notes and unrelated settings when updating an existing file. Do not put `PRIVATE_KEY`, `SOLANA_PRIVATE_KEY`, or API credentials into this template.


### Optional environment setup examples

The following are shell variable names supported by the server. Set only the values required for the selected workflow; never paste a live value into documentation or commit it:

```bash
export PRIVATE_KEY="0x..."              # Enables signed GalaChain operations
export SOLANA_PRIVATE_KEY="..."         # Optional signer for applicable Solana routes
export ETHEREUM_RPC_URL="https://..."   # Optional bridge RPC override
export SOLANA_RPC_URL="https://..."     # Optional bridge RPC override
export STREAM_WEBSOCKET_URL="wss://..." # Optional streaming endpoint
export STREAM_ADMIN_API_KEY="..."       # Optional streaming administration
export USER_API_KEY="..."               # Optional API-key features
export TIMEOUT="30000"                  # Milliseconds; this is the default
export DEBUG="true"                     # Enables verbose diagnostics
```

These variables must reach the process running the MCP server. Values defined only in the plugin preferences file are not passed to the server. If values are placed in `~/.claude.json`, keep that file private and restart Claude Code after editing it.

### Configuration recap

Before finishing, distinguish the three choices in the recap:

- **Network:** `ENVIRONMENT` selects `prod` or `stage`.
- **Signing:** `PRIVATE_KEY` enables full-access signing; omission means read-only. Applicable Solana bridge flows can also need `SOLANA_PRIVATE_KEY`.
- **Teaching style:** the local preferences select personality, code style, and automatic explanation behavior.

This prevents a teaching preference from being mistaken for an access control or network setting.

## 5. v7-only presets

Presets are starting points. Always let the user choose the environment and explain that full-access requires a server-side key.

### Learning

```text
Personality: tutor
Wallet preference: read-only
Environment: stage
Learning: advanced topics, best practices, and error explanations enabled
Auto features: explain errors and suggest examples
```

For a beginner who wants hands-on familiarity while avoiding signed writes.

### Trader

```text
Personality: expert
Wallet preference: full-access
Environment: prod
Learning: concise, with relevant best practices and error recovery
Auto features: explain errors
```

For an experienced user who explicitly intends real production operations. Confirm each consequential write. Full-access requires `PRIVATE_KEY`; the key is stored in `~/.claude.json` if configured there.

### Safe testing

```text
Personality: pragmatist
Wallet preference: full-access
Environment: stage
Learning: best practices and error explanations enabled
Auto features: explain errors and suggest examples
```

For exercising signed flows in staging. `PRIVATE_KEY` is still a secret, even for stage; use a key intended for testing.

The server supports only `prod` and `stage`; do not create presets for other networks.

## After setup

Give a short recap in plain language, for example: “The server is configured for `stage`, your learning style is tutor, and the plugin preference is read-only. Restart Claude Code to reload the server.” Do not repeat any secret value in the recap.


1. Restart Claude Code after changing `~/.claude.json`.
2. Run `/omni-tool:topics` to browse the local index.
3. Run `/omni-tool:ask installation` or ask a natural-language question.
4. Start with read-only topics, then configure signing only when a workflow requires it.
5. Before a write, explain the expected effect, network, amount or target, and relevant recovery behavior; get explicit confirmation.

## Changing configuration later

Before editing, identify whether the requested change affects the server process or only teaching behavior. Network and credential changes require an MCP environment update and restart; personality and learning options belong in the local preferences file and can be changed independently.


- Re-run `/omni-tool:setup` to review preferences and server settings.
- Edit `.claude/galachain-omnitool.local.md` to change teaching style; these local preferences take effect without changing server credentials.
- Edit the `gala-launchpad` entry in `~/.claude.json` to switch `ENVIRONMENT` between `prod` and `stage`, or to update MCP environment variables. Preserve other entries and restart Claude Code afterward.
- `/omni-tool:ask topic --personality=expert` changes the style for one answer when the command options are supported by the caller.

Keep the environment, signing, and presentation settings separate when diagnosing setup. Fix only the layer that is failing, then restart the MCP process when server environment changes.

## Troubleshooting

### The setup command cannot find the MCP tool

Check that `~/.claude.json` has the `gala-launchpad` entry and the package pin `@^7.0.0`. Restart Claude Code after editing. If the error says the tool is unknown, stop calling it and use the installation instructions above.

### Server exits during startup

Check `ENVIRONMENT`: it must be exactly `prod` or `stage`. If the process reports malformed configuration, inspect the JSON syntax and preserve the enclosing `mcpServers` structure.

### Writes are unavailable

The server runs read-only when `PRIVATE_KEY` is omitted. Put an Ethereum-format key in the `env` block for `gala-launchpad` or the shell environment used to start Claude Code, then restart. Protect `~/.claude.json` as a secret-bearing file.

### A Solana bridge cannot sign

Check whether the selected bridge operation needs `SOLANA_PRIVATE_KEY`; do not assume `PRIVATE_KEY` is a substitute for a Solana signer. For RPC connectivity, check the optional `SOLANA_RPC_URL` or `ETHEREUM_RPC_URL` override and consult the live `bridge-operations` topic.

### Requests time out or logs are not useful

`TIMEOUT` is measured in milliseconds and defaults to `30000`. Increase it only when the operation justifies a longer wait. Set `DEBUG=true` temporarily for verbose logs, then remove it when done.

### Preferences seem ignored

Confirm the file is `.claude/galachain-omnitool.local.md` in the project and contains valid frontmatter. These settings affect teaching presentation; they do not install MCP, switch environments, or grant signing access.

## Next steps

Use `/omni-tool:ask token-details` to inspect a token, `/omni-tool:ask buy-tokens` to learn the bonding-curve flow, or `/omni-tool:topics` to browse all 69 indexed topics. The topic enum returned by the connected v7 server remains the live source of truth.
