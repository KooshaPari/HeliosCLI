# Source coverage ledger — HeliosCLI

Program: HARNESS-MATURE-20260929 (corrected active pair 2026-09-30)
Frozen source: `KooshaPari/HeliosCLI@2adc983bbb105546127250e688774338677ff43a`
Status: OPEN. No completion percentage.

| ID | Source family | Initial evidence/classification | Resolution |
|---|---|---|---|
| HC-S01 | User intent / current clarification | Accepted: active Codex-lineage primary; HeliosCLI is behind current Codex but retains historical UX/behavior obligations; active upstream/contribution value matters | Partial; lineage matrix required |
| HC-S02 | Historical bound conversations | repo intent file binds 50 prompts from 2025-08..2026-06; intent statement itself is blank | OPEN: retrieve/read/cluster all useful bound prompts |
| HC-S03 | README/product docs | Claims canonical Codex fork, multi-backend/sandboxing/perf/harness; also documents vendored Codex excluded from root workspace | Supporting evidence, not normative alone |
| HC-S04 | Root Cargo workspace | Current implementation | Active root is a homegrown harness/client workspace; sampled runner is a local subprocess wrapper, queue/cache are basic in-process structures, checkpoint store sampled is in-memory, orchestrator is synthetic. Treat as prototype/scaffold + donor code, not mature shared harness. | Semantically resolved at family level; individual crates still map to dispositions |
| HC-S05 | Vendored codex-rs/codex-cli | Historical/upstream reference trees excluded from active root workspace | Do not infer implementation; compare exact upstream lineage/current Codex |
| HC-S06 | Intent/boundary propagated docs | Placeholders despite active status | Contradictory/incomplete; cannot serve as canonical contract |
| HC-S07 | Harness crates | Current implementation / historical prototype | Sampled orchestrator marks synthetic task success without worker/model/tool execution; interfaces are generic transport types; queue/cache/checkpoint are local primitives. Architecture doc itself says hand-rolled queue should migrate to tokio mpsc. | RESOLVED: no crate earns canonical status by name; classify each USE/ADAPT/REPLACE/RETIRE against mature ontology |
| HC-S08 | CLI/TUI/API surfaces | Current implementation | Active helios binary mounts Run/Checkpoint/Rollback/Status/Enqueue/Record/Ask/Exec/Resume. `exec` currently asks model to describe tool calls and explicitly says future versions will execute them; `resume` reconstructs a session then exits and tells user to start another command. README's modern-Codex-like surface is not mounted root behavior. | RESOLVED major root reachability; exhaustive command handler mapping remains supporting work |
| HC-S09 | Agentora/PhenoShared boundary | Historical architecture + current broken integration | Registry says Agentora was canonical agent/process plane while phenoShared was staging/decompose, not final boundary owner. Root harness_pyo3 is excluded due broken phenoShared path. | RESOLVED assumption: do not make PhenoShared canonical by default; Agentora obligation audit still OPEN |
| HC-S10 | Tests/CI/release | inventory required | OPEN |
| HC-S11 | Security/sandbox/auth/policy | root sandbox + vendored Codex security surfaces must not be conflated | OPEN |
| HC-S12 | Persistence/checkpoint/recovery | Current implementation + historical design | Architecture declares stateless library/NDJSON-era intent; sampled CheckpointStore is in-memory. Resume reconstructs chat session but does not continue execution. Mature durable-effort/effect semantics are absent from sampled root spine. | RESOLVED current-state gap; backend architecture decision remains OPEN |
| HC-S13 | Performance/scaling | historical perf branches + harness_scaling claims | OPEN: benchmark evidence and current Codex/jcode matched comparison |
| HC-S14 | Registry/history/ADRs/issues/PRs | substantial prior rationalization and fork extraction history | OPEN |
| HC-S15 | Current Codex upstream | same-day frozen `openai/codex@60947e234156ac12bdb7fba2477d3965f166bd34`; modern workspace includes agent graph/identity/roles/message board, app-server daemon/client/protocol, plugins/extensions, state/thread stores, rollout tracing, workload identity, realtime/environment/permissions and SDK surfaces absent from the old Helios root model | Partial: architecture delta established; semantic matched-capability comparison open |
| HC-S16 | KCode/jcode comparison | second active primary and potential complementary/converged lineage | OPEN family convergence matrix |
| HC-S17 | HeliosLite/Forgecode | sunset donor/reference only | Preserve evidence; no new primary implementation work |

Resolution means semantic obligations, contradictions, implementation reachability, journey implications and verification consequences are understood—not merely that files were opened.
