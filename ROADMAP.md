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
│   ├── ✅ Key hierarchy API (AnnounceKey, GetKey, GetKeyChain, ListKeys)
│   ├── ✅ Cryptor package (AES-256-GCM, ChaCha20-Poly1305, Ed25519)
│   └── ✅ Architecture decisions finalized
│
├─ Q2/Q3 (Apr–Jul) ──── 🔄 KRYPTON CORE (IN PROGRESS)
│   ├── ✅ CLI tool (announce key, list keys, get key, get descendants)
│   ├── ✅ Vault abstraction layer (SQLite + OpenBao implementations)
│   ├── ✅ OpenBao keystore plugin (L1 key operations via Transit)
│   ├── ✅ KMIP server base (Get, GetAttributes)
│   ├── ✅ Key versioning model and store
│   ├── ✅ Key processor and version-aware key processor manager
│   ├── 🔄 Encrypt / decrypt core — IVK + MasterKey provider integration
│   ├── 🔄 KMIP Create, Activate operations (MongoDB integration)
│   └── 🔄 Krypton deployment on Showroom Gardener cluster
│
├─ Q3 (Jul–Sep) ──── 🎯 END-TO-END DEMO (Target: Sep 2026)
│   ├── KMIP full flow: Create → Activate → Get → MongoDB encrypts at rest
│   ├── L1 (OpenBao) → L2 → L3 → L4 key chain demonstrated end-to-end
│   ├── Key chain visible: tenant root → domain key → service key → DEK
│   └── Sovereignty guarantee demonstrated: platform never holds key material
│
├─ Q4 (Oct–Dec) ──── GOVERNANCE LAYER & PLATFORM MESH INTEGRATION
│   ├── Kill switch (soft — suspend with cascade)
│   ├── Four-eyes / multi-party approval for sensitive key operations
│   ├── Role model (Key Admin, Namespace Encryption Admin, Developer)
│   ├── OpenKCM Controller — Platform Mesh account-level integration
│   ├── L2 auto-provisioning per namespace on Platform Mesh
│   ├── Tenant lifecycle — soft delete with grace period
│   ├── MasterKey management (Seal + Shamir SSS)
│   ├── mTLS authentication between components
│   └── Production-ready Showroom deployment
│
└─ 2027 ──── ENTERPRISE FEATURES & HARDENING
    ├── BYOK / HYOK onboarding wizard (customer-facing L1 registration)
    ├── Key health dashboard and alerting
    ├── Kill switch dry run (blast radius simulation)
    ├── SIEM audit export (pluggable audit backends)
    ├── Key rotation — customer-configurable intervals and manual trigger
    ├── Multi-region deployment and geographic data residency UI
    ├── HA & disaster recovery
    └── Pluggable keystore selection UI (provider switching)
```

| Milestone | Target Date | Description | Status |
|---|---|---|---|
| 🔬 **LLD Complete** | Mar 2026 | Low-level design finalized, interfaces defined | ✅ Done |
| 🔑 **Key Hierarchy API** | Jun 2026 | Tenant, key, and chain management via gRPC | ✅ Done |
| 🔌 **OpenBao Integration** | Jul 2026 | L1 key operations via OpenBao Transit plugin | ✅ Done |
| 🚀 **Showroom Deployment** | Aug 2026 | Krypton running on Showroom Gardener cluster | 🔄 In Progress |
| 🎯 **End-to-End Demo** | Sep 2026 | Full L1→L4 chain with MongoDB encryption at rest | Planned |
| 🔗 **Platform Mesh Integration** | Dec 2026 | OpenKCM Controller + account-level governance | Planned |
| 🏢 **Enterprise Features** | 2027 | Kill switch dry run, SIEM export, health dashboard | Planned |

---

## Krypton — Crypto Execution Layer

### Epics

| # | Title | Quarter | Status |
|---|---|---|---|
| [#144](https://github.com/openkcm/krypton/issues/144) | Agent Registration & Communication Layer | Q1–Q2 | ✅ Done |
| [#145](https://github.com/openkcm/krypton/issues/145) | Key Hierarchy API — Tenant, Key, and Chain Management | Q1–Q2 | ✅ Done |
| [#146](https://github.com/openkcm/krypton/issues/146) | Encrypt / Decrypt Core (Cryptor Layer) | Q2–Q3 | 🔄 In Progress |
| [#61](https://github.com/openkcm/krypton/issues/61) | Crypto Core & Edge Services Using KMIP 1.4 | Q2–Q3 | 🔄 In Progress |
| [#78](https://github.com/openkcm/krypton/issues/78) | OpenKCM Krypton Showroom Demo | Q3 | 🔄 In Progress |
| [#60](https://github.com/openkcm/krypton/issues/60) | Internal Versioned Key (IVK) Management | Q3 | 🔄 In Progress |
| [#26](https://github.com/openkcm/krypton/issues/26) | Seal Mode Provider (multi-cloud + OpenBao) | Q4 | Planned |
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
| [#1](https://github.com/openkcm/openkcm-controller/issues/1) | Tenant Management — OpenKCM Controller | Q4 | 🔄 In Progress |
| [#2](https://github.com/openkcm/openkcm-controller/issues/2) | Remote KCP Client & Kubeconfig Handling | Q4 | Planned |
| [#3](https://github.com/openkcm/openkcm-controller/issues/3) | Tenant Watcher via APIExport Virtual Workspace | Q4 | Planned |

---

## CMK UI — Account-Level Key Management

| # | Title | Quarter | Status |
|---|---|---|---|
| [#2](https://github.com/openkcm/cmk-ui/issues/2) | OpenKCM UI Integration into Platform Mesh Portal | Q4 | 🔄 In Progress |
| [#3](https://github.com/openkcm/cmk-ui/issues/3) | Security Context Propagation from Platform Mesh | Q4 | Planned |

---

## Platform Mesh

| # | Title | Quarter | Status |
|---|---|---|---|
| [#1](https://github.com/openkcm/platform-mesh/issues/1) | OpenKCM Integration into Platform Mesh | Q4 | 🔄 In Progress |

---

## Keystore Plugins

| # | Title | Quarter | Status |
|---|---|---|---|
| [#79](https://github.com/openkcm/keystore-plugins/issues/79) | L1 Key Operations via OpenBao Transit Keys | Q2–Q3 | ✅ Done |
| [#80](https://github.com/openkcm/keystore-plugins/issues/80) | Keystore Storage Plugin for L2–L4 Key Material | Q4 | Planned |

---

## Identity Management Plugins

| # | Title | Quarter | Status |
|---|---|---|---|
| [#62](https://github.com/openkcm/identity-management-plugins/issues/62) | Identity Management Plugin — Group Resolution | Q4 | Planned |

---

_Last updated: 2026-07-21_
