# Workflows

Use this file to map the existing Claude plugin behavior to Codex.

## Surface Mapping

| Claude Surface | Codex Equivalent | Notes |
| --- | --- | --- |
| `/omni-tool:ask <topic>` | Ask naturally or invoke `$galachain-omni` | Route the request to a topic from `topics.md` |
| `/omni-tool:topics` | Read `references/topics.md` | Use this as the topic index |
| `/omni-tool:setup` | Read `references/codex-setup.md` | Codex uses `~/.codex/config.toml`, not `~/.claude.json` |
| `galachain-builder` agent | Use `$galachain-omni` | Same teach-and-build behavior |
| Claude post-tool hook for missing MCP tools | Explicit fallback in this skill | Do not keep retrying missing `gala_launchpad_*` tools |

## Missing MCP Server Workflow

1. Detect that GalaChain MCP tools are unavailable.
2. Stop calling additional `gala_launchpad_*` tools.
3. Explain that the `gala-launchpad` MCP server is not configured for Codex.
4. Point the user to `references/codex-setup.md`.
5. Continue teaching from the local references if the user still wants conceptual help.

## Teaching Workflow

1. Identify the user goal.
2. Map it to a topic from `topics.md`.
3. If the MCP server is available, use `gala_launchpad_explain_sdk_usage` for the topic.
4. Summarize the concept, the practical use case, and the likely next topic.
5. Offer execution only after clarifying environment and risk.

## Execution Workflow

1. Confirm whether the task is read-only or state-changing.
2. Confirm the target environment.
3. Use GalaChain discovery tools first when the operation is risky or ambiguous.
4. Execute the relevant `gala_launchpad_*` tool only after the inputs are clear.
5. Explain the result and the next safe step.

## Recommended Replies

- For missing setup: explain the missing server, show the Codex config path, and tell the user to restart Codex.
- For learning requests: identify the matching topic explicitly so the user can drill deeper.
- For execution requests: name the environment and call out whether the action is read-only or state-changing.
