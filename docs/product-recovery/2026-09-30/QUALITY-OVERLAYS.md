# Quality overlays — canonical harness and HeliosCLI

Quality properties apply to subjects/journeys; they are not cloned into every functional requirement.

## Performance
- interactive event/render latency budgets by client;
- model/tool dispatch overhead budget separated from provider latency;
- bounded queue/backpressure behavior;
- startup and idle footprint;
- concurrency scaling and saturation curves;
- no performance claim without workload/config/hardware identity.

## Reliability
- worker/client/server restart recovery;
- durable-store corruption/partial failure;
- provider/tool/network transient handling;
- no duplicate irreversible effect after uncertainty;
- cancellation convergence;
- upgrade/rollback recovery.

## Security
- least privilege;
- sandbox/workspace isolation;
- path/network/process boundaries;
- secret custody;
- approval integrity;
- protocol auth/replay;
- untrusted model/repo/tool content;
- supply-chain/release provenance.

## Accessibility/usability
- keyboard-only TUI;
- screen-reader/semantic terminal output where feasible;
- no color-only critical state;
- structured noninteractive alternative;
- approval/risk state comprehensible;
- GUI clients may enrich but not hide required state.

## Interoperability
- versioned schemas;
- capability negotiation;
- unknown-field/version behavior;
- MCP/A2A adapter conformance;
- client/runtime skew handling;
- migration/deprecation windows.

## Observability
- trace/span correlation across effort/attempt/session/tool/effect;
- metrics for queues/resources/provider/tool failures;
- privacy/redaction policy;
- replay links to immutable evidence;
- collector failure visible, never green.

## Maintainability
- upstream patch stack size and semantic delta;
- adapter conformance tests;
- generated schema/source provenance;
- dependency/license health;
- no duplicated product-neutral harness logic across clients.

## Portability
- macOS/Linux/Windows native support target;
- architecture/CPU support;
- local/offline/degraded modes;
- no mandatory WSL/PowerShell semantic dependency for product-neutral core unless explicitly accepted.

## Scalability/QoS
- explicit resource accounting;
- priority/fairness/deadline;
- tenant/workload isolation;
- locality/placement;
- preemption/recovery;
- evidence of slope, not one-point throughput.

## Quality evidence binding
Every measured result binds subject, candidate, config, environment/hardware, workload, verifier/version, timestamp and raw artifact. Historical or mismatched evidence does not satisfy current quality gates.
