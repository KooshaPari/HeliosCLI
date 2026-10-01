# Mature harness ontology — draft for falsification

Status: NON-CODE CONTRACT DRAFT. Do not generate implementation from this as if frozen.

## Identity/lifetime objects

### AgentDefinition
Reusable behavioral definition: instructions, model/provider capability requirements, tools/capabilities, delegation policy, guardrails and defaults. It is not a running worker.

### WorkerAttempt
Ephemeral incarnation with worker_attempt_id, process/sandbox/host/model/tool configuration, start/end reason and lease. Replacement creates a new attempt.

### Session
Provider/model-facing working context and conversation history. A durable effort may use zero, one or many sessions; sessions may be shared only where provider semantics permit.

### DurableEffort
Persistent development/work object: accepted assignment, decomposition, dependencies, plans, decisions, attempts, effect receipts, approvals, evidence and state transitions. Survives workers and clients.

### ProductState
Accepted product truth independent of development machinery: product identities/configuration/releases/deployments/evidence/observed behavior/assessment.

## Execution objects

### Capability
Typed operation exposed to an agent or workflow. Declares input/output schema, side-effect class, authorization requirements, execution substrate, reconciliation support, cost/resource hints and version.

### Effect
Mutation intent + dispatch + outcome/reconciliation record. States include INTENT_RECORDED, DISPATCHED, CONFIRMED_SUCCESS, CONFIRMED_FAILURE, UNCERTAIN, RECONCILED_SUCCESS, RECONCILED_FAILURE, ABANDONED.

### Artifact
Durable output with identity/content/provenance. Not interchangeable with transient messages or UI stream events.

### Workspace
Bounded environment containing files/processes/repos/VM/container/browser/game/application state as applicable. Has ownership, isolation, snapshot and cleanup semantics.

### Checkpoint
Serializable execution/workflow state sufficient for a defined resume boundary. A checkpoint is not proof that external effects committed.

## Coordination objects

### WorkGraph
Logical dependency/control structure among efforts/steps/agents. Does not encode resource placement.

### SchedulerLease
Placement/resource contract: CPU/GPU/RAM/VRAM/storage/network/provider quotas/tool slots/priority/deadline/locality/anti-affinity/tenant and preemption semantics.

### Approval
Authority-bearing human/policy decision tied to exact subject/action/scope/time, not a chat message.

### PolicyDecision
Machine or human authorization outcome with policy/version/input provenance.

## Observation/acceptance objects

### Evidence
Verifier-bound observation of exact product/subject/contract/candidate/config/environment/run/time/raw artifact.

### Trace
Operational causal/temporal observation. Useful evidence source, but not automatically acceptance authority.

### GraderResult
Independent multidimensional acceptance result with grader/version/rubric/evidence refs and non-averagable critical failures.

### EventProjection
Ordered/best-effort client-facing state/event stream reconstructable from authoritative state where required. Loss of a projection must not corrupt durable truth.

## Ports

ProviderPort; ToolRuntimePort; WorkspacePort; DurableExecutionPort; SchedulerPort; PolicyPort; SecretPort; EvidencePort; GraderPort; EventProjectionPort; ArtifactStorePort; SessionStorePort.

Ports are capability contracts, not mandates to build every backend.

## Required client invariance

For the same accepted effort and backend semantics, GUI/TUI/CLI/API/SDK clients must not redefine:
- effect identity/retry safety;
- approval authority;
- durable effort state;
- evidence meaning;
- grader acceptance;
- session ownership;
- artifact identity;
- cancellation/worker replacement semantics.

Clients may vary presentation, interaction density, local shortcuts and projections.

## Falsification workloads

1. Coding agent modifies repository with tools and tests.
2. Research agent browses, cites, writes report, no repository.
3. Email/operations agent waits days for external reply then resumes.
4. Data-analysis agent runs distributed compute with GPU/CPU quotas.
5. Computer-use agent controls a GUI application with irreversible actions.
6. Multi-agent debate/review with no shared conversation session.
7. Long-running media generation with artifacts and checkpoints.
8. Human-in-the-loop workflow with approval revocation/expiry.
9. Non-idempotent remote effect during worker crash.
10. Offline/local single-process ephemeral chat.

Any workload requiring an unexplained identity/lifetime/state object reopens the ontology.
