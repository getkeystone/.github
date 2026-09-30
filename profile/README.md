# Keystone Applied Intelligence

Independent applied AI engineering and research by Arnaldo Sepulveda, started in late 2024.

These repositories are separate reference implementations for retrieval, authorization-aware access, conversational workflows, and evaluation, built and tested on local infrastructure. They are not a commercial product and do not represent client engagements.

## Repositories

- [keystone-gov](https://github.com/getkeystone/keystone-gov): hybrid retrieval and RAG API (PostgreSQL full-text search + pgvector) with citations, evidence thresholds that refuse when support is insufficient, query-time access control, and an HMAC-chained audit log.
- [keystone-counsel](https://github.com/getkeystone/keystone-counsel): authorization-first retrieval with role, document-classification, and client-isolation filters.
- [keystone-engage](https://github.com/getkeystone/keystone-engage): conversational workflow reference implementation with a default single orchestrator; a multi-agent coordinator is experimental and behind a feature flag.
- [keystone-verify](https://github.com/getkeystone/keystone-verify): endpoint-agnostic evaluation harness with declarative assertions over HTTP responses and structured JSON results.
- [keystone-ledger](https://github.com/getkeystone/keystone-ledger): retained evaluation runs, including failing runs, negative results, and remediation lineage.
- [keystone-platform-docs](https://github.com/getkeystone/keystone-platform-docs): architecture, evaluation, and research documentation for these reference implementations.
- [runtime-validity](https://github.com/getkeystone/runtime-validity): exploratory research on re-checking authority before an action proceeds. See its README for claim boundaries.

## Evaluation evidence

keystone-core/agent-v0 was evaluated on 186 cases across 12 categories at keystone-gov commit ff66368: 144 strict passes, 9 strict failures, and 33 characterization cases. The failures traced to four implementation defects, which were fixed. keystone-core/agent-v1 reran the same 186 cases at commit 6ac192a (558 executions): 153 strict passes and 33 characterization cases. Results apply only to the evaluated commits, configurations, and cases, and are not independent validation. Both runs are retained in keystone-ledger.

## Real-user pilot

A role-aware knowledge-access prototype built from this work was piloted on-premises by a small group at a volunteer fire department, and their feedback shaped later refinements. This is not an organization-wide deployment or a measured operational outcome.

## Not claimed

- commercial deployments or paying customers
- one integrated production platform across these repositories
- independent or third-party evaluation
- enterprise HA or disaster recovery
- multi-node distributed production deployment
- production OIDC/SAML identity integration
- third-party penetration testing
- formal accessibility certification

## Stack

Python · FastAPI · Pydantic · PostgreSQL 16 + pgvector · Ollama · OpenTelemetry · Grafana Tempo · Docker Compose · Caddy · React / TypeScript · NATS JetStream (experimental)

[getkeystone.ai](https://getkeystone.ai) · [Demo](https://demo.getkeystone.ai) · Maintained by [Arnaldo Sepulveda](https://www.linkedin.com/in/arnaldosepulveda/)
