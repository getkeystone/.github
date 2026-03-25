# Keystone AI

Governed closed-loop operational knowledge system for regulated operations.

Built for environments where answers must come from approved source material,
access must be enforced before retrieval, and every response must be auditable.
When knowledge is used, the system captures what worked, what was missing, and
what needs review -- closing the loop between written procedure and field reality.

## Live demo

**[demo.getkeystone.ai](https://demo.getkeystone.ai)** -- 56 Alberta OHS safety documents.
Log in as `operator1` / `demo123`.
Ask: "What atmospheric testing is required before entering a confined space?"

## What is demonstrated today

- Five-stage query pipeline: hybrid retrieval, reranking, LLM synthesis, HHEM scoring, output
- Factual consistency scoring on every response (HHEM-2.1-Open, 0-1 score)
- Fail-closed behavior: refuses when evidence is insufficient
- Query-time access control enforced before retrieval (four-role model)
- Tamper-evident audit trail with HMAC hash chain
- Prompt injection mitigation (10/10 adversarial tests blocked)
- Config-driven multi-tenant deployment (same engine, different document sets)
- Security hardened API (session TTL, rate limiting, input sanitization)
- Professional operator-facing console with role-aware navigation

## What is NOT claimed

- Enterprise HA or disaster recovery
- Multi-node or distributed deployment
- OIDC/SAML production identity integration
- Third-party penetration testing
- WCAG accessibility compliance

When evidence quality is weaker, we say so. See the proof ledger.

## Where to verify claims

| Resource | Purpose |
|---|---|
| [demo.getkeystone.ai](https://demo.getkeystone.ai) | Live demo with Alberta OHS documents |
| [keystone-kdat](https://github.com/getkeystone/keystone-kdat) | Public proof ledger (55 milestones) |
| [getkeystone.ai](https://getkeystone.ai) | Product website |

## Stack

Python, FastAPI, PostgreSQL + pgvector, Ollama (local LLM inference),
HHEM-2.1-Open (factual consistency), Docker Compose, Cloudflare (tunnel + TLS).

No cloud dependency for core operation. Air-gap compatible.

## Contact

- **Website:** [getkeystone.ai](https://getkeystone.ai)
- **LinkedIn:** [Arnaldo Sepulveda](https://linkedin.com/in/arnaldosepulveda)
- **Email:** arnaldo@getkeystone.ai
