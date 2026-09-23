---
name: learning-galachain
description: Learn to build on GalaChain with the v7 SDK and indexed topics
triggers:
  - "How do I learn GalaChain?"
  - "Teach me about GalaChain"
  - "What can I build with GalaChain?"
  - "How does this teaching system work?"
  - "I want to learn GalaChain from scratch"
  - "Show me the learning roadmap"
  - "What are all the things I can do?"
---

# Learning GalaChain

This skill uses `gala_launchpad_explain_sdk_usage` to teach from current v7 SDK examples, matching MCP tools, pitfalls, and related material. The live tool's `topic` enum is the source of truth. `/omni-tool:topics` is a convenient local index of 69 topics, not a substitute for the live enum; honor exact live values if the server has changed.

## How a topic lesson works

Ask the teaching tool for the closest exact topic. Build the answer around:

1. **Concept:** what the capability does and the problem it solves.
2. **Use case:** when it fits, with any prerequisites.
3. **Steps:** a small ordered workflow.
4. **v7 example:** the returned SDK example and its corresponding MCP tool names.
5. **Parameters and trade-offs:** values that affect outcome, cost, or risk.
6. **Pitfalls:** version-specific behavior, common mistakes, and recovery.
7. **Next topics:** relevant exact values from the live enum.

Adapt the depth to the selected personality. Tutor defines terms and progresses gradually; expert focuses on decisions and edge cases; pragmatist shows a useful implementation path; Socratic guides discovery with focused questions. If the MCP teaching tool is missing, stop calling it, state that live examples are unavailable, and point to `/omni-tool:setup`.

## Learning paths

Treat these sequences as guided routes rather than prerequisites. The user can skip a topic when they already know the concept. Briefly explain why the next topic follows from the previous one, and use the live topic output for exact examples.

Each sequence below uses only topic names in the v7 local index. Follow the live enum if a connected server has newer topics.

### Path 1: Beginner foundations

Build vocabulary and learn safe read workflows before transaction details. By the end, the learner should be able to explain network selection, identify whether an operation needs a signer, and find canonical token data.

Build a mental model before attempting a write:

1. `installation` — connect to the v7 server and understand `prod` versus `stage`.
2. `wallet-connect` — learn read-only versus signer-backed behavior.
3. `token-identification` — distinguish a Launchpad token name from a full DEX identifier.
4. `token-details` — inspect canonical token information.
5. `fetch-pools` — browse Launchpad pools and token listings.
6. `balances` — understand balance reads and address context.
7. `error-handling` — learn how to diagnose failures and recover safely.

Practice the read topics first. A configured wallet mode in preferences does not grant signing access; writes require `PRIVATE_KEY` in the MCP process environment.

### Path 2: Trading and token lifecycle

Follow the token from its Launchpad identity through a possible DEX transition. The key checkpoint is recognizing that graduation changes both the trading surface and the identifier format.

Understand how the trading surface changes with token state:

1. `token-details` → `token-identification` for identity and metadata.
2. `buy-tokens` → `sell-tokens` for bonding-curve execution.
3. `trading-quotes` → `trading-analytics` for estimation and context.
4. `pool-graduation` → `graduation-detection` → `token-status` to detect lifecycle changes.
5. `dex-token-discovery` → `fetch-dex-pools` → `dex-trading` after graduation.
6. `queued-swap-recovery` → `error-handling` for interrupted DEX confirmation.
7. `trade-history` → `recent-trades` to explore activity records.

Trade-off to understand: bonding-curve methods use the simple token name; DEX methods use a full `TokenClassKey`. Quotes, fees, and slippage bounds matter, and a queued swap is not complete until confirmation resolves.

### Path 3: DEX, liquidity, and analytics

Start from market discovery, then compare swaps, position management, and activity data. Learners should be able to separate a quote from a submitted trade and describe what an LP range means.

Learn discovery before managing positions:

1. `dex-token-discovery` and `fetch-dex-pools` to find markets.
2. `spot-prices-smart-routing` and `advanced-dex-analysis` to evaluate price and pool context.
3. `dex-trading` and `queued-swap-recovery` for swap and recovery flow.
4. `liquidity-positions` for position reads and liquidity operations.
5. `fetch-current-dex-season`, `fetch-all-dex-seasons`, and `fetch-current-dex-leaderboard` for current DEX programs.
6. `fetch-dex-leaderboard-by-season-id`, `fetch-dex-aggregated-volume-summary`, and `weekly-challenge` for historical or challenge data.

Liquidity has price-range and inventory risks. Compare position behavior and possible fee outcomes; never equate potential fees with guaranteed return. Use `confirm()` for queued swap outcomes and `confirmSwap(uniqueKey)` to recover the same submission rather than resubmitting.

