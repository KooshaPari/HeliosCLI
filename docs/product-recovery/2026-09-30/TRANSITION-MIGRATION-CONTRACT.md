# Transition and migration contract — HeliosCLI family

## Principle
Migrate by preserving accepted identities/behavior, not old crate topology.

## From frozen HeliosCLI
- root harness interfaces/orchestrator/checkpoint/queue/cache are prototype donors, not canonical compatibility contracts;
- historical sessions/config/artifacts must be inventoried before retirement;
- current `helios` command names may be compatibility aliases if users/scripts depend on them;
- vendored Codex trees are reference history, not migration targets.

## Toward shared harness
1. Freeze mature ontology/schema versions.
2. Implement conformance adapters for current Codex and current jcode.
3. Establish durable-effort/effect/evidence store contract.
4. Map client commands to shared operations.
5. Provide projection/event compatibility.
6. Migrate session/config identities where semantically possible; otherwise explicit unsupported boundary.
7. Run cross-client conformance and installed-artifact tests.
8. Only then retire/sunset old root harness pieces.

## Transition debt ledger
- old stateless/NDJSON assumptions;
- root in-memory checkpoint semantics;
- prompt-only approval policy;
- synthetic orchestrator;
- stale vendored Codex;
- broken/excluded PhenoShared pyo3 bridge;
- command/README mismatch;
- historical 50-prompt intent corpus not yet fully recovered;
- configuration namespace coexistence with Codex/KCode;
- release identity/update migration.

Each debt item requires KEEP_COMPAT, MIGRATE, SUPERSEDE or RETIRE with evidence.
