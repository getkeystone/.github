# Keystone Applied Intelligence

**Independent AI engineering and R&D practice building retrieval, conversational AI, evaluation, and runtime-control systems for enterprise and higher-consequence environments.**

Keystone is an environment for building concrete AI mechanisms, testing how they behave, retaining evidence, and improving the implementation when evaluation exposes failures.

Keystone's public projects are related engineering instruments, but they should not be interpreted as one fully composed or universally validated production runtime. A mechanism demonstrated in one workload is not automatically attributed to another.

## Applied AI systems

Current work spans retrieval and RAG, conversational workflows, authorization-aware retrieval, evaluation and regression tooling, observability, local model execution, explicit task state, and bounded runtime controls.

### Keystone Gov

[Keystone Gov](https://github.com/getkeystone/keystone-gov) is a FastAPI RAG reference implementation. Its query path combines PostgreSQL full-text search and pgvector retrieval, query-time ACL predicates, deterministic procedural reranking, evidence thresholds, local generation, HHEM as an additional factual-consistency signal, and per-record HMAC integrity checks with documented coverage limits.

### Keystone Engage

[Keystone Engage](https://github.com/getkeystone/keystone-engage) is a conversational and workflow AI reference implementation. The default served application uses one `EngageOrchestrator` with retrieval authorization, escalation, intent classification, RAG dispatch, task state, and audit records.

A separate experimental application path registers five specialist agent identities across four coordination phases. Optional NATS JetStream integration belongs to that experimental path. This is not evidence of distributed production execution, durable leases, fencing, compare-and-swap guarantees, distributed correctness, or high availability.

### Keystone Counsel

[Keystone Counsel](https://github.com/getkeystone/keystone-counsel) implements authorization-first retrieval. Role decisions run before retrieval; classification and client predicates restrict candidate rows before model context construction. The response path includes confidence gating and citations.

Regression tests cover a previously identified cross-client retrieval-isolation defect. The public corpus is currently global content, and the implementation does not establish production enterprise identity integration or a production multi-client deployment.

### Keystone Verify

[Keystone Verify](https://github.com/getkeystone/keystone-verify) is endpoint-agnostic evaluation tooling. Profiles describe compatible HTTP endpoints, declarative cases define assertions, and a deterministic pure-function judge evaluates mapped response fields. The runner measures latency and writes structured results and run metadata.

The output is inspectable JSON evidence. It is not cryptographically sealed and does not prove the substantive correctness of the evaluated system.

### Keystone Ledger

[Keystone Ledger](https://github.com/getkeystone/keystone-ledger) retains internal evaluation artifacts, lineage, negative results, remediations, and evidence limitations. PASS and FAIL verdicts apply to the named cases, configurations, commits, and runs. They are not independent external validation.

## Evaluation

Evaluation is part of the engineering loop rather than a final demonstration.

The retained `keystone-core/agent-v1` internal evaluation records:

* 186 cases across 12 categories
* 558 executions across three runs
* adversarial authorization and bypass testing
* 153 strict-pass cases, 33 characterization cases, and 0 strict failures at the evaluated commit

Its failing predecessor is retained alongside the passing run. The evaluation surfaced implementation defects, including audit timestamp handling and missing injection patterns, which were then remediated and regression-tested.

Other workloads have separate suites and evidence boundaries. These results should not be collapsed into one universal Keystone score.

> An evaluation system should be able to expose implementation failures, not only confirm expected behavior.

## Observability and operational engineering

The default Engage application calls its OpenTelemetry setup on the served path. Current implementation evidence supports:

* manual GenAI spans with model attributes
* prompt and completion token attributes
* latency attributes
* automatic FastAPI HTTP tracing
* OTLP/gRPC trace export
* manually verified trace delivery to a self-hosted Grafana Tempo backend

This does not establish OpenTelemetry Metrics API or `MeterProvider` support. Prometheus, Grafana dashboard, and Alertmanager configuration elsewhere should not be read as demonstrated runtime observability or enforcement.

Operational evidence is kept distinct from stronger conclusions: traces show recorded execution behavior, not that an action was authorized, justified, correct, or safe.

## Engineering evidence and boundaries

Mechanisms are attributed to the workload where they are implemented:

| Workload | Current evidence |
|---|---|
| Gov | PostgreSQL FTS + pgvector hybrid retrieval, query-time ACLs, procedural reranking, bounded HHEM signal, per-record HMAC checks |
| Engage | Single-orchestrator served path, experimental specialist coordination, task lifecycle mechanisms, hash-chained audit records, served-path tracing |
| Counsel | Role, classification, and client retrieval restrictions; confidence gating; cross-client regression coverage |
| Verify | Deterministic assertion-based HTTP evaluation and structured run artifacts |
| Ledger | Retained internal evaluation lineage, failures, remediations, and limitations |
| Runtime Validity | Controlled process-local authority-change and revalidation experiment |

Local inference is available in the documented Gov, Engage, and Counsel paths through Ollama. Hash-chain formats and verification scope differ by workload; integrity evidence does not establish semantic correctness or valid authorization.

## Governed Execution

**Governed Execution is Keystone's research program examining runtime governance for consequential AI actions.** It is separate from the applied workload identity above and is not an existing production runtime.

> Orchestration determines how work proceeds. Governance determines whether the intended consequence remains justified to proceed.

The research architecture separates:

* a **Control plane** for authority, policy, admissibility, placement, budget, and release
* an **Execution plane** for models, retrieval, tools, delegation, and workflows
* an **Evidence plane** for decisions, authorizations, actions, evaluations, failures, and outcomes
* a separate **action boundary** determining whether output may create external consequence

Six candidate runtime substrate dimensions are under study:

* Identity
* Task state
* Tempo
* Cost
* Currency
* Fidelity

Here, Currency asks:

> Does the original justification still legitimately authorize the intended consequence at the point of execution?

Candidate classes of governance-material change include Authority, Governance / policy, Evidence, Target / environment, Interface / tool, and Execution state.

The dimensions and change-class taxonomy are research hypotheses to test. They are not a complete ontology or validated coverage of AI governance.

### Track A: Runtime Validity

[Runtime Validity](https://github.com/getkeystone/runtime-validity) is the canonical repository for Track A.

Its current research question is:

> Given a prior decision justification composed of heterogeneous governance obligations, which controlled runtime interventions invalidate which obligations, and under what conditions does obligation-scoped revalidation preserve the same policy-expected disposition as full commit-boundary reevaluation with lower revalidation work?

Research priorities are invalidation mapping first, disposition preservation second, and revalidation work or latency third. These are priorities for the research program, not claims that the current implementation has completed them.

The current implementation supports only a controlled process-local authority change, retention of a process-local transition artifact, and a full-revalidation result that can change from `MATCH` / `PROCEED` to `MISMATCH` / `HOLD`. `HOLD` is an implementation design choice, not a universal research conclusion. With `revalidation_mode="none"`, authority is `NOT_EVALUATED`; proceeding does not establish that the intended consequence remains justified.

This evidence does not establish authentic external revocation, independent witness evidence, production authentication or authorization, durable persistence, cryptographic decision-to-transition binding, external consequence enforcement, distributed correctness, or universal validity of the Governed Execution architecture.

The name **Governed Execution Runtime** is reserved for a future composed runtime. The current public repositories do not demonstrate that composition.

## Implementation model

Selected engineering implementations, documentation, evaluation methods, and artifacts are public. Some operational and deployment components remain private. Public research reference implementations are intentionally separable from applied workloads.

Composition requires its own engineering and evaluation. Passing components do not establish that a composed system is correct, portable, or production-suitable.

## What Keystone does not claim

Keystone does not currently claim:

* enterprise high availability or disaster recovery
* validated multi-node distributed production deployment
* production OIDC or SAML integration
* independent penetration testing
* formal accessibility certification
* completeness of the Governed Execution substrate or change taxonomy
* portability across arbitrary workloads
* correctness of composed mechanisms merely because components passed individually
* semantic correctness merely because audit evidence has integrity

## Engineering background

Keystone is informed by more than 12 years of enterprise contact-center and cloud systems work at Genesys. That experience included knowledge retrieval, classification and earlier conversational systems, Digital Services, Agent Workspace, customer and interaction data, routing, WFM-integrated operational statistics, enterprise integrations, production incidents, migrations, go-lives, clustered and high-volume deployments, and distributed troubleshooting.

Direct work with customers, product managers, developers, and technical leaders established the operational lineage behind Keystone: trace the real execution path, isolate failure domains across product boundaries, preserve evidence, and improve systems without confusing an observed behavior with a universal conclusion. Genesys-era classification and conversational systems are not presented as modern LLM systems.

## Public artifacts

* [Website](https://getkeystone.ai/)
* [Documentation](https://docs.getkeystone.ai/)
* [Live demo](https://demo.getkeystone.ai/)
* [Keystone Gov](https://github.com/getkeystone/keystone-gov)
* [Keystone Engage](https://github.com/getkeystone/keystone-engage)
* [Keystone Counsel](https://github.com/getkeystone/keystone-counsel)
* [Keystone Verify](https://github.com/getkeystone/keystone-verify)
* [Keystone Ledger](https://github.com/getkeystone/keystone-ledger)
* [Runtime Validity](https://github.com/getkeystone/runtime-validity)
* [Personal engineering portfolio](https://arnaldosepulveda.com/)
* [LinkedIn](https://www.linkedin.com/in/arnaldosepulveda/)
* [Contact](mailto:arnaldo@getkeystone.ai)
