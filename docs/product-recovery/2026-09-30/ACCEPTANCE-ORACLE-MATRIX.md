# Acceptance and oracle design matrix — HeliosCLI

Status: design-complete target, executable test generation may follow separately.

| Subject | Positive oracle | Negative/adversarial controls | Evidence identity |
|---|---|---|---|
| Client/runtime identity | client connects to intended runtime and reports version/git/binary/protocol | stale daemon; wrong socket; copied version; upgraded client + old daemon; digest mismatch | client+runtime candidate/config/env/verifier/run |
| Durable effort | attempt replacement resumes same effort without losing accepted state | worker killed at every state boundary; stale checkpoint; corrupt store; concurrent replacement | effort/attempt/checkpoint/store/version |
| External effect | confirmed/reconciled effect not duplicated | kill before dispatch; after commit/before ack; conflicting postcondition; non-queryable target; wrong effect ID | effect/tool/target/attempt/downstream receipt |
| Session | supported resume preserves model-visible context | provider session missing/expired; compaction drops policy; incompatible provider switch | session/provider/model/context-policy |
| Approval | exact pending action accepted by authorized actor | stale/expired/wrong effort/wrong action/replayed approval; action mutates after approval | approval/policy/actor/action digest/time |
| Tool authorization | allowed tool executes within scope | unlisted tool; path escape; network escape; secret exfiltration; tool schema spoof | capability/version/policy/workspace |
| Workspace | isolation and ownership preserved | sibling worktree mutation; symlink escape; cleanup race; stale snapshot | workspace/lease/host/sandbox version |
| Cancellation | cancellation reaches child/tool/model according to policy | child outlives parent; late tool result mutates state; cancel/retry race | effort/attempt/child/tool timestamps |
| Scheduler | requirements respected under pressure | oversubscription; starvation; priority inversion; lost lease; node death; partial placement | lease/resource snapshot/scheduler version |
| Event projection | client can reconstruct current state after reconnect | dropped/duplicated/reordered events; reconnect gap; stale projection | stream/projection version + authoritative state ref |
| Artifact | durable output addressable with provenance | message-only output; mutated artifact; wrong candidate; missing content | artifact digest/producer/effort/candidate |
| Grader | exact contract/evidence produces multidimensional result | missing evidence; skipped collector; grader changed by worker; critical failure averaged away | grader/rubric/version/evidence set |
| Release/update | install/update/rollback preserves identity/state contract | wrong channel; partial update; config migration failure; old daemon; rollback incompatible store | release artifact/digest/channel/migration/run |
| Provider capability | supported features negotiated | unsupported tool/stream/structured output silently emulated; limit exceeded | provider/model/API/version/capability snapshot |
| MCP/A2A adapters | canonical objects round-trip where mapping exists | lossy identity; Message treated as Artifact; task state dropped; authorization mismatch | adapter/protocol version/conformance fixture |
| Multi-client | CLI/GUI/API observe same durable effort | client-local hidden truth; conflicting commands; stale client mutation | effort/client/protocol/command sequence |
| Generic workload | non-coding journey closes without coding assumptions | forced fake repository; missing artifact/wait semantics | journey fixture + all above applicable identities |

## Mutation-style questions

For each guard ask: if removed, can a worker manufacture green, repeat an irreversible effect, reuse stale authority, confuse candidates, or hide missing evidence? If yes, retain a negative control.

## Test layers

1. Pure contract/property tests.
2. Adapter conformance suites.
3. Fault-injection integration tests.
4. Installed-artifact E2E.
5. Cross-client conformance.
6. Scale/QoS stress.
7. Security/adversarial.
8. Held-out grader cases.
9. Comparative pilot vs alternatives after build.

No layer may convert skipped/unavailable into pass.
