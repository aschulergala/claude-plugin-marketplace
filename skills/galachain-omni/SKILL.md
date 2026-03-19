---
name: galachain-omni
description: GalaChain learning, build, and troubleshooting skill for Codex. Use when users ask to learn GalaChain, configure the gala-launchpad MCP server, map natural-language questions to GalaChain topics, or build token, trading, liquidity, bridging, NFT, streaming, moderation, or admin workflows with GalaChain tools.
---

# GalaChain Omni

Use this skill to translate the existing GalaChain OmniTool plugin into a Codex-friendly workflow.

## Quick Start

1. Determine whether the user wants setup help, conceptual teaching, or live execution.
2. Read `references/codex-setup.md` when the user needs MCP installation or environment configuration.
3. Read `references/topics.md` when you need the full GalaChain topic catalog or learning paths.
4. Read `references/workflows.md` when you need to map Claude commands and agent behavior to Codex usage.

## Core Workflow

1. Confirm whether the `gala-launchpad` MCP server is available in Codex.
2. If it is missing, stop retrying missing `gala_launchpad_*` tools and guide the user through `references/codex-setup.md`.
3. If the user asks a broad "how do I..." question, map it to the closest topic from `references/topics.md`.
4. When the server is available, prefer the real GalaChain MCP tools and `gala_launchpad_explain_sdk_usage` for authoritative explanations.
5. When the server is unavailable, answer from the references in this skill and explicitly note that live GalaChain tools are not connected.

## Execution Rules

- Treat `production` as real-money or real-asset territory. Be explicit before suggesting write operations there.
- Confirm the target environment when the user wants to execute trades, transfers, bridging, token creation, liquidity changes, moderation actions, or admin actions.
- Prefer read-only discovery first: inspect pools, balances, token details, routes, or season data before suggesting transactions.
- Do not keep retrying a missing GalaChain MCP tool. Missing-tool errors usually mean the MCP server is not configured in Codex yet.

## Command Mapping

The original Claude plugin exposes slash commands. In Codex, map them like this:

- `/omni-tool:ask` -> natural-language requests plus topic routing through this skill
- `/omni-tool:topics` -> `references/topics.md`
- `/omni-tool:setup` -> `references/codex-setup.md`
- `galachain-builder` -> use this skill for the same learn-and-build workflow

## Response Style

When teaching a topic:

1. Explain what it does.
2. Explain when to use it.
3. Show the relevant topic name so the user can ask follow-up questions precisely.
4. Use the real MCP tool when available.
5. Call out common mistakes, especially environment confusion and wallet permissions.

## Files

- `references/codex-setup.md`: Codex MCP config and environment setup
- `references/topics.md`: topic catalog, categories, and learning paths
- `references/workflows.md`: Codex equivalents for the Claude plugin commands and agent behavior