### Path 4: Create and operate a token

Connect the launch checklist to the information and operations users need afterward. Review what is validated before launch, what is read after launch, and which actions can change balances or supply.

1. `restricted-names` for name constraints.
2. `token-creation` for validation, launch fee, image, and creation flow.
3. `token-details`, `token-status`, and `fetch-pools` for discovery and status.
4. `token-distribution`, `holders`, and `balances` for ownership views.
5. `transfers` and `locks` for token movement and lock workflows.
6. `pool-graduation`, `graduation-detection`, and `dex-trading` for the post-graduation path.

Name and symbol checks can become stale before a write. Explain signing requirements and validate the target network. Burn, transfer, and graduation operations may have consequential effects; use the live topic and explicit confirmation.

### Path 5: Bridge and cross-network flows

Learn the route and status model before configuring signers or submitting anything. The learner should be able to restate the complete source-to-destination path and explain how they will check status.

1. `bridge-operations` for routes, fees, and status.
2. `wrap-unwrap-operations` for channel wrapping behavior.
3. `wallet-connect` and `error-handling` for signer and failure context.

A bridge and a wrap are different workflows. For Solana bridging, the server may require `SOLANA_PRIVATE_KEY`; `ETHEREUM_RPC_URL` and `SOLANA_RPC_URL` are optional bridge RPC overrides. Keys belong in the MCP process environment, never in this skill or the plugin preferences. Explain asset, source, destination, fee, and status tracking before a user signs.

### Path 6: Streaming and community features

Combine realtime updates with moderation and content workflows while keeping permissions visible. Compare when a one-time read is enough with when an event subscription is useful.

1. `streaming` and `gdex-stream` for stream lifecycle and realtime stream events.
2. `stream-chat`, `chat-messages`, and `messages` for chat and message flows.
3. `comments`, `content-reactions`, and `content-flag-management` for community content.
4. `ban-management`, `token-ban-management`, `global-bans`, and `moderator-invites` for moderation.
5. `ai-moderation` and `global-feed-subscription` for moderation configuration and platform events.

Separate user-facing operations from moderator or administrative capabilities. Check authorization requirements in the live topic before suggesting a write.

### Path 7: Application integration and advanced topics

Use this path when the core workflow is clear and the application needs identity, events, or privileged capabilities. Keep administrative capabilities behind the correct role and make the data source visible in the design.

1. `mcp-to-sdk-mapping` to understand tool-to-method mapping.
2. `multi-wallet` and `session-auth` for account and session patterns.
3. `event-subscriptions`, `notifications`, and `events-tracking` for event-driven features.
4. `api-key-management` and `websocket-admin` for privileged integration needs.
5. `platform-stats`, `oembed`, `referral-system`, and `nft-collection-management` for adjacent platform features.
6. `utilities-and-helpers`, `utilities-system`, and `local-calculations` for supporting functionality.

Administrative topics can require elevated access. Confirm the user's intended authority and consult the current topic before proposing execution.

## Checkpoints along the paths

Use a small checkpoint after each cluster so the learner connects topics instead of collecting names:

- **Foundations:** can they tell which information is safe to read without a signer and which action would require signing?
- **Trading:** can they tell whether a token is on the bonding curve or DEX, and which identifier each path expects?
- **Liquidity:** can they explain how a price range changes a position and name the uncertainty around fee outcomes?
- **Token operation:** can they state which values need validating before launch, transfer, lock, or graduation?
- **Bridge:** can they identify both networks, the asset, signer needs, fee, and status path?
- **Community:** can they distinguish a user-facing action from a moderation or administrator action?
- **Integration:** can they explain what event or identity data the application needs and which topics supply it?

If the learner is unsure, fetch the next relevant topic and narrow the question rather than jumping to a write example.

## Topic-specific study prompts

Use these questions to turn a path into active learning:

- **Foundations:** Which calls need a signer, and what does the selected network mean for the result?
- **Trading:** Which identifier and trading surface apply to this token now? What proves that the operation finished?
- **Liquidity:** What changes when the price leaves a position's range? Which data can be observed before submitting a change?
- **Token operation:** Which launch values are checked in advance, and which can still fail when submitted?
- **Bridge:** What identifies the source and destination asset, and how will status be checked afterward?
- **Community:** Which role is allowed to moderate, and how should the app explain that boundary?
- **Integration:** Does the app need a one-time read, a stream of updates, or both?

The live topic answer should resolve implementation details; these prompts help the learner understand what to look for.

## Practice and review

After each lesson, ask the learner to summarize the next decision or identify which prerequisite they still need. For example, before a DEX trade, check that they understand the full token identifier, quote limits, queued submission, and recovery key. Before bridging, check that source, destination, asset, signer, and tracking are all clear.

