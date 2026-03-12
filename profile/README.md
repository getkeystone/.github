# Keystone AI

On-premises AI knowledge infrastructure for organizations that cannot use cloud AI.

Built for regulated and compliance-constrained environments where data sovereignty,
access control, and auditability are mandatory.

No external API calls. Air-gap compatible. Runs entirely on customer infrastructure.

---

## Proven today: KDAT-001A

Single-machine offline proof demonstrating:

| Property | What is proven |
|---|---|
| Query-time ACL enforcement | Groups checked before retrieval. Users cannot retrieve unauthorized documents. |
| Evidence-backed answers | Every response cites a specific source document. |
| Fail-closed behavior | System refuses to answer when evidence is insufficient. See ADR-001. |
| Tamper-evident audit log | Hash-chained records. App DB user has INSERT-only permission. |
| Offline operation | Single machine, no internet connection required. |

## What KDAT-001A does NOT prove

- Multi-node or HA/DR deployment
- Enterprise identity (OIDC/SAML)
- Production-scale corpus validation
- Multi-source ingestion (SharePoint, SMB, SQL) — designed for, not yet demonstrated
- Compliance certification of any kind

## Repositories

| Repo | Purpose |
|---|---|
| [keystone-docs](https://github.com/getkeystone/keystone-docs) | Architecture, ADRs, threat model, KDAT evidence folders. Start here. |
| [keystone-core](https://github.com/getkeystone/keystone-core) | Retrieval and query pipeline. |
| [keystone-gov](https://github.com/getkeystone/keystone-gov) | Query-time authorization and tamper-evident audit subsystem. |
| [keystone-deploy](https://github.com/getkeystone/keystone-deploy) | Docker Compose packaging for reproducible offline demos. |

---

**Contact:** arnaldo@getkeystone.ai
**Website:** https://getkeystone.ai
**LinkedIn:** https://linkedin.com/in/arnaldo-sepulveda
