# Agent Skills

This repository publishes GalaChain agent integrations for both Claude Code and Codex-style skill loaders.

## Available Skills

- `galachain-omni`
  - Path: `skills/galachain-omni`
  - Use when the user wants to learn GalaChain, configure the `gala-launchpad` MCP server for Codex, or build and troubleshoot token, trading, liquidity, bridging, NFT, streaming, moderation, or admin workflows.
- `galachain-builder`
  - Path: `skills/galachain-builder`
  - Use when the user wants end-to-end help building or operating a GalaChain application, including implementation planning, feature selection, safe execution, and multi-step GalaChain workflows.

## Install

- Codex: `$skill-installer https://github.com/<repo-owner>/claude-plugin-marketplace/tree/<ref>/skills/galachain-omni`
- Codex builder persona: `$skill-installer https://github.com/<repo-owner>/claude-plugin-marketplace/tree/<ref>/skills/galachain-builder`
- Manual Codex install: copy `skills/galachain-omni` into `~/.codex/skills/`
- Claude Code: use the existing plugin in `plugins/omni-tool`

Replace `<repo-owner>` with the GitHub owner that hosts the skill and `<ref>` with the target branch or tag.

## Maintenance

- Treat `plugins/omni-tool` as the Claude-facing source of truth.
- Keep `skills/galachain-omni` and `skills/galachain-builder` aligned with the topic catalog and MCP server behavior documented in `plugins/omni-tool`.