A practice sequence should make progress visible without requiring a real write: inspect data, explain the intended operation, review the live example, then decide whether the user actually wants to submit. If the environment or signer is unknown, ask or explain the dependency rather than assuming.

## v7 behavior to keep in mind

Launchpad SDK methods are flat on the SDK. GSwap DEX operations live in namespaces such as `sdk.dex.quoting`, `sdk.dex.swaps`, and `sdk.dex.positions`. Use examples returned by the live teaching topic for exact code and response handling; do not invent method signatures or revive removed flat DEX methods.

For GSwap, `swap()` queues a submission. Call `confirm()` to resolve it. If the process stops or confirmation times out, `queued-swap-recovery` documents how to find the result using the original `uniqueKey`; never create another swap only because the first confirmation was interrupted.

## Topic answer structure

For every lesson, keep the response useful on its own: begin with the concept and use case, then prerequisites and ordered steps. Include an exact live SDK example when requested, name equivalent MCP tools, explain key parameters, and call out pitfalls or recovery. Finish with a small set of related topics. This lets learners use `/omni-tool:ask` as a focused lesson without needing to read the entire skill.

## Project-based practice

When the learner has a concrete project, choose the smallest path that answers the next product question:

- A token detail page can combine `token-details`, `token-identification`, and `fetch-pools` before any signer is introduced.
- A trade preview can combine `trading-quotes`, `balances`, and `error-handling`, then add writes only after the user understands the expected outcome.
- A DEX status screen can combine `fetch-dex-pools`, `liquidity-positions`, and `queued-swap-recovery` to represent both positions and pending outcomes.
- A bridge tracker can focus on `bridge-operations` and status updates without starting a transfer.
- A live community page can combine `streaming`, `stream-chat`, `comments`, and `notifications` according to the events it must show.

Keep the boundary between a teaching example and a production-ready application clear. The live topic provides a method example; product code still needs validation, state management, error display, and appropriate access controls.

## Learning progress

The paths can be combined for a project. A token application can follow foundations, token operation, then trading. A market dashboard can follow foundations and DEX analytics without enabling writes. A community application can focus on streaming and integration topics. Let the user choose based on the feature they want to understand; there is no requirement to finish every path.

At the end of a lesson, suggest one useful next topic and explain why it follows. Keep the recommendation within the live enum, and don't claim the local index is exhaustive if the server exposes newer values.

## Answer depth by learner stage

- **New to GalaChain,** define terms, explain one operation at a time, and prefer reads or `stage`.
- **Building an application:** connect the topic to user experience, data flow, and failure handling.
- **Experienced integrator:** focus on exact live signatures, identity formats, queued state, and operational trade-offs.

Keep the same accurate network and security guidance at every level. A shorter expert answer still needs the important failure behavior.

## Short guided labs

Use these read-first exercises to apply what the topic taught:

1. **Token viewer:** combine `fetch-pools`, `token-details`, and `token-identification`; display the canonical identifier and basic state.
2. **Trade preview:** combine `trading-quotes`, `balances`, and `error-handling`; show the expected result and explain why a preview is not execution.
3. **DEX recovery plan:** combine `dex-trading` and `queued-swap-recovery`; describe confirmation and how to look up the original submission after interruption.
4. **Bridge status page:** combine `bridge-operations` and `notifications`; present route and status without initiating a bridge.
5. **Community panel:** combine `stream-chat`, `chat-messages`, and `content-flag-management`; distinguish reading conversation from moderation actions.

Ask the learner to explain one design choice after each lab. Extend the exercise only after they understand its data, signer, and failure boundaries.

## Revisit and connect topics

When a learner returns to a workflow, recap only the relevant context: current token state, chosen network, signer availability, and the last confirmed result. Then select the next topic from the path. This avoids teaching an operation as if earlier steps had succeeded when they may not have.

Use related topics to answer specific gaps. For example, pair `error-handling` with a failed operation, `token-identification` with an identifier mismatch, and `queued-swap-recovery` with an uncertain DEX result. Prefer the closest current topic over repeating a general tutorial.

## Learn safely

- Start with reads and `stage` for experimentation.
- `prod` is the real network; say so before a consequential operation.
- The server defaults to `prod` when `ENVIRONMENT` is unset and accepts only `prod` or `stage`.
- Without `PRIVATE_KEY`, the server is read-only. Never ask users to paste their key into chat.
- If the key is configured in `~/.claude.json`, warn that the file contains a secret and should not be committed or shared.
- Explain the effect of each write and wait for the user's explicit intent before running it.

## Commands

- `/omni-tool:ask [question or topic]` fetches a focused live lesson.
- `/omni-tool:topics` browses the local topic index; the server enum remains authoritative.
- `/omni-tool:setup` configures the MCP connection and teaching preferences.
