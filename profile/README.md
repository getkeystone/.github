# Keystone AI

On-prem AI knowledge infrastructure for organizations that cannot use cloud AI.

Keystone is being built for regulated and compliance-constrained environments where data sovereignty, access control, and auditability are mandatory.

Runs fully on customer infrastructure. No external API calls. Air-gap compatible.

## Proven today: KDAT-001A

KDAT-001A is the current public proof: a single-machine demo that runs fully offline and demonstrates:

- Evidence-backed answers with citations
- Fail-closed behavior when evidence is insufficient
- Query-time authorization
- Tamper-evident audit logging with chain verification
- Reproducible offline run on one machine

### What KDAT-001A is
- Single-machine proof of governed retrieval
- Local inference via Ollama
- Local vector search
- Local audit trail
- Proof-of-concept architecture, not production deployment

### What KDAT-001A does not prove
- Multi-node deployment
- HA/DR or cross-site failover
- OIDC / enterprise identity
- Full enterprise networking patterns
- Production-grade audit hardening
- Retrieval quality at larger corpus scale

## Core product direction

### Governed Retrieval
- Authorization enforced at query time
- Evidence threshold outside the model
- Citation-backed responses
- Fail-closed behavior when evidence is insufficient

### Governance Layer
- Audit records for every query
- Policy enforcement outside the LLM
- Trust-boundary-first design
- Honest documentation of limitations and residual risks

### On-Prem Deployment
- Customer-controlled infrastructure
- No required cloud dependency for core operation
- Air-gap compatible patterns
- Single-machine first, multi-node later

## Repositories

| Repository | Purpose |
|-----------|---------|
| `keystone-core` | Retrieval and query pipeline |
| `keystone-gov` | Authorization and audit subsystem |
| `keystone-deploy` | Demo packaging and deployment runbooks |
| `keystone-docs` | Architecture, ADRs, threat model, compliance notes |
| `keystone-web` | Public website |

## Near-term roadmap

Next milestone: **KDAT-001B**
- Retrieval evaluation
- Adversarial ACL testing
- Threat model publication
- Demo video
- External reproducibility validation

## Contact

🌐 https://getkeystone.ai  
📧 arnaldo@getkeystone.ai  
💼 https://linkedin.com/in/arnaldo-sepulveda
