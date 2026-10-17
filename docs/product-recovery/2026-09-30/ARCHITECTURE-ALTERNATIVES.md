# Architecture alternatives gate — HeliosCLI family

## A — Modern Codex core/App Server + shared harness extensions
Current Codex already powers CLI/TUI/IDE/web/app from one harness through App Server and also exposes exec/SDK/MCP embedding paths. Default challenger for Codex lineage.

Disposition: STRONG CHALLENGER. Prefer contribution/adapters before hard fork.

## B — Modern jcode + shared harness extensions
KCode/jcode lineage may provide preferable runtime/provider/session behavior. Must satisfy recovered Codex/HeliosCLI UX/client obligations.

Disposition: STRONG CHALLENGER / second active primary.

## C — Segmented Codex-lineage + jcode-lineage clients over one shared harness contract
Justified only if stable role boundaries survive: e.g. different interaction/runtime strengths that cannot be expressed as modes/adapters without material complexity/performance loss.

Disposition: UNVERIFIED.

## D — One converged/superset client/runtime
Merge strongest client/runtime semantics into one canonical CLI while retaining upstream contribution paths.

Disposition: UNVERIFIED; high maintenance/integration risk if implemented as a permanent mega-fork.

## E — HeliosLite/Forgecode lightweight client
Sunset donor. Survives only if measured lightweight/headless/ephemeral advantages cannot be obtained as a mode/client over A/B/shared harness.

Disposition: PRESUMED SUNSET / falsifiable exception.

## F — Root HeliosCLI homegrown harness as canonical kernel
Current root orchestrator/interfaces are prototype-level and old persistence assumptions conflict with mature intent.

Disposition: REJECT AS CURRENT CANONICAL IMPLEMENTATION; retain archaeology/requirements and reusable proven pieces.

## Durable execution backend
Treat durable effort as a port. Evaluate Temporal, Microsoft Durable Task and other self-hosted systems before custom implementation. Custom engine requires measured need.

## Architecture invariant
Client presentation != agent kernel != durable orchestration != scheduler/control plane != product acceptance/evidence authority. Boundaries may collapse in-process for latency, but contracts remain explicit.
