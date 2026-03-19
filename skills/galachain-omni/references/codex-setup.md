# Codex Setup

Use this file when Codex does not have the GalaChain MCP server configured yet.

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

## Environment Values

- `production`: live GalaChain environment
- `qa1`: pre-release QA environment
- `staging`: test network
- `development`: local or development backend

## Wallet Notes

- Read-only discovery does not need a private key.
- Write operations may require the relevant GalaChain wallet environment variables or other project-specific credentials.
- Be explicit about risk before running write operations against `production`.

## After Editing

1. Save `~/.codex/config.toml`.
2. Restart Codex.
3. Re-check whether the `gala-launchpad` server is available before attempting GalaChain tool calls.

## Fallback Guidance

If the server is still unavailable after restart:

- verify that `npx` works on the machine
- verify the package name is spelled exactly `@gala-chain/launchpad-mcp-server@beta`
- try a non-production environment first if the user is testing setup
