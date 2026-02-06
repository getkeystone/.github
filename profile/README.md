# Keystone AI

On-prem AI knowledge infrastructure for organizations that cannot use cloud AI.

Keystone AI is built for **regulated and compliance-constrained environments** where data sovereignty and auditability are mandatory.

Runs fully on customer infrastructure. No external API calls. Air-gap compatible.

## Current milestone: single-machine air-gapped proof (KDAT-001A)

The first public proof is a single-machine demo that runs fully offline and demonstrates:

- Evidence-backed answers with citations
- Fail-closed behavior when evidence is insufficient
- Query-time authorization (permission-aware retrieval)
- Tamper-evident audit records for every query (verifiable chain)
- Reproducible run (same results twice while air-gapped)

## Core Capabilities

### Governed Retrieval
- Query-time authorization (enforced at retrieval, not by trusting the LLM)
- Metadata-filtered retrieval with ACL fidelity from source systems
- Citation-backed answers with source lineage

### Multi-Source Ingestion
- SharePoint (Microsoft Graph API with OAuth delegation)
- File shares (SMB/NFS with permission metadata extraction)
- Databases (PostgreSQL, SQL Server, MySQL)
- Documents (PDF, Office formats, OCR fallback)

### Audit-Grade Logging
- Query, retrieval, and response logged by default
- Exportable audit records for reviews and incident response
- Evidence artifacts and runbook-driven verification

### On-Prem Deployment
- Air-gap compatible operation (no internet required)
- Docker Compose packaging for single-node and multi-node patterns
- Network segmentation patterns for regulated environments

## Repositories

| Repository | Purpose |
|-----------|---------|
| `keystone-core` | Retrieval + ingestion engine |
| `keystone-gov` | Authorization + audit records |
| `keystone-deploy` | Compose + runbooks for deployment and demo |
| `keystone-docs` | Architecture decisions, threat model, compliance notes |
| `keystone-web` | Marketing site |

## Contact

🌐 https://getkeystone.ai  
📧 arnaldo@getkeystone.ai  
💼 https://linkedin.com/in/arnaldo-sepulveda
