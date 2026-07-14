# Keystone Applied Intelligence

Governed AI infrastructure for regulated industries.  
Local-first, evidence-backed, fail-closed.

Keystone is a platform for AI systems that must operate under real regulatory
pressure — where a wrong answer, an unauthorized retrieval, or an unaudited
action creates safety, compliance, or legal risk. It is three extensions on one
shared substrate, with governance, authorization, and evaluation designed in
from the first commit rather than bolted on afterward. It is a governed
operating model for retrieval and agent systems, not a demo wrapper around a
model API.

## What the platform covers

Three regulated AI workloads on one shared substrate:

- **Engage** — governed conversational agents for regulated customer interaction.
- **Counsel** — authorization-first retrieval for legal, financial, and compliance content.
- **Verify** — an endpoint-agnostic evaluation harness for governed AI systems.

The substrate — agent registry, task state machine, hash-chained audit ledger,
event bus, agent-scoped tools, and cost-aware dispatch — is what makes this a
platform: new behaviors register onto it instead of rebuilding orchestration.

## What Keystone enforces

Structural properties, not prompt instructions:

- evidence-backed answers tied to source documents,
- fail-closed refusal when evidence or authorization is insufficient,
- access control enforced at retrieval time (in the query, not after it),
- tamper-evident, hash-chained auditability for queries and actions,
- human review for high-consequence actions,
- local-first deployment with no external model-API dependency for core operation.

## Proven, not implied

Keystone publishes eval baselines, failing runs, passing runs, and remediation
history. Current public proof includes a governed retrieval baseline with
adversarial ACL blocking and fail-closed behavior; a governed agent baseline of
186 cases across 12 categories with 0 failures; and an evaluation methodology
that surfaced real bugs in the system it was testing — with the failing runs
preserved alongside the passing runs. The point is to make claims that survive
inspection.

## Public artifacts

- **[Platform documentation](https://docs.getkeystone.ai/)** — architecture, the
  substrate model, extension capabilities, evaluation methodology, and access policy.
- **[keystone-verify](https://github.com/getkeystone/keystone-verify)** — the
  open, endpoint-agnostic evaluation framework.
- **[keystone-ledger](https://github.com/getkeystone/keystone-ledger)** — the
  published evaluation ledger with sealed passing and failing artifacts.
- **[Platform demo](https://getkeystone.ai/platform/)** — the employer-facing
  platform narrative.

## Proprietary implementation

The substrate and extension source — the conversational agent, the
authorization-first retrieval engine, the substrate API, and the deployment
configuration — is proprietary. The architecture, evaluation outcomes, and design
rationale are public (above); the implementation is the product.

Read-only access for interview-depth technical review is available on request to
hiring managers, staff engineers, and technical evaluators. Response within 24
hours. See the [access policy](https://docs.getkeystone.ai/access/).

## Not claimed

Keystone does **not** currently claim enterprise HA/disaster recovery, multi-node
distributed production deployment, production OIDC/SAML identity integration,
third-party penetration testing, or formal accessibility certification. Claims
are limited to what has been built, tested, and published.

## Links

- Website: [getkeystone.ai](https://getkeystone.ai)
- Docs: [docs.getkeystone.ai](https://docs.getkeystone.ai/)
- Platform: [getkeystone.ai/platform](https://getkeystone.ai/platform/)
- Eval ledger: [getkeystone/keystone-ledger](https://github.com/getkeystone/keystone-ledger)
- Lead engineer: [Arnaldo Sepulveda](https://www.linkedin.com/in/arnaldosepulveda/)
