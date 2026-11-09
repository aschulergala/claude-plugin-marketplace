# GalaChain Claude Plugin Marketplace

Official marketplace for GalaChain Claude Code plugins.

## Quick Install

```bash
claude plugins add omni-tool
```

Optional subsets: `claude plugins add launchpad` or `claude plugins add swap`.

## Features

- **326 MCP tools** for GalaChain operations (core 47, launchpad 244, gswap 32, composite 3)
- **68 teaching topics** indexed for the v7 SDK
- **8 learning paths** for structured learning

**Version 2.3.0 runs the single `@gala-chain/gala-mcp-server` package (1.1.0 or newer 1.x; it replaces the deprecated `@gala-chain/launchpad-mcp-server`).** Toolsets are chosen with the `GALA_TOOLSETS` environment variable (`core`, `launchpad`, `gswap`, `composite`; default all). Two lighter plugins ship alongside: `launchpad` (core + launchpad, 291 tools) and `swap` (core + gswap, 79 tools). The supported environments are `prod` (real GalaChain mainnet) and `stage` (test network).

## Links

- [Landing Page](https://aschulergala.github.io/claude-plugin-marketplace/)
- [Plugin Manifest](https://aschulergala.github.io/claude-plugin-marketplace/marketplace.json)
- [GitHub](https://github.com/aschulergala/claude-plugin-marketplace)
- [Gala Games](https://gala.com)

## License

MIT
