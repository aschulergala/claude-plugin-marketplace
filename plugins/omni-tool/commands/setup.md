---
name: omni-tool:setup
description: Configure the GalaChain OmniTool plugin and MCP server
arguments: []
---

# GalaChain Setup

Configure teaching preferences and the MCP server connection.

## MCP connection check

First call `gala_launchpad_explain_sdk_usage` with topic `installation`. If the tool is missing or unknown, stop and explain that the MCP server is not installed. Show this `~/.claude.json` entry, preserving any other MCP server entries already in the file:

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

After editing `~/.claude.json`, restart Claude Code. The supported environments are exactly:

- `prod` — real GalaChain mainnet
- `stage` — test network

Ask which environment to use. Write exactly `prod` or `stage` to `ENVIRONMENT`; default to `prod` only when the user selects mainnet or accepts the default. Do not offer or write other values.

## Preferences

Offer personality (`tutor`, `expert`, `pragmatist`, `socratic`), wallet mode (`read-only` or `full-access`), code style, and whether to include best practices and error explanations. Save plugin preferences in `.claude/galachain-omnitool.local.md`. Keep private keys in environment variables; never put secrets in config or preferences files.

When merging `~/.claude.json`, preserve unrelated settings and MCP servers, then create or update only the `gala-launchpad` entry with:

```json
{
  "command": "npx",
  "args": ["-y", "@gala-chain/launchpad-mcp-server@^7.0.0"],
  "env": { "ENVIRONMENT": "prod" }
}
```

Use `stage` in place of `prod` only when the user selects the test network. Remind them to restart Claude Code after writing the config.

## Verify

Once connected, report 323 MCP tools and 69 indexed topics. The `gala_launchpad_explain_sdk_usage` topic enum is the live authority for topic names. Use `/omni-tool:topics` to browse the local index and `/omni-tool:ask` to ask about a topic.
