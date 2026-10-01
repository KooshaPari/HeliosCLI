# Mature product contract — HeliosCLI

HeliosCLI is the Codex-lineage coding-agent client/reference runtime over the canonical shared harness semantics. It may ultimately converge with KCode; this contract describes obligations that must survive even if the repository identity does not.

## Functional obligation families

### HC-FAM-CLIENT Client lifecycle
- install/start/configure/diagnose/update/rollback;
- interactive and noninteractive invocation;
- structured machine output/event subscription;
- session/thread discover/resume/fork where supported;
- explicit errors/degraded capability state.

### HC-FAM-THREAD Agent/thread interaction
- create/select/resume thread;
- submit turns/messages/assignments;
- receive ordered typed lifecycle/model/tool/approval/evidence events;
- cancel/pause/resume with defined semantics;
- reconnect without semantic loss.

### HC-FAM-TOOLS Coding capability
- repository/file discovery and reading;
- edits/patches with conflict/precondition behavior;
- process/shell/test/build/lint execution;
- git/worktree/review workflows;
- external capabilities through adopted protocols such as MCP/apps;
- tool identity, authorization and effect semantics bind to shared contract.

### HC-FAM-PROVIDER Model/provider
- provider/model configuration and authentication;
- capability negotiation;
- streaming and structured outputs;
- model/tool/context limits represented explicitly;
- unsupported features fail explicitly or use declared degradation.

### HC-FAM-HITL Human intervention
- approval/question/conflict requests are typed events;
- request binds actor, effort, operation and expiry/state;
- response may originate from any compatible client;
- stale/wrong-effort/wrong-actor responses rejected.

### HC-FAM-DURABILITY Durable work
- client death does not define effort death;
- reconnect/replacement restores shared durable state;
- uncertain external effects reconcile before retry;
- completed durable steps are not silently repeated;
- backend is replaceable behind conformance contract.

### HC-FAM-PROJECTION Multi-client projection
- GUI/TUI/CLI/API/SDK can consume same underlying effort/thread/event semantics;
- client presentation state is separable;
- no transcript scraping required as canonical GUI integration;
- protocol/version/capability negotiation supports evolution.

### HC-FAM-PARALLEL Parallel work
- isolated attempts/workspaces;
- scheduling/priority/budget/resource policy visible;
- results/evidence independently attributable;
- fan-out/fan-in and selection do not merge acceptance authority with worker output.

### HC-FAM-EVIDENCE Verification
- tests/checks/graders produce identity-bound evidence;
- missing/skipped/stale/wrong-candidate evidence not green;
- critical acceptance dimensions fail closed;
- implementation cannot mutate acceptance policy and self-approve.

### HC-FAM-SEC Security
- sandbox/permissions/secret access/approvals explicit;
- untrusted repository/tool/model content cannot silently elevate authority;
- audit/provenance retained for sensitive actions;
- network/external system access follows declared policy.

### HC-FAM-OPERATIONS Operations
- exact runtime/binary/protocol identity observable where daemonized;
- coexistence/migration with upstream/current clients is defined;
- release provenance/update rollback;
- observability and performance budgets per journey;
- supported OS/arch/backend matrix explicit.

## Explicit non-goals
- owning a second generic agent semantic model separate from shared harness;
- preserving old root harness crates merely because they exist;
- matching every Codex feature if it is irrelevant to accepted journeys;
- hard-forking current Codex when extension/contribution satisfies the contract;
- embedding HeliosLab by wrapping/scraping terminal output as the primary interface.

## Architecture-dependent obligations
Backend selection (Codex core/App Server, jcode, shared runtime, durable engine) remains open where experiments/SOTA are required. The behavior contract above survives backend choice.