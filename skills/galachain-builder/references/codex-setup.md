# Codex Setup

Use this file when the user wants to execute GalaChain MCP tools from Codex and the `gala-launchpad` server is not configured.

## Add the MCP Server

Add this block to `~/.codex/config.toml`:

```toml
[mcp_servers.gala-launchpad]
command = "npx"
args = ["-y", "@gala-chain/launchpad-mcp-server@beta"]
startup_timeout_sec = 120.0
tool_timeout_sec = 300.0

[mcp_servers.gala-launchpad.env]
ENVIRONMENT = "qa1"
```

## Environment Choices

- `production`: live GalaChain environment
- `qa1`: pre-release QA environment
- `staging`: test environment
- `development`: local or development backend

## After Configuration

1. Save the file.
2. Restart Codex.
3. Re-check GalaChain MCP availability before attempting live execution.

## Risk Notes

- Write operations in `production` can affect live balances, pools, or governance state.
- Favor `qa1`, `staging`, or `development` while testing new flows.
