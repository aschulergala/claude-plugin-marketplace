---
name: omni-tool:ask
description: Ask a natural-language GalaChain question or request an SDK topic
arguments:
  - name: query
    description: "Your question or topic name, such as 'how do I buy tokens?' or 'buy-tokens'"
    required: true
  - name: examples
    description: "Show code examples? (yes/no, default: yes)"
    required: false
  - name: personality
    description: "Personality mode: tutor, expert, pragmatist, or socratic"
    required: false
---

# GalaChain Ask

Ask a GalaChain question in your own words or provide a topic name. Map the request to a topic and call `gala_launchpad_explain_sdk_usage` for current explanation, code, tools, and related topics.

The server's `gala_launchpad_explain_sdk_usage` `topic` enum is the live source of truth for topic names. Use its current values, including names added by a newer server even when the local index lags. The local index describes 69 topics.

## Examples

```text
/omni-tool:ask how do I buy tokens?
/omni-tool:ask queued-swap-recovery
/omni-tool:ask token-creation --examples=no
/omni-tool:ask dex-trading --personality=expert
```

For natural-language questions, infer intent and choose the closest live enum member. If several topics fit, present the best matches or ask a short follow-up. Do not invent a topic: consult the live enum. If the MCP tool is missing or unknown, stop MCP attempts, answer from available knowledge, and direct the user to `/omni-tool:setup`.

## v7 SDK guidance

Prefer examples returned by the live tool. Launchpad operations are flat SDK methods such as `sdk.buy()`, `sdk.sell()`, `sdk.launchToken()`, and `sdk.transferToken()`. DEX operations are grouped under `sdk.dex.*`. DEX swaps are queued: explain submission and `confirm()` behavior, and use `confirmSwap(uniqueKey)` to recover an existing swap after uncertainty. Do not suggest resubmitting after a confirmation timeout.
