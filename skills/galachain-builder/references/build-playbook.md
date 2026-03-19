# Build Playbook

Use this file to route product requests to the correct GalaChain topics and execution phases.

## Workflow Pattern

For most build requests, work in this order:

1. Discovery
2. Design
3. Read-only validation
4. State-changing execution
5. Post-execution verification

## Goal Routing

### Launch A Token

Use these topics:

- `token-creation`
- `token-status`
- `token-distribution`
- `pool-graduation`

Suggested order:

1. Define token parameters and supply model.
2. Create the token.
3. Inspect token status and holder distribution.
4. Plan graduation or post-launch DEX behavior.

### Build A Trading Bot

Use these topics:

- `trading-quotes`
- `buy-tokens`
- `sell-tokens`
- `dex-trading`
- `recent-trades`
- `event-subscriptions`

Suggested order:

1. Define the strategy and venue.
2. Pull quotes and market state.
3. Simulate or validate read-only assumptions.
4. Execute bounded trades.
5. Track fills and events.

### Add Liquidity Features

Use these topics:

- `fetch-dex-pools`
- `liquidity-positions`
- `advanced-dex-analysis`
- `fetch-current-dex-leaderboard`

Suggested order:

1. Discover candidate pools.
2. Analyze pool conditions and incentives.
3. Create or adjust liquidity positions.
4. Verify resulting position state and performance metrics.

### Add Bridging

Use these topics:

- `bridge-operations`
- `wrap-unwrap-operations`

Suggested order:

1. Verify supported assets and networks.
2. Estimate fees and route constraints.
3. Execute a small validation transfer if risk is non-trivial.
4. Track bridge status to completion.

### Add Streaming Or Community Features

Use these topics:

- `streaming`
- `stream-chat`
- `messages`
- `ban-management`
- `moderator-invites`
- `content-flag-management`

Suggested order:

1. Set up stream primitives.
2. Add chat and messaging.
3. Layer moderation controls.
4. Verify permissions, bans, and operational settings.

### Add Analytics Or Admin Features

Use these topics:

- `trading-analytics`
- `platform-stats`
- `fetch-dex-aggregated-volume-summary`
- `api-key-management`
- `event-subscriptions`
- `websocket-admin`

Suggested order:

1. Identify which metrics or controls are needed.
2. Select the correct event or stats source.
3. Validate with read-only calls first.
4. Apply admin changes only after confirming environment and privileges.

## Missing MCP Tools

If `gala_launchpad_*` tools are unavailable:

1. Stop retrying.
2. Explain that the `gala-launchpad` MCP server is not configured in Codex.
3. Use `codex-setup.md`.
4. Continue with architecture or implementation guidance while the user fixes setup.

## Execution Checklist

Before a state-changing call:

1. Confirm the environment.
2. Confirm the asset, token, pool, or destination identifiers.
3. Confirm credentials or wallet prerequisites.
4. Prefer a dry run, quote, or read-only inspection first when available.
5. Explain what success and failure look like before execution.
