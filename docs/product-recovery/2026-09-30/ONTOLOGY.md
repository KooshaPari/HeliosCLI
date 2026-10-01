# Mature product ontology — HeliosCLI / Codex-lineage client

Status: DRAFT-COMPLETE-STRUCTURE / semantic population ongoing.

HeliosCLI is not the canonical generic harness itself. It is the Codex-lineage CLI/TUI/headless client and one reference consumer of the shared harness contract.

## Independent projections

### Client experience
- interactive TUI
- direct CLI commands
- headless/exec
- scripting/structured output
- session/thread discovery/resume/fork
- approvals/HITL
- configuration/profiles
- authentication/account
- diagnostics
- update/release
- accessibility
- shell integration

### Harness integration
- agent/thread lifecycle
- turn lifecycle
- model/provider invocation
- tool/capability invocation
- context/memory
- workspace/sandbox
- durable effort
- event projection
- evidence/grader
- policy/approval
- cancellation/recovery

### Coding specialization
- repository discovery
- editing/patches
- shell/process
- tests/build/lint
- git/worktrees
- review
- code search/LSP
- MCP/apps/browser where enabled

### Operations
- install/update/coexistence
- telemetry/observability
- performance/QoS
- security/secrets
- provenance/supply chain
- compatibility/migrations

### Verification
- contract tests
- negative/adversarial controls
- client/harness conformance
- upstream-delta regression
- journey tests
- performance/reliability
- evidence identity

## Authority

Shared harness semantics outrank client-local convenience. HeliosCLI may project or adapt state; it must not create a second incompatible definition of attempt, effort, effect, evidence, approval, or product acceptance.

Current root harness crates are historical implementation/prototypes until mapped to this ontology and compared with Agentora/PhenoShared plus external SOTA.
