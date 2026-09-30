# Source coverage ledger — HeliosCLI

Program: HARNESS-MATURE-20260929 (corrected active pair 2026-09-30)
Frozen source: `KooshaPari/HeliosCLI@2adc983bbb105546127250e688774338677ff43a`
Status: OPEN. No completion percentage.

| ID | Source family | Initial evidence/classification | Resolution |
|---|---|---|---|
| HC-S01 | User intent / current clarification | Accepted: active Codex-lineage primary; HeliosCLI is behind current Codex but retains historical UX/behavior obligations; active upstream/contribution value matters | Partial; lineage matrix required |
| HC-S02 | Historical bound conversations | repo intent file binds 50 prompts from 2025-08..2026-06; intent statement itself is blank | OPEN: retrieve/read/cluster all useful bound prompts |
| HC-S03 | README/product docs | Claims canonical Codex fork, multi-backend/sandboxing/perf/harness; also documents vendored Codex excluded from root workspace | Supporting evidence, not normative alone |
| HC-S04 | Root Cargo workspace | Active harness crates + helios binary/TUI/tools/sandbox/AI; codex-rs/codex-cli excluded; harness_pyo3 excluded due broken phenoShared path | OPEN: map mounted callers and stubs |
| HC-S05 | Vendored codex-rs/codex-cli | Historical/upstream reference trees excluded from active root workspace | Do not infer implementation; compare exact upstream lineage/current Codex |
| HC-S06 | Intent/boundary propagated docs | Placeholders despite active status | Contradictory/incomplete; cannot serve as canonical contract |
| HC-S07 | Harness crates | queue/rollback/runner/schema/spec/teammates/verify/cache/checkpoint/discoverer/elicitation/interfaces/normalizer/orchestrator etc. | OPEN: semantic implementation/reachability audit |
| HC-S08 | CLI/TUI/API surfaces | root helios + helios-tui + tools/AI/sandbox; README claims broader Codex CLI commands | OPEN: distinguish active root binary from vendored/unmounted commands |
| HC-S09 | Agentora/PhenoShared boundary | harness_pyo3 excluded because path dependency broken; shared-harness absorption hypothesis unverified | BLOCKING architecture evidence |
| HC-S10 | Tests/CI/release | inventory required | OPEN |
| HC-S11 | Security/sandbox/auth/policy | root sandbox + vendored Codex security surfaces must not be conflated | OPEN |
| HC-S12 | Persistence/checkpoint/recovery | harness_checkpoint and related crates present | OPEN: actual durability/consumer mapping |
| HC-S13 | Performance/scaling | historical perf branches + harness_scaling claims | OPEN: benchmark evidence and current Codex/jcode matched comparison |
| HC-S14 | Registry/history/ADRs/issues/PRs | substantial prior rationalization and fork extraction history | OPEN |
| HC-S15 | Current Codex upstream | active strategic upstream; user states materially evolved since HeliosCLI fork | OPEN SOTA/upstream delta |
| HC-S16 | KCode/jcode comparison | second active primary and potential complementary/converged lineage | OPEN family convergence matrix |
| HC-S17 | HeliosLite/Forgecode | sunset donor/reference only | Preserve evidence; no new primary implementation work |

Resolution means semantic obligations, contradictions, implementation reachability, journey implications and verification consequences are understood—not merely that files were opened.
