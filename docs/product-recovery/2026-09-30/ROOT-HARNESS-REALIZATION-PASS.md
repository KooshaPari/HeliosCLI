# Root harness realization — pass 1

Frozen source: `2adc983bbb105546127250e688774338677ff43a`

This pass separates useful implementation primitives from names/architecture claims.

| Surface | Observed realization | Current classification | Mature disposition hypothesis |
|---|---|---|---|
| harness_runner | Real Tokio subprocess runner with timeout/env/working-dir/stdin/output; shell mode escapes args | SUBSTANTIVE PRIMITIVE | Compare/reuse behind generic execution-environment port |
| harness_queue | Mutex/VecDeque bounded channel + rudimentary local/global WorkQueue | SUBSTANTIVE BUT NAIVE | Research scheduler/backpressure systems; likely replace/adapt rather than canonical fleet scheduler |
| harness_orchestrator | In-memory Agent/Task structs; decompose creates main+verify; execute marks tasks success without worker/model/tool invocation | SCAFFOLD / SIMULATION | Do not extend as canonical orchestrator before Freyr/SOTA decomposition |
| harness_interfaces | Generic HTTP-like Request/Response/Event Handler/Publisher/Subscriber | SUBSTANTIVE SMALL LIBRARY, WRONG ABSTRACTION LEVEL for mature agent contract | Likely supersede with shared harness contracts |
| harness_checkpoint | Real git/checkpoint modules present; deeper semantics pending | SUBSTANTIVE CANDIDATE | Salvage if semantics survive durable-effort research |
| helios-tools | Real filesystem read/write/edit primitive with ambiguity guard | SUBSTANTIVE PRIMITIVE | Tool adapter candidate; needs sandbox/effect/evidence integration |
| helios-tui | Source explicitly calls itself minimal ratatui scaffold; chat/status/input only | SCAFFOLD | Do not preserve as UX baseline; compare modern Codex/jcode |
| harness_pyo3 | In-memory Python cache + fast_hash only; root Cargo excludes crate | UNMOUNTED AUXILIARY / MISLEADING NAME | Not evidence of Agentora/PhenoShared integration |
| root helios binary | Real narrow command router: run/checkpoint/rollback/status/enqueue/record/ask/exec/resume | MOUNTED CLIENT | Trace each command; do not infer modern Codex parity |
| vendored codex-rs/codex-cli | Explicitly excluded/unbuilt | HISTORICAL/UPSTREAM REFERENCE | Replace baseline with current Codex snapshot |

## Finding

The root workspace should not be “completed” crate-by-crate. Its strongest pieces are donor primitives. Its existing orchestrator/interfaces/TUI do not establish the mature generic harness ontology.

The next architecture pass should map each primitive into the independently researched shared-harness decomposition and either USE, ADAPT, REPLACE, MOVE TO PHENOSHARED, or RETIRE it.
