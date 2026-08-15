# Keystone Applied Intelligence

**Governed AI systems, retrieval, and evaluation infrastructure for regulated environments.**

Local-first. Evidence-backed. Fail-closed.

Keystone Applied Intelligence is an independent engineering and R&D practice exploring how AI systems can operate under explicit authority, evidence, evaluation, and audit constraints.

The work focuses on the runtime layer between model capability and production consequence.

The goal is not to make stronger claims about AI systems. It is to make narrower claims that can be tested, inspected, reproduced, and challenged.

---

## What Keystone builds

Keystone currently develops three related workloads on shared infrastructure:

### Keystone Engage

Governed conversational and agent workflows for higher-consequence interactions, including explicit task state, evaluation, escalation, and human review patterns.

### Keystone Counsel

Authorization-first retrieval for legal, financial, compliance, and other access-controlled knowledge workloads.

### Keystone Verify

Endpoint-agnostic evaluation infrastructure for governed retrieval and agent systems, with reproducible artifacts and regression evidence.

These workloads share common infrastructure for identity, task state, retrieval authorization, event-driven coordination, audit evidence, evaluation, observability, and model dispatch.

---

## Implemented controls

Keystone treats governance controls as runtime mechanisms rather than prompt instructions.

Current implementation work includes:

* Authorization applied before protected content enters model context
* Query-time and corpus-scope retrieval predicates
* Fail-closed refusal when evidence or authorization is insufficient
* Explicit task lifecycle state
* Agent and runtime identity records
* Event-driven execution coordination
* Hash-chained audit records
* Endpoint-agnostic evaluation harnesses
* Structured failing and passing evaluation artifacts
* OpenTelemetry instrumentation for tokens, latency, cost, and budget
* Local-first model execution without external model-API dependency for core operation

Some broader governance mechanisms described in Keystone research, including generalized action-binding and change-aware execution-boundary revalidation, remain research architecture rather than demonstrated platform guarantees.

---

## Evaluation

Keystone publishes evaluation artifacts instead of treating successful demos as sufficient evidence.

Current evaluation work includes:

* A governed retrieval baseline with adversarial authorization testing
* Fail-closed retrieval behavior
* 186 evaluation cases across 12 categories and 558 executions
* Regression testing that surfaced real system defects before release
* Preserved failing runs alongside repaired and passing runs
* Structured evidence for reproducing evaluation results

The evaluation process has identified defects in retrieval isolation, domain scoping, scorer behavior, and retrieval configuration. Those failures are part of the evidence, not something removed from the project history.

The principle is simple:

> Claims should be limited to what has been built, tested, and preserved as evidence.

---

## Research

Keystone is also the experimental platform for a technical-governance research program.

The working manuscript:

**Governed Execution as a Runtime Contract: A Substrate Architecture for Agentic AI**

proposes six candidate runtime substrate dimensions:

* Identity
* Task state
* Tempo
* Cost
* Currency
* Fidelity

The dimensions are research hypotheses, not a claim that these six properties form a complete theory of AI governance.

A related research question now being developed is:

> When conditions change during an agent execution, which changes are material to a prior governance decision, what must be revalidated, and what evidence should allow an independent reviewer to reconstruct why the resulting action proceeded, was held, denied, or escalated?

The current candidate change classes include authority, governance, evidence, target/environment, interface, and execution state.

This taxonomy is also a hypothesis to test, not a predetermined answer.

---

## Public artifacts

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

The core platform implementation remains proprietary.

Public material includes:

* architecture,
* evaluation methods,
* research framing,
* design rationale,
* evaluation artifacts,
* selected tooling.

The proprietary implementation includes the primary runtime services, governed retrieval engine, orchestration components, application workflows, and deployment configuration.

The architecture and research claims are intentionally separable from the proprietary implementation.

---

## What Keystone does not claim

Keystone does not currently claim:

* Enterprise high availability or disaster recovery
* Multi-node distributed production deployment
* Production OIDC or SAML identity integration
* Independent penetration testing
* Formal accessibility certification
* Universal completeness of the proposed governance substrate
* Proven effectiveness of generalized action-binding controls
* Validated completeness of the proposed material-change taxonomy
* Formal proof that audit evidence establishes substantive correctness, safety, legality, or desirability

These boundaries are deliberate.

---

## Engineering background

Keystone is informed by more than 12 years of enterprise contact-center and cloud engineering experience at Genesys across on-premises, hybrid, and cloud environments.

That work included production troubleshooting, routing, knowledge retrieval, digital channels, conversational systems, migrations, distributed integrations, and direct collaboration with customer engineers, DBAs, developers, deployment teams, and technical managers.

Many of the operational concerns now appearing in agentic AI systems are familiar systems-engineering problems:

* identity,
* state,
* routing,
* deadlines,
* capacity,
* authorization,
* escalation,
* recovery,
* evidence,
* auditability.

Large language models add new capabilities and failure modes. They do not remove those operational requirements.

---

## Links

**Website:** https://getkeystone.ai/
**Documentation:** https://docs.getkeystone.ai/
**Platform:** https://getkeystone.ai/platform/
**Evaluation ledger:** https://github.com/getkeystone/keystone-ledger
**LinkedIn:** https://www.linkedin.com/in/arnaldosepulveda/
**Contact:** [arnaldo@getkeystone.ai](mailto:arnaldo@getkeystone.ai)
