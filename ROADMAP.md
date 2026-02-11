# OpenKCM Roadmap

This document provides an overview of all tracked issues across OpenKCM repositories.

> **Note:** This is the current roadmap and will be updated periodically. For the most recent tasks and issues, please check our [GitHub Project Board](https://github.com/orgs/openkcm/projects).

---

## 📅 Timeline Overview

```
2026
│
├─ Q1 (Jan-Mar) ──── INVESTIGATION & DESIGN
│   ├── Low-Level Design (LLD) for Krypton
│   ├── KMIP Protocol POC
│   └── Architecture decisions finalized
│
├─ Q2 (Apr-Jun) ──── KRYPTON CORE DEVELOPMENT
│   ├── KMIP Server implementation
│   ├── KeyChain & Key lifecycle (L2-L4)
│   ├── Static MasterKey provider
│   ├── CLI tool (krypton command)
│   └── Platform Mesh deployment (Showroom demo)
│
├─ Q3 (Jul-Sep) ──── 🎯 CRYPTO LAYER MVP (End of Summer)
│   ├── MongoDB KMIP integration validated
│   ├── Multi-tenant key isolation
│   ├── mTLS authentication
│   ├── In-memory + persistent storage
│   └── Production-ready Showroom deployment
│
└─ Q4 (Oct-Dec) ──── CMK INTEGRATION & HARDENING
    ├── L1 (CMK) ↔ L2-L4 (Krypton) integration
    ├── Seal/Auto-Unseal implementation
    ├── Keystore plugins (OpenBao, AWS, Azure, GCP)
    └── HA & disaster recovery
```

### Key Milestones

| Milestone | Target Date | Description |
|-----------|-------------|-------------|
| 🔬 **LLD Complete** | Mar 2026 | Low-Level Design finalized, interfaces defined |
| 🚀 **Showroom Demo** | Jun 2026 | Krypton running on Platform Mesh with MongoDB |
| 🎯 **Crypto Layer MVP** | Aug 2026 | Production-ready KMIP server with multi-tenancy |
| 🔗 **Full Chain (L1-L4)** | Nov 2026 | CMK + Krypton integrated end-to-end |

---

## openkcm-controller

| # | Title | State | Link |
|---|-------|-------|------|
| 1 | [EPIC](apeiro) Tenant Management: Remote KCP-Aware -> OpenKCM Controller | OPEN | [#1](https://github.com/openkcm/openkcm-controller/issues/1) |

---

## crypto layer: Krypton

> 🎯 **MVP Target: End of Summer 2026 (August)**

### Q2 2026 - Core Development (Apr-Jun)

| # | Title | State | Link |
|---|-------|-------|------|
| 61 | [EPIC](crypto) Crypto Core & Edge Services Using KMIP 1.4 | OPEN | [#61](https://github.com/openkcm/crypto/issues/61) |
| 60 | [EPIC](crypto) Internal Versioned Key (IVK) Management (with Per-Version Algorithm Selection & Automatic L2.x Rotation) | OPEN | [#60](https://github.com/openkcm/crypto/issues/60) |

### Q3 2026 - MVP Completion (Jul-Aug) 🎯

| # | Title | State | Link |
|---|-------|-------|------|
| 40 | [Task](crypto \| ivk) IVK layer integration & algorithm agnosticism | OPEN | [#40](https://github.com/openkcm/crypto/issues/40) |
| 34 | [Task](crypto \| masterkey \| seal) OpenBao/Vault provider | OPEN | [#34](https://github.com/openkcm/crypto/issues/34) |
| 38 | [Task](crypto \| masterkey \| seal) Common Seal utilities & patterns | OPEN | [#38](https://github.com/openkcm/crypto/issues/38) |
| 39 | [Task](crypto \| masterkey \| seal) Configuration parsing & provider factory | OPEN | [#39](https://github.com/openkcm/crypto/issues/39) |
| 42 | [Task](crypto \| masterkey \| seal) Comprehensive testing suite | OPEN | [#42](https://github.com/openkcm/crypto/issues/42) |
| 43 | [Task](crypto \| masterkey \| seal) Documentation & operational guides | OPEN | [#43](https://github.com/openkcm/crypto/issues/43) |

### Q4 2026 - Post-MVP Hardening (Sep-Dec)

| # | Title | State | Link |
|---|-------|-------|------|
| 35 | [Task](crypto \| masterkey \| seal) AWS KMS provider | OPEN | [#35](https://github.com/openkcm/crypto/issues/35) |
| 36 | [Task](crypto \| masterkey \| seal) GCP KMS provider | OPEN | [#36](https://github.com/openkcm/crypto/issues/36) |
| 37 | [Task](crypto \| masterkey \| seal) Azure Key Vault provider | OPEN | [#37](https://github.com/openkcm/crypto/issues/37) |
| 41 | [Task](crypto \| masterkey \| seal) Security hardening & zeroization | OPEN | [#41](https://github.com/openkcm/crypto/issues/41) |

### Future - Shamir Secret Sharing (SSS) Mode

| # | Title | State | Link |
|---|-------|-------|------|
| 44 | [Task](crypto \| masterkey \| SSS) Implement SSS Generator CLI Tool | OPEN | [#44](https://github.com/openkcm/crypto/issues/44) |
| 45 | [Task](crypto \| masterkey \| SSS) Implement Shard Encryption Workflow (KMS/HSM Integration) | OPEN | [#45](https://github.com/openkcm/crypto/issues/45) |
| 46 | [Task](crypto \| masterkey \| SSS) Implement Shard Encryption Workflow (KMS/HSM Integration) | OPEN | [#46](https://github.com/openkcm/crypto/issues/46) |
| 47 | [Task](crypto \| masterkey \| SSS) Design and Implement Shard Database Persistence Layer | OPEN | [#47](https://github.com/openkcm/crypto/issues/47) |
| 48 | [Task](crypto \| masterkey \| SSS) Implement GF(256) Math Engine for Lagrange Interpolation | OPEN | [#48](https://github.com/openkcm/crypto/issues/48) |
| 49 | [Task](crypto \| masterkey \| SSS) Implement AWS KMS Decryption Client | OPEN | [#49](https://github.com/openkcm/crypto/issues/49) |
| 50 | [Task](crypto \| masterkey \| SSS) Implement GCP KMS Decryption Client | OPEN | [#50](https://github.com/openkcm/crypto/issues/50) |
| 51 | [Task](crypto \| masterkey \| SSS) Implement HashiCorp/OpenBao Vault Decryption Client | OPEN | [#51](https://github.com/openkcm/crypto/issues/51) |
| 52 | [Task](crypto \| masterkey \| SSS) Implement HSM (PKCS#11) Decryption Client | OPEN | [#52](https://github.com/openkcm/crypto/issues/52) |
| 53 | [Task](crypto \| masterkey \| SSS) Implement mTLS-backed REST Decryption Client | OPEN | [#53](https://github.com/openkcm/crypto/issues/53) |
| 54 | [Task](crypto \| masterkey \| SSS) Implement Database "Peek" and Shard Aggregation Logic | OPEN | [#54](https://github.com/openkcm/crypto/issues/54) |
| 55 | [Task](crypto \| masterkey \| SSS) Implement Secure Memory Zeroization for Shard Material | OPEN | [#55](https://github.com/openkcm/crypto/issues/55) |
| 56 | [Task](crypto \| masterkey \| SSS) Implement Shard Integrity and Anti-Replay Validation | OPEN | [#56](https://github.com/openkcm/crypto/issues/56) |
| 57 | [Task](crypto \| masterkey \| SSS) Implement SSS Provider Integration with Unified Interface | OPEN | [#57](https://github.com/openkcm/crypto/issues/57) |
| 58 | [Task](crypto \| masterkey \| SSS) Create Operational Documentation for Key Ceremony and Recovery | OPEN | [#58](https://github.com/openkcm/crypto/issues/58) |
| 59 | [Task](crypto \| masterkey \| SSS) Implement Database "Peek" and Shard Aggregation Logic | OPEN | [#59](https://github.com/openkcm/crypto/issues/59) |
| 33 | [Task](crypto \| master key) Define & document (future) disaster recovery procedure | CLOSED | [#33](https://github.com/openkcm/crypto/issues/33) |

---

## cmk

| # | Title | State | Link |
|---|-------|-------|------|
| 38 | [EPIC](cmk) Adapt CMK Backend for Apeiro Platform Mesh | OPEN | [#38](https://github.com/openkcm/cmk/issues/38) |

---

## cmk-ui

| # | Title | State | Link |
|---|-------|-------|------|
| 4 | [Epic] CMK-UI: Tenant & System Management | OPEN | [#4](https://github.com/openkcm/cmk-ui/issues/4) |
| 3 | [EPIC](cmk) CMK UI - Propagate the security context from Platform Mesh | OPEN | [#3](https://github.com/openkcm/cmk-ui/issues/3) |
| 2 | [EPIC](apeiro) OpenKCM CMK UI Integration into Platform Mesh Portal | OPEN | [#2](https://github.com/openkcm/cmk-ui/issues/2) |

---

## keystore-plugins

| # | Title | State | Link |
|---|-------|-------|------|
| 80 | [EPIC](plugins) Crypto Keystore Storage as plugin for L2-4 Key Material | OPEN | [#80](https://github.com/openkcm/keystore-plugins/issues/80) |
| 79 | [EPIC](plugins) CMK Keystore Plugin for L1 Key Operations using OpenBao Transit Keys | OPEN | [#79](https://github.com/openkcm/keystore-plugins/issues/79) |

---

## identity-management-plugins

| # | Title | State | Link |
|---|-------|-------|------|
| 62 | [EPIC](plugins) CMK Identity Management Plugins to retrieve the list of groups associated to the user | OPEN | [#62](https://github.com/openkcm/identity-management-plugins/issues/62) |

---

_Last updated: 2026-02-11_
