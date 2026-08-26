# Keystone Applied Intelligence

**Independent engineering and R&D practice for governed AI systems, agent infrastructure, retrieval, and evaluation.**

Local-first. Evidence-backed. Fail-closed.

Keystone Applied Intelligence develops and studies AI systems that operate under explicit authority, evidence, evaluation, and audit constraints.

The work focuses on the runtime layer between model capability and external consequence.

A central principle is:

> Orchestration determines how work proceeds. Governance determines whether the intended consequence remains justified to proceed.

The goal is not to make stronger claims about AI systems. It is to make narrower claims that can be implemented, tested, inspected, reproduced, and challenged.

---

## Engineering and research structure

Keystone combines applied AI engineering with a broader runtime-governance research program.

### Applied workloads

Keystone currently develops three related workloads on shared infrastructure.

#### Keystone Engage

Governed conversational and agent workflows for higher-consequence interactions, including explicit task state, evaluation, escalation, and human-review patterns.

#### Keystone Counsel

Authorization-first retrieval for legal, financial, compliance, and other access-controlled knowledge workloads.

#### Keystone Verify

Endpoint-agnostic evaluation infrastructure for governed retrieval and agent systems, with reproducible artifacts and regression evidence.

These workloads share infrastructure for identity, task state, retrieval authorization, event-driven coordination, audit evidence, evaluation, observability, and model dispatch.

### Governed Execution

**Governed Execution** is Keystone's runtime-governance research program and reference platform for autonomous and semi-autonomous AI systems.

Its current architecture separates:

* a **control plane** for authority, policy, admissibility, placement, budget, and release
* an **execution plane** for models, retrieval, tools, delegation, and workflows
* an **evidence plane** for decisions, authorizations, actions, evaluations, failures, and outcomes
* a separate **action boundary** governing whether model or agent output may create external consequence

Governed Execution is being developed through bounded research tracks.

Each track isolates a governance question so its behavior, assumptions, failure modes, and evidence can be tested separately before broader integration.

Results from an individual track do not automatically validate the broader platform. Composition, interaction effects, failure propagation, and portability require separate evaluation.

---

## Public research tracks

### Track A: Runtime Validity

