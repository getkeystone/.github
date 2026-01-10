# Keystone AI

On-premise AI knowledge infrastructure for organizations that cannot use cloud AI.

## What This Is

Production RAG platform with query-time authorization, multi-source ingestion, and comprehensive audit logging.

Designed for deployment in air-gapped environments, regulated industries, and organizations where data sovereignty is mandatory.

## Core Capabilities

**Permission-Aware Retrieval**
- Query-time authorization (users only see content they're permitted to access)
- Role-based metadata filtering at vector search layer
- Access control inheritance from source systems (SharePoint ACLs, file permissions)
- Zero raw-text exposure in vector storage

**Multi-Source Ingestion**
- SharePoint (Microsoft Graph API with OAuth On-Behalf-Of flow)
- File shares (SMB/NFS with permission metadata extraction)
- Databases (PostgreSQL, SQL Server, MySQL)
- Email archives (Exchange, IMAP)
- Structured documents (PDF, Office formats with OCR fallback)

**Audit-Grade Logging**
- Every query logged: user identity, timestamp, query text
- Every retrieval logged: document sources, permission checks, chunk IDs
- Every response logged: generated answer, citations, model version
- Tamper-evident audit trail with cryptographic integrity

**On-Premise Deployment**
- No external API calls (runs entirely on customer infrastructure)
- Air-gap compatible (no internet dependencies)
- Docker Compose orchestration for single-node or multi-node clusters
- Network segmentation with VLAN isolation
- Encryption at rest, TLS in transit

## Target Deployments

Organizations operating under:
- NIST 800-171 (Controlled Unclassified Information)
- CMMC readiness frameworks (defense contractors)
- FedRAMP-aligned patterns (federal agencies)
- HIPAA (healthcare systems)
- SOX (financial services)

Defense contractors, federal agencies, energy operators, healthcare systems, legal firms, any organization where data control is non-negotiable.

## Architecture Stack

**Inference & Embeddings**
- Ollama for local LLM deployment (Qwen2.5-32B-Instruct, Llama 3.1)
- BGE-large-en-v1.5 for embeddings (1024-dim vectors)
- Multi-GPU support (RTX 3090/4090 class hardware)

**Vector Storage**
- Qdrant for metadata-filtered vector search
- PostgreSQL for permissions database, sync state, audit trails
- Zero raw-text storage in vector DB (hash-based chunk references only)

**API Layer**
- FastAPI with async processing and rate limiting
- WebSocket support for streaming responses
- OpenAPI/Swagger documentation
- JWT-based authentication with RBAC

**Security & Operations**
- SOPS with age encryption for secrets management
- Loki for centralized logging
- Prometheus + Grafana for monitoring
- Automated backup/restore with recovery time testing

## Repository Structure

| Repository | Purpose |
|-----------|---------|
| [`keystone-core`](https://github.com/getkeystone/keystone-core) | RAG engine: ingestion, indexing, retrieval pipeline |
| [`keystone-gov`](https://github.com/getkeystone/keystone-gov) | Access control, audit logging, policy enforcement |
| [`keystone-deploy`](https://github.com/getkeystone/keystone-deploy) | Docker Compose configs, network topology, deployment runbooks |
| [`keystone-docs`](https://github.com/getkeystone/keystone-docs) | Architecture decisions, security considerations, compliance mapping |

## What This Is Not

- Not a SaaS platform (no managed service, no subscription)
- Not a RAG-as-a-Service API (runs on your infrastructure)
- Not a compliance certification (enables compliance, does not certify)
- Not a cloud-first platform (cloud-hostile by design)

## Design Principles

1. **Query-time authorization** - permission checks at retrieval, not ingestion
2. **Zero external dependencies** - deployable without internet access
3. **Audit-first architecture** - logging is not optional, it's foundational
4. **Source system fidelity** - preserve ACLs, metadata, lineage from origin
5. **Production operations** - monitoring, backup/restore, security hardening built-in

## Use Cases

**Safety & Compliance**
- "What's the confined space entry procedure for Tank 401?"
- "Show me all JSAs related to electrical work in Zone 3"
- "What were the findings from the 2023 COR audit?"

**Operations & Maintenance**
- "How was pump failure P-2304 resolved in 2019?"
- "What's the torque spec for flange assembly on Line 7?"
- "Show me all maintenance records for Compressor C-401"

**Legal & Contracts**
- "Find all contracts with indemnification clauses mentioning IP"
- "What precedent cases involved force majeure in oil & gas?"
- "Show me clauses related to liquidated damages in construction contracts"

## Getting Started

**Requirements:**
- Linux host (Ubuntu 22.04+ recommended)
- GPU with 24GB+ VRAM (RTX 3090/4090 or better)
- 64GB+ system RAM
- Docker + Docker Compose
- Network-accessible source systems (SharePoint, file shares, databases)

**Quick Start:**
```bash
git clone https://github.com/getkeystone/keystone-deploy
cd keystone-deploy
./scripts/setup.sh
docker compose up -d
```

See [`keystone-deploy`](https://github.com/getkeystone/keystone-deploy) for detailed deployment instructions.

## Contact

🌐 [getkeystone.ai](https://getkeystone.ai)  
📧 arnaldo@getkeystone.ai  
💼 [LinkedIn](https://linkedin.com/in/arnaldo-sepulveda)

---

*Infrastructure for organizations that cannot afford to leak, lose, or hallucinate knowledge.*
