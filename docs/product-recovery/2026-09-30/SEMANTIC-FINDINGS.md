# Semantic findings — HeliosCLI

Frozen source: `2adc983bbb105546127250e688774338677ff43a`

## HC-F001 — Root harness and vendored Codex are separate products at the build boundary

`ARCHITECTURE.md` explicitly says the Codex fork was severed 2026-06-30 and `codex-rs/` / `codex-cli/` are excluded, unbuilt reference material. The active root workspace is a homegrown harness plus `helios` client crates. Therefore README examples inherited from Codex are not implementation evidence unless the active root binary mounts equivalent behavior.

Consequence: current Codex must be researched as an external active upstream/alternative, not treated as the executable implementation hiding inside this repo.

## HC-F002 — Current root orchestrator is prototype semantics, not a production agent harness

`harness_orchestrator::RootManager::execute` selects an idle in-memory Agent, marks a Task running, appends a formatted “executed by agent” string, marks the task success, and releases the agent. It does not invoke a model/worker/tool runtime, persist durable effort, reconcile effects, recover workers, grade outcomes, enforce capability constraints, or execute a real task body.

Its `decompose` implementation creates only a main task plus a verify task. This is useful scaffolding/history, not evidence that multi-agent orchestration is mature.

## HC-F003 — harness_interfaces is transport-shaped, not the canonical agent contract

The current leaf interface crate defines generic Request/Response/Event plus synchronous Handler and Publisher/Subscriber traits. It lacks first-class agent attempt, durable effort, tool/effect, checkpoint, evidence, cancellation, approval, model capability, event-stream projection, grader, workspace and lifecycle contracts.

Do not evolve this API by accreting fields until the independent generic-harness research establishes the ontology. It may be superseded by Agentora/PhenoShared contracts.

## HC-F004 — “stateless library” architecture conflicts with mature durable harness intent

`ARCHITECTURE.md` intentionally describes the library layer as stateless between runs, with newline-delimited checkpoint/rollback files and no database. Mature accepted intent now requires durable effort surviving worker replacement, evidence identity, replay/trace and at-scale generic harness use. The old stateless rule is historical accepted design for that phase, not automatically current intent.

Need alternatives research before selecting event log / DB / workflow engine / hybrid persistence.

## HC-F005 — root helios binary is a narrow mounted client, not modern Codex parity

The active root `crates/helios/src/main.rs` mounts Run, Checkpoint, Rollback, Status, Enqueue, Record, Ask, Exec and Resume. This proves a usable command surface exists, but it is not evidence for the much broader modern Codex command/runtime behavior described elsewhere in the README. Each command must be traced to implementation and journey closure.

## HC-F006 — historical prompt corpus is referenced but not co-located

The propagated intent document binds 50 prompts, but the referenced `docs/curated-prompts/...` files are not present at the frozen HeliosCLI paths sampled. Recover them from PhenoRegistry/history/conversation sources rather than treating the intent file as self-contained evidence.


## HC-F007 — Several headline harness crates are not mounted by the active helios binary

`crates/helios/Cargo.toml` directly depends on harness_queue, harness_runner, harness_rollback, harness_checkpoint, harness_spec, harness_verify, helios_config, recorder, AI/tools/sandbox. It does **not** depend on harness_orchestrator, harness_scaling or harness_interfaces.

Therefore the repository's architecture diagram describes workspace inventory, not a single integrated runtime. Orchestrator/scaling/interfaces receive no mounted-product credit until an actual caller/consumer is traced. This is particularly important because the current orchestrator is prototype semantics.

## HC-F008 — Active upstream velocity is an architectural requirement

Contemporary baselines are now frozen outside this repo: Codex `60947e2341...` (2026-09-30) and jcode `5f1c091cf7...` (2026-10-01). Both moved recently. HeliosCLI's own architecture says its Codex hard fork was severed 2026-06-30.

A mature HeliosCLI design must therefore treat upstream synchronization/contribution/extension strategy as a first-class lifecycle requirement. A deep fork is not neutral; it continuously converts upstream product/security/runtime evolution into integration debt.