**[Track A Runtime Validity](https://github.com/getkeystone/track-a-runtime-validity)** is the first public Governed Execution track.

It studies:

> Which runtime changes make a prior governance decision stale or otherwise invalid, what should trigger revalidation before consequential action, and what evidence should allow an external reviewer to reconstruct why the resulting action proceeded, was held, denied, or escalated?

The current Track A implementation evaluates a narrow authority-revalidation case.

It is an engineering reference implementation and experimental artifact, not evidence that the broader Governed Execution architecture is complete, correct, portable, or production-ready.

Future tracks are intended to isolate additional governance questions before composition into the broader reference platform.

---

## Implemented controls

Keystone treats governance controls as runtime mechanisms rather than prompt instructions.

Current implementation work includes:

* authorization applied before protected content enters model context
* query-time and corpus-scope retrieval predicates
* fail-closed refusal when evidence or authorization is insufficient
* explicit task lifecycle state
* agent and runtime identity records
* event-driven execution coordination
* hash-chained audit records
* endpoint-agnostic evaluation harnesses
* structured failing and passing evaluation artifacts
* OpenTelemetry instrumentation for tokens, latency, cost, and budget
* local-first model execution without external model-API dependency for core operation

Some broader mechanisms described in the Governed Execution research program remain research architecture rather than demonstrated platform guarantees.

---

## Evaluation

Keystone publishes evaluation artifacts rather than treating successful demonstrations as sufficient evidence.

Current evaluation work includes:

* a governed retrieval baseline with adversarial authorization testing
* fail-closed retrieval behavior
* 186 evaluation cases across 12 categories and 558 executions
* regression testing that surfaced implementation defects before release
* preserved failing runs alongside repaired and passing runs
* structured evidence for reproducing evaluation results

The evaluation process has identified defects in retrieval isolation, domain scoping, scorer behavior, and retrieval configuration.

Those failures are part of the evidence.

> Claims should be limited to what has been built, tested, and preserved as evidence.

---

## Research

The current working manuscript is:

**Governed Execution as a Runtime Contract: A Substrate Architecture for Agentic AI**

The manuscript proposes six candidate runtime substrate dimensions:

* Identity
* Task state
* Tempo
* Cost
* Currency
* Fidelity

These dimensions are research hypotheses and a candidate representation, not a claim that they form a complete ontology or theory of AI governance.

The current narrow research question is:

> Which runtime changes make a prior governance decision stale or otherwise invalid, what should trigger revalidation before consequential action, and what evidence should let an external reviewer reconstruct why the resulting action proceeded, was held, denied, or escalated?

Candidate classes of governance-material change currently include:

* Authority
* Governance / policy
* Evidence
* Target / environment
* Interface / tool
* Execution state

This taxonomy is also a hypothesis to test.

---

## Public artifacts

### Track A: Runtime Validity

Public runtime-validity and revalidation reference implementation:

https://github.com/getkeystone/track-a-runtime-validity

### Documentation

Architecture, evaluation methodology, runtime controls, and research notes:

https://docs.getkeystone.ai/

### Keystone Verify

Open endpoint-agnostic evaluation tooling:

https://github.com/getkeystone/keystone-verify

### Keystone Ledger

Published evaluation evidence, including passing and failing artifacts:

https://github.com/getkeystone/keystone-ledger

### Platform overview

https://getkeystone.ai/platform/

---

## Implementation model

Keystone uses a mixed public and proprietary implementation model.

Public material includes:

* selected research reference implementations
* architecture
* evaluation methods
* research framing
* design rationale
* evaluation artifacts
* selected tooling

The primary platform runtime, governed retrieval services, orchestration components, application workflows, deployment configuration, and operational infrastructure remain proprietary unless explicitly published.

Public research implementations such as Track A are intentionally separable from the proprietary runtime.

A public reference implementation should not be interpreted as evidence that the same mechanism has been validated across every Keystone workload or deployment environment.

---

## What Keystone does not claim

Keystone does not currently claim:

* enterprise high availability or disaster recovery
* multi-node distributed production deployment
* production OIDC or SAML identity integration
* independent penetration testing
* formal accessibility certification
* universal completeness of the proposed governance substrate
* validated completeness of the proposed material-change taxonomy
* that one research track validates the broader platform
* that composition of individually tested mechanisms is automatically correct
* formal proof that audit evidence establishes substantive correctness, safety, legality, or desirability

These boundaries are deliberate.

---

## Engineering background

Keystone is informed by more than 12 years of enterprise contact-center and cloud engineering experience at Genesys across on-premises, hybrid, and cloud environments.

That work included production troubleshooting, routing, knowledge retrieval, digital channels, conversational systems, migrations, distributed integrations, and direct collaboration with customer engineers, DBAs, developers, deployment teams, and technical managers.

Many operational concerns now appearing in agentic AI systems are familiar systems-engineering problems:

* identity
* state
* routing
* deadlines
* capacity
* authorization
* escalation
* recovery
* evidence
* auditability

Large language models introduce new capabilities and failure modes. They do not remove those operational requirements.

---

## Links

**Website:** https://getkeystone.ai/  
**Documentation:** https://docs.getkeystone.ai/  
**Platform:** https://getkeystone.ai/platform/  
**Track A:** https://github.com/getkeystone/track-a-runtime-validity  
**Evaluation ledger:** https://github.com/getkeystone/keystone-ledger  
**LinkedIn:** https://www.linkedin.com/in/arnaldosepulveda/  
**Contact:** [arnaldo@getkeystone.ai](mailto:arnaldo@getkeystone.ai)
