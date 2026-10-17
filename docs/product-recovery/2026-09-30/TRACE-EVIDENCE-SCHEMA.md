# Trace and evidence schema — non-code contract

## Authority classes
ACCEPTED_INTENT; AUTHORIZED_DECISION; DETERMINISTIC_SOURCE_FACT; VERIFIED_OBSERVATION; IMPORTED_ASSERTION; AGENT_INFERENCE; HISTORICAL_SUPERSEDED.

Confidence never upgrades authority.

## Core trace nodes
Intent, Capability, Requirement, QualityConstraint, Journey, ArchitectureDecision, InterfaceContract, WorkPackage, SourceSurface, ImplementationSubject, TestOracle, EvaluationRun, Evidence, GraderResult, Release, RuntimeObservation, Finding.

## Required relations
Intent -> motivates -> Capability
Capability -> decomposes_to -> Requirement
Requirement -> participates_in -> Journey
Requirement -> constrained_by -> QualityConstraint
Requirement -> realized_by -> ImplementationSubject
Requirement -> verified_by -> TestOracle
TestOracle -> executed_as -> EvaluationRun
EvaluationRun -> produces -> Evidence
Evidence -> evaluated_by -> GraderResult
Release -> contains -> ImplementationSubject
RuntimeObservation -> observes -> Release/subject
Finding -> blocks/qualifies/supersedes -> any subject

Every edge stores authority, provenance, validation state and version/time.

## Evidence identity minimum
evidence_id
product_id
subject_id
contract_baseline
criterion_id
candidate_id/release digest
configuration digest
environment/hardware
verifier + version
evaluation_run_id
timestamp
raw artifact/content digest
collector status
provenance chain

## Invalid green rules
Missing evidence != pass.
Skipped != pass.
Collector failure != pass.
Wrong candidate != pass.
Stale evidence != current pass.
Historical work completion != product acceptance.
Worker-authored grader modification cannot self-qualify without independent policy approval.
Critical security/authority/effect failures cannot be averaged away.

## Progress dimensions
source coverage; semantic specification; implementation realization; mounted reachability; traceability; evidence freshness; journey closure; regression; performance; reliability; security; accessibility; usability; transition debt; uncertainty.

Do not collapse these into one percentage unless a presentation explicitly shows the vector and denominator semantics.
