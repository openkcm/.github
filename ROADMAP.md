# OpenKCM Roadmap

This document provides an overview of all tracked issues across OpenKCM repositories.

> **Note:** This is the current roadmap and will be updated periodically. For the most recent tasks and issues, please check our [GitHub Project Board](https://github.com/orgs/openkcm/projects).

---

## 📅 Timeline Overview

```
2026
│
├─ Q1 (Jan-Mar) ──── ✅ INVESTIGATION & DESIGN (COMPLETE)
│   ├── ✅ Low-Level Design (LLD) for Krypton
│   ├── ✅ KMIP Protocol POC
│   ├── ✅ Architecture decisions finalized
│   ├── ✅ CMK Layer v0.1.0 → v0.7.0 (16 releases)
│   ├── ✅ CMK UI v0.0.1 → v0.0.5 (first public release)
│   ├── ✅ Orbital v0.4.0 → v0.5.1
│   └── ✅ Plugin architecture redesigned (gRPC → Go interfaces)
│
├─ Q2 (Apr-Jun) ──── 🔄 KRYPTON CORE DEVELOPMENT (IN PROGRESS)
│   ├── KMIP Server implementation
│   ├── KeyChain & Key lifecycle (L2-L4)
│   ├── MasterKey management (Seal + Shamir SSS)
│   ├── Static MasterKey provider
│   ├── CLI tool (krypton command)
│   └── Krypton Integration in Showroom
│
├─ Q2 (Apr-Jun) ──── 🔄 CMK INTEGRATION IN PLATFORM MESH (IN PROGRESS)
│   ├── CMK UI integrated in Platform (SSO)
│   ├── AWS KMS plugin working
│   ├── Tenant management complete
│   └── CMK Core Deployment in Showroom
│
├─ Q3 (Jul-Sep) ──── 🎯 CRYPTO LAYER MVP (End of Summer)
│   ├── Krypton KMIP + crypto ops production-ready
│   ├── Keystore plugin (OpenBao)
│   └── CMK UI adoption finalized
│
├─ Q4 (Oct-Dec) ──── CMK-KRYPTON INTEGRATION & HARDENING
│   ├── L1 (CMK) ↔ L2-L4 (Krypton) integration
│   ├── Seal/Auto-Unseal implementation
│   ├── HA & disaster recovery
│   ├── MongoDB KMIP integration validated
│   ├── Multi-tenant key isolation
│   ├── mTLS authentication
│   ├── In-memory + persistent storage
│   └── Production-ready Showroom deployment
```

| Milestone                 | Target Date | Description                                     | Status         |
| ------------------------- | ----------- | ----------------------------------------------- | -------------- |
| 🔬 **LLD Complete**       | Mar 2026    | Low-Level Design finalized, interfaces defined  | ✅ Done        |
| 🚀 **Showroom Demo**      | Jun 2026    | Krypton running on Platform Mesh with MongoDB   | 🔄 In Progress |
| 🎯 **Crypto Layer MVP**   | Aug 2026    | Production-ready KMIP server with multi-tenancy | Planned        |
| 🔗 **Full Chain (L1-L4)** | Nov 2026    | CMK + Krypton integrated end-to-end             | Planned        |

---

## Crypto Layer: Krypton

### Epics

| #   | Title                                                                             | State | Link                                                |
| --- | --------------------------------------------------------------------------------- | ----- | --------------------------------------------------- |
| 22  | [EPIC] MasterKey Management (Seal + Shamir SSS)                                   | OPEN  | [#22](https://github.com/openkcm/krypton/issues/22) |
| 23  | [EPIC] Internal Versioned Key (IVK) Management                                    | OPEN  | [#23](https://github.com/openkcm/krypton/issues/23) |
| 26  | [EPIC] Implement Seal mode provider (multi-cloud + OpenBao)                       | OPEN  | [#26](https://github.com/openkcm/krypton/issues/26) |
| 27  | [EPIC] Implement Shamir SSS mode provider                                         | OPEN  | [#27](https://github.com/openkcm/krypton/issues/27) |
| 60  | [EPIC] IVK Management (Per-Version Algorithm Selection & Automatic L2.x Rotation) | OPEN  | [#60](https://github.com/openkcm/krypton/issues/60) |
| 61  | [EPIC] Crypto Core & Edge Services Using KMIP 1.4                                 | OPEN  | [#61](https://github.com/openkcm/krypton/issues/61) |
| 68  | [Investigation] Krypton Layer - Investigation & Low-Level Design                  | ✅ DONE | [#68](https://github.com/openkcm/krypton/issues/68) |

### MasterKey: Seal Providers (Q2 — Epic #26)

| #   | Title                                         | Link                                                |
| --- | --------------------------------------------- | --------------------------------------------------- |
| 34  | OpenBao/Vault provider                        | [#34](https://github.com/openkcm/krypton/issues/34) |
| 35  | AWS KMS provider                              | [#35](https://github.com/openkcm/krypton/issues/35) |
| 36  | GCP KMS provider                              | [#36](https://github.com/openkcm/krypton/issues/36) |
| 37  | Azure Key Vault provider                      | [#37](https://github.com/openkcm/krypton/issues/37) |
| 38  | Common Seal utilities & patterns              | [#38](https://github.com/openkcm/krypton/issues/38) |
| 39  | Configuration parsing & provider factory      | [#39](https://github.com/openkcm/krypton/issues/39) |
| 40  | IVK layer integration & algorithm agnosticism | [#40](https://github.com/openkcm/krypton/issues/40) |
| 41  | Security hardening & zeroization              | [#41](https://github.com/openkcm/krypton/issues/41) |
| 42  | Comprehensive testing suite                   | [#42](https://github.com/openkcm/krypton/issues/42) |
| 43  | Documentation & operational guides            | [#43](https://github.com/openkcm/krypton/issues/43) |

### MasterKey: Shamir SSS (Q2-Q3 — Epic #27)

| #   | Title                                                          | Link                                                |
| --- | -------------------------------------------------------------- | --------------------------------------------------- |
| 44  | Implement SSS Generator CLI Tool                               | [#44](https://github.com/openkcm/krypton/issues/44) |
| 45  | Shard Encryption Workflow (KMS/HSM Integration)                | [#45](https://github.com/openkcm/krypton/issues/45) |
| 47  | Design and Implement Shard Database Persistence Layer          | [#47](https://github.com/openkcm/krypton/issues/47) |
| 48  | Implement GF(256) Math Engine for Lagrange Interpolation       | [#48](https://github.com/openkcm/krypton/issues/48) |
| 49  | Implement AWS KMS Decryption Client                            | [#49](https://github.com/openkcm/krypton/issues/49) |
| 50  | Implement GCP KMS Decryption Client                            | [#50](https://github.com/openkcm/krypton/issues/50) |
| 51  | Implement HashiCorp/OpenBao Vault Decryption Client            | [#51](https://github.com/openkcm/krypton/issues/51) |
| 52  | Implement HSM (PKCS#11) Decryption Client                      | [#52](https://github.com/openkcm/krypton/issues/52) |
| 53  | Implement mTLS-backed REST Decryption Client                   | [#53](https://github.com/openkcm/krypton/issues/53) |
| 54  | Implement Database "Peek" and Shard Aggregation Logic          | [#54](https://github.com/openkcm/krypton/issues/54) |
| 55  | Implement Secure Memory Zeroization for Shard Material         | [#55](https://github.com/openkcm/krypton/issues/55) |
| 56  | Implement Shard Integrity and Anti-Replay Validation           | [#56](https://github.com/openkcm/krypton/issues/56) |
| 57  | Implement SSS Provider Integration with Unified Interface      | [#57](https://github.com/openkcm/krypton/issues/57) |
| 58  | Create Operational Documentation for Key Ceremony and Recovery | [#58](https://github.com/openkcm/krypton/issues/58) |

### MasterKey: Core (Q2 — Epic #22)

| #   | Title                                            | Link                                                |
| --- | ------------------------------------------------ | --------------------------------------------------- |
| 24  | Design unified MasterKey abstraction & interface | [#24](https://github.com/openkcm/krypton/issues/24) |
| 25  | Implement core in-memory MasterKey holder        | [#25](https://github.com/openkcm/krypton/issues/25) |
| 29  | Integrate MasterKey provider into IVK system     | [#29](https://github.com/openkcm/krypton/issues/29) |

### Showroom & Demos (Q2)

| #   | Title                                          | Link                                                |
| --- | ---------------------------------------------- | --------------------------------------------------- |
| 78  | OpenKCM Krypton Showroom Demo                  | [#78](https://github.com/openkcm/krypton/issues/78) |
| 80  | Krypton: Business Story For Platform Mesh Demo | [#80](https://github.com/openkcm/krypton/issues/80) |
| 82  | Demo of Business Case                          | [#82](https://github.com/openkcm/krypton/issues/82) |

### Investigation

| #   | Title                                               | Link                                                |
| --- | --------------------------------------------------- | --------------------------------------------------- |
| 76  | OpenBao Plugin Technical Specifications for OpenKCM | [#76](https://github.com/openkcm/krypton/issues/76) |

---

## OpenKCM Controller: Integration

| #   | Title                                                            | State | Link                                                         |
| --- | ---------------------------------------------------------------- | ----- | ------------------------------------------------------------ |
| 1   | [EPIC] Tenant Management: Remote KCP-Aware -> OpenKCM Controller | OPEN  | [#1](https://github.com/openkcm/openkcm-controller/issues/1) |
| 2   | [EPIC] Remote KCP client & kubeconfig handling                   | OPEN  | [#2](https://github.com/openkcm/openkcm-controller/issues/2) |
| 3   | [EPIC] Tenant watcher / informer via APIExport virtual workspace | OPEN  | [#3](https://github.com/openkcm/openkcm-controller/issues/3) |

---

## CMK Backend: Adoption

### Epics

| #   | Title                                             | State | Link                                            |
| --- | ------------------------------------------------- | ----- | ----------------------------------------------- |
| 38  | [EPIC] Adapt CMK Backend for Apeiro Platform Mesh | OPEN  | [#38](https://github.com/openkcm/cmk/issues/38) |

### Stories & Tasks

| #   | Title                                                                | Link                                              |
| --- | -------------------------------------------------------------------- | ------------------------------------------------- |
| 231 | bug: CMK UI – Empty Landing Page After Login                         | [#231](https://github.com/openkcm/cmk/issues/231) |
| 154 | feature: Grant KeyAdmin the permission to access tenant info         | [#154](https://github.com/openkcm/cmk/issues/154) |
| 153 | [Task] Allow loading groups from IAM on ClientData verification time | [#153](https://github.com/openkcm/cmk/issues/153) |
| 148 | feature: Order systems by identifier ascending                       | [#148](https://github.com/openkcm/cmk/issues/148) |
| 106 | bug: Change keystores resource type                                  | [#106](https://github.com/openkcm/cmk/issues/106) |
| 101 | feature: Return tenant Role                                          | [#101](https://github.com/openkcm/cmk/issues/101) |
| 83  | feature: Improve approved email                                      | [#83](https://github.com/openkcm/cmk/issues/83)   |
| 80  | feat: Move the scim plugin as builtin plugin into cmk source code    | [#80](https://github.com/openkcm/cmk/issues/80)   |
| 42  | feature: Enable authz in unit test middleware                        | [#42](https://github.com/openkcm/cmk/issues/42)   |

---

## CMK UI: Adoption

### Epics

| #   | Title                                                             | State | Link                                             |
| --- | ----------------------------------------------------------------- | ----- | ------------------------------------------------ |
| 2   | [EPIC] OpenKCM CMK UI Integration into Platform Mesh Portal       | OPEN  | [#2](https://github.com/openkcm/cmk-ui/issues/2) |
| 3   | [EPIC] CMK UI - Propagate the security context from Platform Mesh | OPEN  | [#3](https://github.com/openkcm/cmk-ui/issues/3) |
| 4   | [Epic] CMK-UI: Tenant & System Management                         | OPEN  | [#4](https://github.com/openkcm/cmk-ui/issues/4) |

### Stories & Tasks

| #   | Title                                                                       | Link                                               |
| --- | --------------------------------------------------------------------------- | -------------------------------------------------- |
| 76  | feature: Include tenantID in logout API call                                | [#76](https://github.com/openkcm/cmk-ui/issues/76) |
| 73  | feature: Re-enable BYOK feature                                             | [#73](https://github.com/openkcm/cmk-ui/issues/73) |
| 72  | bug: Error pages should be customizable for Open Source                     | [#72](https://github.com/openkcm/cmk-ui/issues/72) |
| 65  | bug: Fix app initialisation race condition on tenants and userInfo API call | [#65](https://github.com/openkcm/cmk-ui/issues/65) |
| 62  | feature: Add Fortanix functionality to Key Creation                         | [#62](https://github.com/openkcm/cmk-ui/issues/62) |
| 39  | feature: Add helm chart building                                            | [#39](https://github.com/openkcm/cmk-ui/issues/39) |
| 35  | feature: Fix Multiple login attempt-infinite loop issue                     | [#35](https://github.com/openkcm/cmk-ui/issues/35) |
| 32  | feature: Update mock api                                                    | [#32](https://github.com/openkcm/cmk-ui/issues/32) |
| 30  | feature: Add error details to failed system                                 | [#30](https://github.com/openkcm/cmk-ui/issues/30) |
| 24  | feature: Add workflows settings                                             | [#24](https://github.com/openkcm/cmk-ui/issues/24) |
| 22  | feature: Add editing of iam identifier                                      | [#22](https://github.com/openkcm/cmk-ui/issues/22) |
| 20  | feature: Renable tenant dropdown                                            | [#20](https://github.com/openkcm/cmk-ui/issues/20) |
| 17  | feature: Add loader pre auth                                                | [#17](https://github.com/openkcm/cmk-ui/issues/17) |
| 14  | feature: CMK-UI: Session Logout                                             | [#14](https://github.com/openkcm/cmk-ui/issues/14) |
| 9   | feature: CMK-UI: Enable key config switch for Systems                       | [#9](https://github.com/openkcm/cmk-ui/issues/9)   |

---

## Platform Mesh: Integration

| #   | Title                                                                 | State | Link                                                    |
| --- | --------------------------------------------------------------------- | ----- | ------------------------------------------------------- |
| 1   | [EPIC] OpenKCM (Key Chain Manager) integration into the Platform Mesh | OPEN  | [#1](https://github.com/openkcm/platform-mesh/issues/1) |

---

## Keystore Plugins

| #   | Title                                                                       | State | Link                                                         |
| --- | --------------------------------------------------------------------------- | ----- | ------------------------------------------------------------ |
| 79  | [EPIC] CMK Keystore Plugin for L1 Key Operations using OpenBao Transit Keys | OPEN  | [#79](https://github.com/openkcm/keystore-plugins/issues/79) |
| 80  | [EPIC] Crypto Keystore Storage as plugin for L2-4 Key Material              | OPEN  | [#80](https://github.com/openkcm/keystore-plugins/issues/80) |

---

## Identity Management Plugins

| #   | Title                                                                                        | State | Link                                                                    |
| --- | -------------------------------------------------------------------------------------------- | ----- | ----------------------------------------------------------------------- |
| 62  | [EPIC] CMK Identity Management Plugins to retrieve the list of groups associated to the user | OPEN  | [#62](https://github.com/openkcm/identity-management-plugins/issues/62) |

---

## Supporting Components

The following repositories have no open epics/feature issues — they are stable and maintained:

| Repository                                                    | Latest Version | Notes                  |
| ------------------------------------------------------------- | -------------- | ---------------------- |
| [orbital](https://github.com/openkcm/orbital)                 | v0.5.1         | Event engine — stable  |
| [registry](https://github.com/openkcm/registry)               | Active         | Tenant registry        |
| [session-manager](https://github.com/openkcm/session-manager) | Active         | Session handling       |
| [extauthz](https://github.com/openkcm/extauthz)               | Active         | External authorization |
| [checker](https://github.com/openkcm/checker)                 | v0.3.1         | Operational insights   |
| [common-sdk](https://github.com/openkcm/common-sdk)           | v1.14.1        | Shared Go SDK          |
| [api-sdk](https://github.com/openkcm/api-sdk)                 | v0.16.0        | API client SDK         |
| [plugin-sdk](https://github.com/openkcm/plugin-sdk)           | v0.10.2        | Plugin interface SDK   |

_Last updated: 2026-04-17_
