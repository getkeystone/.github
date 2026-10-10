# Keystone Applied Intelligence

Independent applied AI engineering and research by [Arnaldo Sepulveda](https://www.linkedin.com/in/arnaldosepulveda/). Keystone Applied Intelligence is a Canadian sole proprietorship registered in 2026. Independent research and engineering work began in late 2024, before registration.

Keystone's developing direction is to help organizations understand operational workflows, establish credible evidence and baselines, diagnose operational constraints, compare possible interventions, determine whether AI is warranted, design and implement appropriate technical solutions, and evaluate technical behavior and operational outcomes. This is a developing services direction, not an assertion that Keystone has already delivered commercial client projects.

## Public repositories

### Implementation references

These are separately composed reference implementations, not one integrated production platform.

- [keystone-gov](https://github.com/getkeystone/keystone-gov): governed RAG — hybrid retrieval (PostgreSQL full-text search + pgvector), role-based ACL at the database layer, evidence thresholds, factual consistency scoring (HHEM-2.1-Open), fail-closed refusal, and HMAC-SHA256 audit trail.
- [keystone-counsel](https://github.com/getkeystone/keystone-counsel): authorization-first retrieval — role, document-classification, and client-isolation filters for regulated content. Enforced at the retrieval layer, not post-filtered.
- [keystone-engage](https://github.com/getkeystone/keystone-engage): governed conversational agent — authorization before retrieval, severity-tier human routing, intent classification, fail-closed refusal, and hash-chained audit. A multi-agent coordinator exists behind a feature flag; the served path is a single orchestrator.

### Evaluation and evidence

- [keystone-verify](https://github.com/getkeystone/keystone-verify): standalone endpoint-agnostic evaluation harness with a deterministic judge, declarative assertions, and structured JSON artifacts. Open-source.
- [keystone-ledger](https://github.com/getkeystone/keystone-ledger): retained evaluation runs — passing and failing runs, negative results, remediation lineage, and per-test artifacts. Internal evaluation, not independent validation.

### Architecture and research

- [keystone-platform-docs](https://github.com/getkeystone/keystone-platform-docs): architecture, evaluation methodology, and research documentation.
- [runtime-validity](https://github.com/getkeystone/runtime-validity): bounded research into whether runtime condition changes invalidate obligations supporting a prior decision. An experimental research component, not validation of a full Governed Execution architecture.

## Evaluation evidence

keystone-core/agent-v0 was evaluated on 186 cases across 12 categories at keystone-gov commit ff66368: 144 strict passes, 9 strict failures, and 33 characterization cases. The failures traced to four implementation defects, which were fixed. keystone-core/agent-v1 reran the same 186 cases at commit 6ac192a (558 executions): 153 strict passes and 33 characterization cases. Results apply only to the evaluated commits, configurations, and cases, and are not independent validation. Both runs are retained in keystone-ledger.

## Real-user pilot

A role-aware knowledge-access prototype built from this work was piloted on-premises by a small group at a volunteer fire department, and their feedback shaped later refinements. This is not an organization-wide deployment or a measured operational outcome.

## Not claimed

- Commercial deployments or paying customers
- One integrated production platform across these repositories
- Independent or third-party evaluation
- Enterprise HA or disaster recovery
- Multi-node distributed production deployment
- Production OIDC/SAML identity integration
- Third-party penetration testing
- Formal accessibility certification

## Stack

Python · FastAPI · Pydantic · PostgreSQL 16 + pgvector · Ollama · OpenTelemetry · Grafana Tempo · Docker Compose · Caddy · React / TypeScript · NATS JetStream (experimental)

[getkeystone.ai](https://getkeystone.ai) · [Demo](https://demo.getkeystone.ai) · Maintained by [Arnaldo Sepulveda](https://www.linkedin.com/in/arnaldosepulveda/)
