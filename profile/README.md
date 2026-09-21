# Keystone Applied Intelligence

**Applied AI engineering for operational workflows, knowledge systems, evaluation, and governed execution.**

Keystone Applied Intelligence is an independent engineering and R&D practice focused on understanding where AI belongs in real operational workflows, building concrete mechanisms when justified, and evaluating their behavior and limits.

The work spans two related questions:

1. **What should change in the operation?**  
   Operational evidence, workflow understanding, baseline measurement, diagnosis, intervention selection, implementation, and measurable outcomes.

2. **How should AI behave when it becomes part of that intervention?**  
   Retrieval, conversational workflows, evaluation, observability, authorization boundaries, explicit task state, and governed execution.

Keystone does not assume that an operational problem requires an AI solution.

The intended sequence is:

```text
operational problem
        ->
evidence
        ->
baseline
        ->
workflow understanding
        ->
diagnosis
        ->
intervention selection
        ->
implementation
        ->
evaluation
        ->
workflow outcome
        ->
business outcome
```

An intervention may be process change, integration, deterministic software, automation, analytics, retrieval, Applied AI, or no intervention until stronger evidence exists.

Keystone builds concrete mechanisms, evaluates them, and preserves both failures and passing evidence rather than presenting only polished results.

The public repositories are related engineering instruments. They should not be interpreted as one fully composed or universally validated production runtime.

A mechanism demonstrated in one workload is not automatically attributed to another.

---

## Applied operational work

### Fire-department knowledge workflow

One applied Keystone deployment supports knowledge access inside a volunteer fire department.

The operational problem was straightforward: procedures and departmental documentation existed, but finding the relevant information could require unnecessary document searching during activities such as training, truck work, and maintenance.

The work proceeded from problem discovery through internal deployment:

```text
knowledge-access problem
        ->
user and document requirements
        ->
retrieval design
        ->
role and access constraints
        ->
implementation
        ->
evaluation
        ->
on-premises deployment
        ->
operational use and feedback
```

The resulting workflow uses role-aware retrieval to help firefighters locate relevant procedures and operational documentation.

Because some source material relates to operational and medical procedures, the system applies evidence thresholds and can withhold an answer when retrieved evidence is insufficient rather than presenting low-confidence output as authoritative.

Firefighters have used the system during internal departmental activities.

### Scope and boundaries

This is a bounded internal operational deployment.

It does not establish:

- clinical validation
- independent safety validation
- production healthcare certification
- enterprise high availability
- generalized effectiveness across fire departments
- suitability outside the department and use case in which it is deployed

The deployment demonstrates that a concrete organizational knowledge problem can be carried from discovery through implementation and real-user use.

It is not presented as universal evidence for RAG, AI safety, healthcare use, or organizational transformation.

---

## Related applied work: Support Operations Intelligence

