# OpenKCM Roadmap

This document provides an overview of the OpenKCM project roadmap across all repositories.

> **Note:** This roadmap is updated periodically. For real-time status, see the [OpenKCM Roadmap Board](https://github.com/orgs/openkcm/projects/2).

---

## Timeline Overview

```
2026
│
├─ Q1 (Jan–Mar) ──── ✅ FOUNDATION (COMPLETE)
│   ├── ✅ Krypton architecture investigation & low-level design
│   ├── ✅ KMIP protocol proof of concept
│   ├── ✅ Agent registration & communication layer (gRPC)
│   ├── ✅ Key hierarchy API (AnnounceKey, GetKeyChain)
│   ├── ✅ Encrypt / decrypt core (cryptor layer)
│   ├── ✅ CMK deployed into showroom environment
│   └── ✅ Architecture decisions finalized
│
├─ Q2 (Apr-Jun) ──── 🔄 KRYPTON CORE DEVELOPMENT (IN PROGRESS)
│   ├── KMIP Server implementation
│   ├── KeyChain & Key lifecycle (L2-L4)
│   ├── MasterKey management (Seal + Shamir SSS)
│   ├── Static MasterKey provider
│   ├── CLI tool (krypton command)
│   └── Krypton deployment on Showroom Gardener cluster (service running, visible — not full integration)
│
├─ Q2 (Apr-Jun) ──── 🔄 CMK INTEGRATION IN PLATFORM MESH (IN PROGRESS)
│   ├── CMK UI integrated in Platform (SSO)
│   ├── AWS KMS plugin working
│   ├── Tenant management complete
│   └── CMK Core deployment on Showroom Gardener cluster
│
└─ Q4 (Oct–Dec) ──── 🔒 PRODUCTION HARDENING
    ├── MasterKey management (Seal + Shamir SSS)
    ├── High availability & disaster recovery
    ├── mTLS hardening
    └── Kill switch & key revocation
```

| Milestone                 | Target Date | Description                                     | Status         |
| ------------------------- | ----------- | ----------------------------------------------- | -------------- |
| 🔬 **LLD Complete**       | Mar 2026    | Low-Level Design finalized, interfaces defined  | ✅ Done        |
| 🚀 **Showroom Deployment**      | Jun 2026    | Krypton deployed on Showroom Gardener cluster — service running and visible (deployment only, not full integration)  | 🔄 In Progress |
| 🎯 **Crypto Layer MVP**   | Aug 2026    | Production-ready KMIP server with multi-tenancy | Planned        |
| 🔗 **Full Chain (L1-L4)** | Nov 2026    | CMK + Krypton integrated end-to-end             | Planned        |

---

## Krypton — Crypto Execution Layer

### Epics

| # | Title | Quarter | Status |
|---|---|---|---|
| [#144](https://github.com/openkcm/krypton/issues/144) | Agent Registration & Communication Layer | Q1–Q2 | ✅ Done |
| [#145](https://github.com/openkcm/krypton/issues/145) | Key Hierarchy API — Tenant, Key, and Chain Management | Q1–Q2 | 🔄 In Progress |
| [#146](https://github.com/openkcm/krypton/issues/146) | Encrypt / Decrypt Core (Cryptor Layer) | Q1–Q2 | ✅ Done |
| [#61](https://github.com/openkcm/krypton/issues/61) | Crypto Core & Edge Services Using KMIP 1.4 | Q2 | 🔄 In Progress |
| [#78](https://github.com/openkcm/krypton/issues/78) | OpenKCM Krypton Showroom Demo | Q2 | 🔄 In Progress |
| [#60](https://github.com/openkcm/krypton/issues/60) | Internal Versioned Key (IVK) Management | Q3 | Planned |
| [#26](https://github.com/openkcm/krypton/issues/26) | Seal Mode Provider (multi-cloud + OpenBao) | Q3 | Planned |
| [#22](https://github.com/openkcm/krypton/issues/22) | MasterKey Management (Seal + Shamir SSS) | Q4 | Planned |
| [#27](https://github.com/openkcm/krypton/issues/27) | Shamir SSS Mode Provider | Q4 | Planned |

### Investigations

| # | Title | Status |
|---|---|---|
| [#68](https://github.com/openkcm/krypton/issues/68) | Krypton Layer — Investigation & Low-Level Design | ✅ Done |
| [#76](https://github.com/openkcm/krypton/issues/76) | OpenBao Plugin Technical Specifications | 🔄 In Progress |

---

## OpenKCM Controller — Platform Mesh Integration

| # | Title | Quarter | Status |
|---|---|---|---|
| [#1](https://github.com/openkcm/openkcm-controller/issues/1) | Tenant Management — OpenKCM Controller | Q2 | 🔄 In Progress |
| [#2](https://github.com/openkcm/openkcm-controller/issues/2) | Remote KCP Client & Kubeconfig Handling | Q3 | Planned |
| [#3](https://github.com/openkcm/openkcm-controller/issues/3) | Tenant Watcher via APIExport Virtual Workspace | Q3 | Planned |

---

## CMK UI — Account-Level Key Management

| # | Title | Quarter | Status |
|---|---|---|---|
| [#2](https://github.com/openkcm/cmk-ui/issues/2) | OpenKCM CMK UI Integration into Platform Mesh Portal | Q2 | 🔄 In Progress |
| [#3](https://github.com/openkcm/cmk-ui/issues/3) | Security Context Propagation from Platform Mesh | Q3 | Planned |

---

## Platform Mesh

| # | Title | Quarter | Status |
|---|---|---|---|
| [#1](https://github.com/openkcm/platform-mesh/issues/1) | OpenKCM Integration into Platform Mesh | Q2 | 🔄 In Progress |

---

## Keystore Plugins

| # | Title | Quarter | Status |
|---|---|---|---|
| [#79](https://github.com/openkcm/keystore-plugins/issues/79) | L1 Key Operations via OpenBao Transit Keys | Q2 | 🔄 In Progress |
| [#80](https://github.com/openkcm/keystore-plugins/issues/80) | Keystore Storage Plugin for L2–L4 Key Material | Q3 | Planned |

---

## Identity Management Plugins

| # | Title | Quarter | Status |
|---|---|---|---|
| [#62](https://github.com/openkcm/identity-management-plugins/issues/62) | Identity Management Plugin — Group Resolution | Q3 | Planned |

---

_Last updated: 2026-05-28_
