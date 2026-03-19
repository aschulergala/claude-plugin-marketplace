# GalaChain Agent Plugin Marketplace

Official marketplace for GalaChain Claude Code plugins, now with a Codex-compatible skill for the GalaChain OmniTool.

## Claude Code Install

```bash
claude plugins add omni-tool
```

## Codex Install

Install the Codex skill from this repository:

```bash
$skill-installer https://github.com/<repo-owner>/claude-plugin-marketplace/tree/<ref>/skills/galachain-omni
```

Replace `<repo-owner>` with the GitHub owner that hosts the skill and `<ref>` with the branch or tag you want to install.

After installing, add the `gala-launchpad` MCP server to `~/.codex/config.toml` using [`skills/galachain-omni/references/codex-setup.md`](skills/galachain-omni/references/codex-setup.md), then restart Codex.

## Features

- **310 MCP Tools** - Comprehensive GalaChain operations
- **38 Categories** - Trading, liquidity, bridging, and more
- **63 Teaching Topics** - AI-powered learning
- **8 Learning Paths** - Structured skill development
- **Codex Skill** - Native `SKILL.md` package for Codex and other `AGENTS.md` readers

## Categories

| Category | Tools | Description |
| --- | --- | --- |
| Trading | 20+ | Buy, sell, track tokens |
| Liquidity | 15+ | DEX pools, fee collection |
| Bridging | 18+ | Cross-chain operations |
| Learning | 63 topics | AI-powered tutoring |

## Repository Layout

- `plugins/omni-tool` - Claude Code plugin source
- `skills/galachain-omni` - Codex and OpenSkills-compatible skill
- `AGENTS.md` - Universal discovery entry for agent tools

## Links

- [Landing Page](https://aschulergala.github.io/claude-plugin-marketplace/)
- [Claude Marketplace Manifest](https://aschulergala.github.io/claude-plugin-marketplace/marketplace.json)
- [Codex Skill](skills/galachain-omni/SKILL.md)
- [AGENTS.md](AGENTS.md)
- [Gala Games](https://gala.com)

## License

MIT