[Support Operations Intelligence](https://github.com/arnaldosepulveda/support-operations-intelligence) is a separate public portfolio and research project maintained by Arnaldo Sepulveda.

It examines the layer before AI implementation:

```text
operational evidence
        ->
baseline
        ->
competing explanations
        ->
workflow understanding
        ->
diagnosis
        ->
intervention selection
        ->
implementation
        ->
evaluation
```

The project asks whether an intervention is warranted before selecting an AI mechanism.

### Current Calgary 311 work

Current empirical work uses a 7.47-million-record Calgary 311 artifact.

The work is currently in evidence-establishment and source-characterization stages.

Completed work includes:

- reproducible ingestion
- structural checks
- identifier checks
- source-native descriptive baselines
- sentinel and missingness analysis
- controlled human-review procedures
- retained engineering artifacts

It has not yet established:

- an end-to-end operational workflow model
- a diagnosed Calgary service-performance problem
- intervention prioritization
- intervention selection
- an AI solution
- before-and-after improvement
- business impact
- a production deployment

Support Operations Intelligence is maintained separately from Keystone's reference implementations and should not be interpreted as part of a composed Keystone production platform.

---

## Applied AI systems

Current Keystone work spans:

- retrieval and RAG
- conversational workflows
- authorization-aware retrieval
- evaluation and regression tooling
- observability
- local model execution
- explicit task state
- bounded runtime controls

Mechanisms are kept attributable to the workload where they are actually implemented.

---

## Keystone Gov

[Keystone Gov](https://github.com/getkeystone/keystone-gov) is a FastAPI RAG reference implementation.

Its query path combines:

- PostgreSQL full-text search
- pgvector semantic retrieval
- query-time ACL predicates
- deterministic procedural reranking
- evidence thresholds
- local generation
- HHEM as an additional factual-consistency signal
- per-record HMAC integrity checks with documented coverage limits

These mechanisms apply to the Gov workload.

They do not establish production enterprise identity integration, high availability, universal retrieval correctness, or correctness of other Keystone workloads.

---

## Keystone Engage

[Keystone Engage](https://github.com/getkeystone/keystone-engage) is a conversational and workflow AI reference implementation.

The default served application uses one `EngageOrchestrator` with mechanisms including:

- retrieval authorization
- escalation
- intent classification
- RAG dispatch
- explicit task state
- audit records
- served-path tracing

A separate experimental application path registers five specialist agent identities across four coordination phases.

Optional NATS JetStream integration belongs to that experimental path.

This is not evidence of:

- distributed production execution
- durable agent leases
- fencing
- compare-and-swap correctness
- distributed correctness
- high availability

The default served application should not be described as a production multi-agent runtime.

---

## Keystone Counsel

[Keystone Counsel](https://github.com/getkeystone/keystone-counsel) implements authorization-first retrieval.

Role decisions run before retrieval.

Classification and client predicates restrict candidate rows before model context construction.

The response path includes confidence gating and citations.

Regression tests cover a previously identified cross-client retrieval-isolation defect.

The current public corpus is global content.

The implementation does not establish production enterprise identity integration or a production multi-client deployment.

---

## Keystone Verify

[Keystone Verify](https://github.com/getkeystone/keystone-verify) is endpoint-agnostic evaluation tooling.

Profiles describe compatible HTTP endpoints.

Declarative cases define expected assertions.

A deterministic pure-function judge evaluates mapped response fields.

The runner records latency and writes structured result and run metadata.

The output is inspectable JSON evidence.

It is not cryptographically sealed and does not establish the substantive correctness of the evaluated system.

---

## Keystone Ledger

[Keystone Ledger](https://github.com/getkeystone/keystone-ledger) retains internal evaluation artifacts, lineage, negative results, remediations, and evidence limitations.

PASS and FAIL verdicts apply only to the named:

- cases
- configurations
- commits
- datasets
- runs

They are not independent external validation.

---

## Evaluation

Evaluation is part of the engineering loop rather than a final demonstration step.

A retained `keystone-core/agent-v1` internal evaluation records:

- 186 cases across 12 categories
- 558 executions across three runs
- adversarial authorization and bypass testing
- 153 strict-pass cases
- 33 characterization cases
- 0 strict failures at the evaluated commit

Its failing predecessor is retained alongside the passing run.

The evaluation surfaced implementation defects that were subsequently remediated and regression-tested.

Other workloads have separate suites and evidence boundaries.

These results should not be collapsed into one universal Keystone score.

> An evaluation system should be able to expose implementation failures, not only confirm expected behavior.

Internal evaluation is not independent validation.

A passing run does not establish universal correctness, production readiness, safety, or portability.

---

## Observability and operational engineering

The default Engage application calls its OpenTelemetry setup on the served path.

Current implementation evidence supports:

- manual GenAI spans with model attributes
- prompt and completion token attributes
- latency attributes
- automatic FastAPI HTTP tracing
- OTLP/gRPC trace export
- manually verified trace delivery to a self-hosted Grafana Tempo backend

This does not establish OpenTelemetry Metrics API or `MeterProvider` support.

Prometheus, Grafana dashboard, and Alertmanager configuration elsewhere should not be interpreted as demonstrated runtime observability or enforcement unless tied to an explicitly evaluated workload.

Operational evidence is kept distinct from stronger conclusions.

Traces can record execution behavior.

They do not establish that an action was authorized, justified, correct, safe, or effective.

---

## Engineering evidence and workload boundaries

| Workload | Current evidence |
|---|---|
| Gov | PostgreSQL FTS + pgvector hybrid retrieval, query-time ACLs, procedural reranking, bounded HHEM signal, per-record HMAC checks |
| Engage | Single-orchestrator served path, experimental specialist coordination, task lifecycle mechanisms, hash-chained audit records, served-path tracing |
| Counsel | Role, classification, and client retrieval restrictions; confidence gating; cross-client regression coverage |
| Verify | Deterministic assertion-based HTTP evaluation and structured run artifacts |
| Ledger | Retained internal evaluation lineage, failures, remediations, and limitations |
| Runtime Validity | Controlled process-local authority-change and revalidation experiment |

Local inference is available in documented Gov, Engage, and Counsel paths through Ollama.

Hash-chain formats and verification scope differ by workload.

Integrity evidence does not establish semantic correctness, valid authorization, or justified action.

---

## Governed Execution

**Governed Execution** is Keystone's research program examining runtime governance for consequential AI actions.

It is separate from the applied workload identity above.

It is not an existing composed production runtime.

> **Orchestration determines how work proceeds. Governance determines whether the intended consequence remains justified to proceed.**

The research architecture separates three planes and a distinct action boundary.

### Control plane

Authority, policy, admissibility, placement, budget, and release.

### Execution plane

Models, retrieval, tools, delegation, and workflows.

### Evidence plane

Decisions, authorizations, actions, evaluations, failures, and outcomes.

### Action boundary

A separate boundary determines whether output may create external consequence.

---

## Runtime substrate hypotheses

Six candidate dimensions are currently under study:

- Identity
- Task state
- Tempo
- Cost
- Currency
- Fidelity

These dimensions are research hypotheses.

They are not a complete ontology or a claim of complete AI governance coverage.

### Currency

Currency asks:

> **Does the original justification still legitimately authorize the intended consequence at the point of execution?**

Candidate classes of governance-material change currently include:

- Authority
- Governance / policy
- Evidence
- Target / environment
- Interface / tool
- Execution state

These change classes are also research hypotheses rather than validated exhaustive coverage.

---

## Track A: Runtime Validity

[Runtime Validity](https://github.com/getkeystone/runtime-validity) is the canonical repository for Track A.

Its research question is:

> Given a prior decision justification composed of heterogeneous governance obligations, which controlled runtime interventions invalidate which obligations, and under what conditions does obligation-scoped revalidation preserve the same policy-expected disposition as full commit-boundary reevaluation with lower revalidation work?

Research priorities are:

1. invalidation mapping
2. disposition preservation
3. revalidation work and latency

These are research priorities, not claims that the current implementation has completed them.

### Current implementation boundary

The current reference implementation supports only:

- a controlled process-local authority change
- retention of a process-local transition artifact
- full revalidation that can alter the implemented result from `MATCH / PROCEED` to `MISMATCH / HOLD`

`HOLD` is an implementation design choice.

It is not a universal research conclusion.

With `revalidation_mode="none"`, authority is `NOT_EVALUATED`.

Proceeding under that mode does not establish that the intended consequence remains justified.

### Current evidence does not establish

- authentic external revocation
- independent witness evidence
- production authentication or authorization
- durable persistence guarantees
- cryptographic decision-to-transition binding
- external consequence enforcement
- distributed correctness
- universal validity of the Governed Execution architecture

The name **Governed Execution Runtime** is reserved for a future composed runtime when actual components exist to integrate.

The current public repositories do not demonstrate that composition.

---

## Implementation model

Selected engineering implementations, documentation, evaluation methods, and retained artifacts are public.

Some operational and deployment components remain private.

Public research reference implementations are intentionally separable from applied workloads.

Composition requires its own engineering and evaluation.

Passing components do not establish that a composed system is correct, portable, safe, or production-suitable.

---

## What Keystone does not claim

Keystone does not currently claim:

- enterprise high availability or disaster recovery
- validated multi-node distributed production deployment
- production OIDC or SAML integration
- independent penetration testing
- formal accessibility certification
- complete AI governance coverage
- completeness of the Governed Execution substrate
- completeness of the change-class taxonomy
- portability across arbitrary workloads
- correctness of composed mechanisms merely because individual components passed
- semantic correctness merely because audit evidence has integrity
- universal effectiveness of retrieval or RAG
- universal effectiveness of AI for operational transformation

---

## Engineering background

Keystone is informed by more than 12 years of enterprise contact-center and cloud systems work at Genesys.

That background included:

- customer discovery
- technical requirements
- enterprise knowledge systems
- classification and earlier conversational AI
- Digital Services
- Agent Workspace
- customer and interaction data
- routing
- workflow automation
- WFM-integrated operational statistics
- enterprise integrations
- on-premises, hybrid, and cloud environments
- migrations
- go-lives
- clustered and high-volume deployments
- production incidents
- distributed troubleshooting
- internal training and knowledge enablement

Direct work with customers, product managers, developers, technical directors, and support teams established much of the operational lineage behind Keystone:

```text
understand the real workflow
        ->
trace the actual execution path
        ->
separate symptoms from causes
        ->
identify failure domains
        ->
define the smallest useful change
        ->
test the change
        ->
observe the result
        ->
retain the evidence
```

Genesys-era classification and conversational systems are not presented as modern LLM systems.

They provide earlier operational experience with classification, confidence, routing, escalation, human handoff, and production support.

---

## Technology

### AI and retrieval

Python · FastAPI · Pydantic · PostgreSQL · pgvector · PostgreSQL full-text search · RAG · hybrid retrieval · embeddings · Ollama

### Evaluation and observability

pytest · deterministic evaluation · regression testing · structured artifacts · OpenTelemetry · Grafana Tempo

### Application and infrastructure

REST/HTTP APIs · Docker · Linux · Git · React · TypeScript

### Experimental or workload-specific

NATS JetStream · HHEM · HMAC integrity checks · hash-chained audit records

Experimental or workload-specific components should not be interpreted as platform-wide production capabilities.

---

## Public artifacts

- [Website](https://getkeystone.ai/)
- [Documentation](https://docs.getkeystone.ai/)
- [Live demo](https://demo.getkeystone.ai/)
- [Keystone Gov](https://github.com/getkeystone/keystone-gov)
- [Keystone Engage](https://github.com/getkeystone/keystone-engage)
- [Keystone Counsel](https://github.com/getkeystone/keystone-counsel)
- [Keystone Verify](https://github.com/getkeystone/keystone-verify)
- [Keystone Ledger](https://github.com/getkeystone/keystone-ledger)
- [Runtime Validity](https://github.com/getkeystone/runtime-validity)
- [Support Operations Intelligence](https://github.com/arnaldosepulveda/support-operations-intelligence)
- [Arnaldo Sepulveda](https://arnaldosepulveda.com/)
- [LinkedIn](https://www.linkedin.com/in/arnaldosepulveda/)
- [Contact](mailto:arnaldo@getkeystone.ai)

---

## Working principle

Understand the operation.

Establish what the evidence supports.

Choose the intervention.

Build the mechanism.

Test the mechanism.

Preserve failures.

Measure the outcome.

Keep the claim inside the evidence.
