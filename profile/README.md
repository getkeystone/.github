# Keystone Applied Intelligence

Governed AI infrastructure for regulated industries.  
On-premises, evidence-backed, fail-closed.

Keystone Applied Intelligence is a platform for AI systems that must operate under real regulatory pressure. It is built for environments where wrong answers, unauthorized retrieval, or unaudited actions create safety, compliance, or legal risk.

This is not a demo wrapper around a model API. It is a governed operating model for retrieval and agent systems: evidence-backed answers, authorization at query time, fail-closed refusal, tamper-evident audit trails, and reproducible evaluation.

## What the platform covers

Keystone currently spans three regulated AI workloads on one shared substrate:

- **Keystone Engage** — governed conversational agents for regulated customer interaction.
- **Keystone Counsel** — authorization-first retrieval for legal, financial, and compliance content.
- **Keystone Verify** — standalone evaluation harness for governed AI systems.

Together they show that Keystone is not one use case. It is a reusable platform for multiple regulated AI workloads.

## Shared substrate

The platform substrate provides the mechanics that make this a platform instead of a collection of apps:

- agent identity and role registration,
- task lifecycle state management,
- hash-chained audit logging,
- event-driven coordination,
- dispatch abstraction for local or remote execution,
- sealed evaluation artifacts.

New behaviors can be added by registering new agents or profiles instead of rebuilding orchestration each time.

## What Keystone enforces

These are structural properties, not prompt instructions:

- evidence-backed answers tied to source documents,
- fail-closed refusal when evidence is insufficient,
- access control enforced at retrieval time,
- tamper-evident auditability for queries and actions,
- human review for high-consequence actions,
- local-first deployment with no external API dependency for core operation.

## Proven, not implied

Keystone publishes working systems, eval baselines, failing runs, passing runs, and remediation history.

Current public proof includes:

- governed retrieval baseline with adversarial ACL blocking and fail-closed behavior,
- governed agent baseline with 186 test cases across 12 categories and 0 failures,
- evaluation methodology that identified real bugs in the system it was testing,
- failing runs preserved alongside passing runs as part of the public record.

The point is not just to ship behavior. The point is to make claims that survive inspection.

## Current repositories

- [`keystone-engage`](https://github.com/getkeystone/keystone-engage) — governed conversational agents for regulated customer interaction.
- [`keystone-counsel`](https://github.com/getkeystone/keystone-counsel) — regulated content retrieval with authorization-first design.
- [`keystone-verify`](https://github.com/getkeystone/keystone-verify) — reusable evaluation harness for governed AI systems.
- [`keystone-ledger`](https://github.com/getkeystone/keystone-ledger) — evaluation ledger and lineage.
- [`keystone-web`](https://github.com/getkeystone/keystone-web) — project website.

## Technical position

Most LLM systems are still missing the operational discipline that regulated enterprise environments have required for years:

- severity-tier escalation,
- per-step validation,
- compliance logging,
- explicit authorization boundaries,
- confidence-threshold refusal,
- evaluation that preserves failing evidence instead of hiding it.

Keystone rebuilds that discipline for the LLM substrate.

## Deployment model

Keystone is designed for regulated deployment reality:

- local inference,
- local storage,
- local messaging,
- local observability,
- customer-controlled infrastructure.

Core operation does not require sending sensitive data to third-party model providers.

## Not claimed

Keystone does **not** currently claim:

- enterprise HA or disaster recovery,
- multi-node distributed production deployment,
- production OIDC/SAML identity integration,
- third-party penetration testing,
- formal accessibility certification.

Claims are limited to what has been built, tested, and published.

## Stack

Python · FastAPI · PostgreSQL 16 + pgvector · Ollama · React / TypeScript · Docker Compose · NATS JetStream · Grafana Tempo · Caddy · Cloudflare Tunnels

## Links

- Website: [getkeystone.ai](https://getkeystone.ai)
- Demo: [demo.getkeystone.ai](https://demo.getkeystone.ai)
- Blog: [getkeystone.ai/blog](https://getkeystone.ai/blog/)
- Eval ledger: [getkeystone/keystone-ledger](https://github.com/getkeystone/keystone-ledger)
- Lead engineer: [Arnaldo Sepulveda](https://www.linkedin.com/in/arnaldosepulveda/)
