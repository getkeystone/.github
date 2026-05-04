# Keystone AI

Governed knowledge retrieval for regulated industries. On-premises, evidence-backed, fail-closed.

The system serves approved procedures with source citations and role-based access control, refuses when evidence is insufficient, scores every response for factual consistency, and records a tamper-evident audit trail. Runs entirely on customer-controlled infrastructure with no external API dependencies.

## Live demo

**[demo.getkeystone.ai](https://demo.getkeystone.ai)** — 53 Alberta OHS safety documents.
Log in as `operator1` / `demo123`.
Ask: "What atmospheric testing is required before entering a confined space?"

## Demonstrated capabilities

- 11-step query pipeline: input validation, jurisdiction scoping, RBAC, hybrid retrieval (pgvector + FTS), ACL filtering, reranking, evidence thresholding, LLM synthesis, factual consistency scoring (HHEM-2.1-Open), fail-closed gate, hash-chained audit logging
- Query-time access control enforced before retrieval (four-role model)
- Tamper-evident audit trail with HMAC-SHA256 hash chain and INSERT-only database role
- Fail-closed refusal when evidence is insufficient
- Governed review workflow with separation of duties enforced at the API layer
- Document version tracking with point-in-time retrieval
- Config-driven multi-deployment architecture (same engine, different document sets and feature flags)

## In development
Governed agent extension (KDAT-002): same governance primitives applied to tool-using agents. Per-step authorization, action audit trails, HITL approval enforced at the API layer. Follow this org for updates.

## Evaluation baseline (KDAT-001B, 2026-04-11)

- Retrieval: P@1 = 0.75, MRR = 0.79
- Adversarial ACL testing: 8/8 blocked, 0 leaks
- Audit chain: intact and immutable
- Fail-closed: 5/6 (83%)

## Not claimed

- Enterprise HA or disaster recovery
- Multi-node or distributed deployment
- OIDC/SAML production identity integration
- Third-party penetration testing
- WCAG accessibility compliance

## Stack

Python, FastAPI, PostgreSQL 16 + pgvector, Ollama (nomic-embed-text, qwen2.5:7b-instruct), React/TypeScript/Tailwind, Docker Compose, Caddy, Cloudflare Tunnels. No cloud dependency for core operation.

## Links

| | |
|---|---|
| Website | [getkeystone.ai](https://getkeystone.ai) |
| Live demo | [demo.getkeystone.ai](https://demo.getkeystone.ai) |
| LinkedIn | [Arnaldo Sepulveda](https://linkedin.com/in/arnaldosepulveda) |
| Eval ledger | [getkeystone/keystone-kdat](https://github.com/getkeystone/keystone-kdat) |
| Contact | [arnaldo@getkeystone.ai](mailto:arnaldo@getkeystone.ai) |
