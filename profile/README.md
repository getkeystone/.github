# Keystone AI

Governed knowledge retrieval for regulated industries. On-premises, evidence-backed, fail-closed.

The system serves approved procedures with source citations and role-based access control, refuses when evidence is insufficient or out of corpus scope, scores every response for factual consistency, and records a tamper-evident audit trail. Runs entirely on customer-controlled infrastructure with no external API dependencies.

## Live demo

**[demo.getkeystone.ai](https://demo.getkeystone.ai)** — 53 Alberta OHS safety documents.
Log in as `operator1` / `demo123`.
Ask: "What atmospheric testing is required before entering a confined space?"

## Demonstrated capabilities

- Pre-retrieval query pipeline: input validation, prompt injection check, jurisdiction guard, domain scope guard, RBAC
- Hybrid retrieval (pgvector + full-text search) with ACL filtering and reranking
- Evidence thresholding before LLM synthesis
- Factual consistency scoring (HHEM-2.1-Open) on every response
- Fail-closed refusal on insufficient evidence or out-of-corpus queries
- Tamper-evident audit trail with HMAC-SHA256 hash chain and INSERT-only database role
- Governed review workflow with separation of duties enforced at the API layer
- Document version tracking with point-in-time retrieval
- Config-driven multi-deployment architecture (same engine, different document sets and feature flags)

## In development

Governed agent extension (KDAT-002): same governance primitives applied to tool-using agents. Per-step authorization, action audit trails, HITL approval enforced at the API layer. Follow this org for updates.

## Recent

**FC-005 remediation deployed (2026-05-17, v0.5.2-fc005).** Pre-retrieval domain scope guard refusing out-of-corpus queries (emissions regulations, workers comp, tax, IT procurement). Closes the FC-005 failure mode from KDAT-001B where a TIER greenhouse gas query returned Part 36 mine gas chunks via embedding overlap. Validated manually against the KDAT-001B probe set. Full taxonomy-based two-stage gate scoped for KDAT-002. Commit: [38ef89f](https://github.com/getkeystone/keystone-gov/commit/38ef89f).

## Hackathon work (May 2026)

[**governed-incident-agent**](https://github.com/arnaldosepulveda/governed-incident-agent) — KDAT-002 governance architecture applied to a CopilotKit generative UI. Per-action authorization, fail-closed refusal, tamper-evident audit trail rendered as interactive components. Built solo for the AI Tinkerers Generative UI Hackathon, Boston, May 9, 2026.

[**Provana AcuteCare**](https://getkeystone.ai/blog/provana-acutecare/) — Clinical copilot with role-based action guardrails. Built collaboratively at the same hackathon, applying the governed-incident-agent scaffold to acute care medicine. Same governance architecture, different domain.

## Evaluation baseline (KDAT-001B, 2026-04-11)

- Retrieval: P@1 = 0.75, MRR = 0.79
- Adversarial ACL testing: 8/8 blocked, 0 leaks
- Audit chain: intact and immutable
- Fail-closed: 5/6 (83%). FC-005 remediated 2026-05-17; sealed re-eval pending KDAT-002.

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
| Blog | [getkeystone.ai/blog](https://getkeystone.ai/blog/) |
| LinkedIn | [Arnaldo Sepulveda](https://linkedin.com/in/arnaldosepulveda) |
| Eval ledger | [getkeystone/keystone-kdat](https://github.com/getkeystone/keystone-kdat) |
| Contact | [arnaldo@getkeystone.ai](mailto:arnaldo@getkeystone.ai) |
