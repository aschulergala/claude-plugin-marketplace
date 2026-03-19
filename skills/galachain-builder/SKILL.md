---
name: galachain-builder
description: GalaChain application builder and operator skill for Codex. Use when users want end-to-end help building or integrating a GalaChain app, planning token launch or trading workflows, implementing liquidity, bridging, streaming, moderation, or admin features, or safely executing GalaChain MCP operations from Codex.
---

# GalaChain Builder

Use this skill for build-oriented GalaChain work where the user wants an outcome, not just a topic explanation.

## Quick Start

1. Decide whether the task is planning, implementation guidance, or live execution.
2. Read `references/codex-setup.md` if the `gala-launchpad` MCP server may be missing.
3. Read `references/build-playbook.md` to map the user goal to the right GalaChain workflow.
4. If the MCP server is available, prefer `gala_launchpad_explain_sdk_usage` plus the relevant `gala_launchpad_*` tools for authoritative details and execution.

## Session Startup Check

At the start of a GalaChain build or execution session:

1. Verify whether the `gala-launchpad` MCP server is available.
2. If GalaChain tools are missing, stop retrying them.
3. Route the user to `references/codex-setup.md`.
4. Continue with design and workflow guidance from this skill even when live tools are unavailable.

## Builder Workflow

1. Understand the desired product or operation.
2. Break the work into discovery, implementation, and execution phases.
3. Map the task to the closest GalaChain topics from `references/build-playbook.md`.
4. Use read-only discovery first when the task touches live assets, pools, or account state.
5. Execute state-changing operations only after the environment and inputs are clear.

## Safety Rules

- Treat `production` as a live environment with real consequences.
- Confirm the target environment before any state-changing step.
- Prefer a smaller validation step before a larger token, liquidity, or bridging action.
- Name the GalaChain topic or operation explicitly so the user can verify intent.
- When an MCP tool fails at runtime, explain the likely cause and fall back to topic guidance instead of blind retries.

## Typical Uses

- Build a token launch workflow
- Design or troubleshoot a trading bot
- Plan DEX liquidity management
- Integrate bridging flows
- Add streaming, chat, or moderation features
- Set up analytics, leaderboards, or event-driven processing
- Map SDK examples to operational GalaChain MCP calls

## Response Structure

When helping with a build:

1. State the target workflow.
2. Break it into steps.
3. Identify the GalaChain topics involved.
4. Call out environment or credential requirements.
5. Offer the next concrete implementation or execution step.

## Files

- `references/codex-setup.md`: Codex MCP installation and restart steps
- `references/build-playbook.md`: workflow routing, implementation patterns, and execution guidance
