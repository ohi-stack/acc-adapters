# acc-adapters

ACC Adapters is the provider and external-system integration boundary for the canonical ACC™ control plane at `https://acc.onegodian.com`.

## ACC V2 role

Adapters translate ACC Work Orders into provider-specific requests only after applicable identity, policy, approval, and execution gates are satisfied.

Canonical provider-independent flow:

```text
Project
→ Responsibility
→ Work Order
→ ACC authorization
→ Provider adapter
→ Execution target
→ Verification
→ Audit
```

Adapters must never redefine ACC authority or silently fall back to an unknown provider.

## Provider contract

Current canonical provider identifiers include:

- `acc-runner`
- `omos`
- `openai-agents`
- `openai-dot`
- `openai-codex`
- `chatgpt-work`
- `external-mcp`
- `human`

A provider identifier does not prove an operational connection. Adapter capability, authentication, runtime availability, and deployment state must be verified separately.

`openai-dot` is reserved for future compatibility and must remain non-executable until a supported developer integration is implemented, verified, repeatable, and deployed.

## Existing integration classes

This repository may contain adapters for WordPress, QR-V, wallets, notifications, APIs, model providers, MCP-compatible services, and other connected systems.

Privileged writes, deployments, financial actions, identity changes, and other governed operations remain subject to ACC human-approval and audit requirements.

**Synchronization target:** ACC `2.0.0-alpha.1` delegation foundation. Production ACC remains on the separately verified production baseline until V2 is deployed.
