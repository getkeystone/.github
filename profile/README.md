# Keystone Applied Intelligence

Governed conversational and retrieval AI for regulated industries. On-premises, evidence-backed, fail-closed.

Built from operational discipline, not from demos. Every architectural decision traces to a documented contact center governance pattern (severity-tier escalation, compliance logging, per-step validation, confidence-threshold refusal), rebuilt for the LLM substrate.

The system serves approved procedures with source citations and role-based access control, refuses when evidence is insufficient or out of corpus scope, scores every response for factual consistency, and records a tamper-evident audit trail. Runs entirely on customer-controlled infrastructure with no external API dependencies.

## Live demo

demo.getkeystone.ai - 53 Alberta OHS safety documents. Log in as operator1 / demo123. Ask: "What atmospheric testing is required before entering a confined space?"

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

### Governed agent extension (KDAT-002)

Same governance primitives applied to tool-using agents: per-step authorization, action audit trails, HITL approval enforced at the API layer. H1 confirmed 2026-05-20 (KDAT-002D). 186 eval cases, 12 categories, 558 executions, 0 failures. Eval identified 4 system bugs; all fixed and re-verified. Failing run (KDAT-002C) published.

## Recent

Governed agent extension (KDAT-002D, 2026-05-20): 186 eval cases, 12 categories, 558 executions, 153 strict pass, 33 characterization, 0 fail. Spec-compliant expansion from 66 to 186 cases identified 4 real system bugs (HMAC timestamp mismatch, 3 injection scanner gaps); all fixed and re-verified. Failing run (KDAT-002C) published. H1 confirmed: governance primitives for retrieval extend to tool-using agents. Full results in keystone-kdat.

FC-005 remediated (2026-05-17, v0.5.2-fc005). Pre-retrieval domain scope guard refusing out-of-corpus queries (emissions regulations, workers comp, tax, IT procurement). Closes the FC-005 failure mode from KDAT-001B. Commit: 38ef89f.

### Hackathon work (May 2026)

**governed-incident-agent** — KDAT-002 governance architecture applied to a CopilotKit generative UI. Per-action authorization, fail-closed refusal, tamper-evident audit trail rendered as interactive components. Built solo for the AI Tinkerers Generative UI Hackathon, Boston, May 9, 2026.

**Provana AcuteCare** — Clinical copilot with role-based action guardrails. Built collaboratively at the same hackathon, applying the governed-incident-agent scaffold to acute care medicine. Same governance architecture, different domain.

## Evaluation baselines

Governed agent extension (KDAT-002D, 2026-05-20): 186 eval cases, 12 categories, 558 executions, 153 strict pass, 33 characterization, 0 fail. Spec-compliant expansion from 66 to 186 cases identified 4 real system bugs (HMAC timestamp mismatch, 3 injection scanner gaps); all fixed and re-verified. Failing run (KDAT-002C) published. H1 confirmed: governance primitives for retrieval extend to tool-using agents.

KDAT-001B (2026-04-11): Governed retrieval.

- Retrieval: P@1 = 0.75, MRR = 0.79
- Adversarial ACL testing: 8/8 blocked, 0 leaks
- Audit chain: intact and immutable
- Fail-closed: 5/6 (83%). FC-005 remediated 2026-05-17.

Forward eval lineage uses `keystone-{component}/{type}-v{n}` versioning. KDAT-001B and KDAT-002D remain published as the canonical historical baselines; the migration cross-reference lives in keystone-kdat.

## Next

The platform is extending into three regulated verticals:

- **keystone-engage** — governed conversational agents for regulated customer interaction. Severity-tier HITL, behavioral content library with citation, per-step evidence gating. Direct continuation of the KDAT-002 agent work.
- **keystone-counsel** — regulated content retrieval for legal and financial advisory contexts. Direct continuation of the KDAT-001 retrieval work, applied to higher-stakes corpora.
- **keystone-verify** — standalone evaluation harness released as a public framework. Productization of the discipline that found four real bugs in KDAT-002.

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
| Website | getkeystone.ai |
| Live demo | demo.getkeystone.ai |
| Blog | getkeystone.ai/blog |
| LinkedIn | Arnaldo Sepulveda |
| Eval ledger | getkeystone/keystone-kdat |
| Contact | arnaldo@getkeystone.ai |
