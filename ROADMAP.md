# OpenKCM Roadmap

This document provides an overview of the OpenKCM project roadmap across all repositories.

> **Note:** This roadmap is updated periodically. For real-time status, see the [OpenKCM Roadmap Board](https://github.com/orgs/openkcm/projects/2).

---

## Timeline Overview

```
2026
│
├─ Q1 (Jan–Mar) ──── ✅ FOUNDATION (COMPLETE)
│   ├── ✅ Key management API — announce, list, get, and traverse key chains
│   ├── ✅ KMIP protocol support — industry-standard key retrieval for databases and services
│   ├── ✅ Pluggable keystore backend — swap key storage without changing application code
│   ├── ✅ OpenBao integration — first supported external keystore for customer root keys (L1)
│   └── ✅ mTLS authentication — secure communication between all OpenKCM components
│
├─ Q2/Q3 (Apr–Aug) ──── 🔄 ENCRYPTION OPERATIONS (IN PROGRESS)
│   ├── ✅ Key versioning — rotate keys without re-encrypting existing data
│   ├── ✅ KMIP Get and GetAttributes — services can retrieve and inspect keys via KMIP
│   ├── ✅ KMIP Activate — full key lifecycle management via KMIP protocol
│   ├── ✅ Multi-cloud MasterKey unsealing — AWS, GCP, Azure, OpenBao, PKCS#11 backends
│   ├── 🔄 Encrypt / decrypt operations — wrap and unwrap data encryption keys
│   ├── 🔄 KMIP Create — services can request new keys via KMIP (MongoDB integration)
│   └── 🔄 Showroom deployment — OpenKCM running on a live Gardener cluster
│
├─ Q3 (Sep 2026) ──── 🎯 END-TO-END DEMO
│   ├── MongoDB encrypts data at rest using keys from OpenKCM — full KMIP flow
│   ├── Customer registers their own root key (L1) — platform never holds it
│   ├── Full key chain visible: root key → domain key → service key → data key
│   ├── Kill switch demonstrated: customer disables root key → MongoDB instantly inaccessible
│   └── Live showroom demo — apeirora/showroom#180
│
├─ Q4 (Oct–Dec 2026) ──── CUSTOMER CONTROL & PLATFORM MESH
│   ├── Kill switch — customer can instantly revoke all data access with one action
│   ├── Soft suspension — pause encryption for a service without destroying keys
│   ├── Key rotation — customer-triggered rotation with zero downtime
│   ├── Four-eyes approval — sensitive key operations require multi-party sign-off
│   ├── Role-based access — Key Administrator, Service Encryption Admin, Developer
│   ├── Platform Mesh integration — enable OpenKCM from the marketplace per account
│   ├── Zero-touch encryption — services deployed on Platform Mesh get encryption automatically
│   ├── Region support — advertise available OpenKCM regions to Platform Mesh consumers
│   ├── Tenant lifecycle — safe account deletion with grace period before key cleanup
│   └── MasterKey management — Shamir Secret Sharing for secure operator key unsealing
│
└─ 2027 ──── ENTERPRISE READINESS
    ├── BYOK / HYOK onboarding — guided wizard for customers bringing their own keys
    ├── Kill switch dry run — preview which services would be affected before acting
    ├── Audit export — send key operation events to SIEM systems
    ├── Key health dashboard — visibility into key states, expiry, and rotation status
    ├── Multi-region data residency — deploy OpenKCM close to data, enforce regional boundaries
    ├── High availability & disaster recovery
    ├── Additional keystore integrations — HSM, AWS KMS, Azure Key Vault, Thales
    └── Service provider SDK — standardized integration for services offering encryption to customers
```

| Milestone | Target | Description | Status |
|---|---|---|---|
| ✅ **Key Management API** | Mar 2026 | Announce, list, get, and traverse key chains | ✅ Done |
| ✅ **OpenBao Integration** | Jul 2026 | Customer root keys via OpenBao Transit | ✅ Done |
| ✅ **KMIP Protocol** | Aug 2026 | Industry-standard key retrieval for databases | ✅ Done |
| 🔄 **Showroom Deployment** | Aug 2026 | OpenKCM live on Showroom Gardener cluster | 🔄 In Progress |
| 🎯 **End-to-End Demo** | Sep 2026 | MongoDB encryption with customer-controlled keys | Planned |
| 🔗 **Platform Mesh Integration** | Dec 2026 | Marketplace enablement, zero-touch encryption | Planned |
| 🏢 **Enterprise Readiness** | 2027 | Audit export, BYOK wizard, multi-region, HA | Planned |

---

## Krypton — Crypto Execution Layer

### Epics

| # | Title | Quarter | Status |
|---|---|---|---|
| [#144](https://github.com/openkcm/krypton/issues/144) | Key Management API — Tenant, Key, and Chain Operations | Q1–Q2 | ✅ Done |
| [#145](https://github.com/openkcm/krypton/issues/145) | Pluggable Keystore Backend | Q1–Q2 | ✅ Done |
| [#146](https://github.com/openkcm/krypton/issues/146) | Encrypt / Decrypt Operations | Q2–Q3 | 🔄 In Progress |
| [#61](https://github.com/openkcm/krypton/issues/61) | KMIP Protocol — Create, Activate, Get, Wrap, Unwrap | Q2–Q3 | 🔄 In Progress |
| [#60](https://github.com/openkcm/krypton/issues/60) | Key Rotation with Zero Downtime | Q3 | 🔄 In Progress |
| [#78](https://github.com/openkcm/krypton/issues/78) | Showroom Demo — MongoDB Encryption End-to-End | Q3 | 🔄 In Progress |
| [apeirora/showroom#180](https://github.com/apeirora/showroom/issues/180) | Encrypted File Management Demo | Q3–Q4 | Planned |
| [#187](https://github.com/openkcm/krypton/issues/187) | Kill Switch — Instant Revocation of All Data Access | Q4 | Planned |
| [#189](https://github.com/openkcm/krypton/issues/189) | Customer-Triggered Key Rotation | Q4 | Planned |
| [#188](https://github.com/openkcm/krypton/issues/188) | Kill Switch Dry Run — Blast Radius Preview | 2027 | Planned |
| [#26](https://github.com/openkcm/krypton/issues/26) | Multi-Cloud MasterKey Unsealing | Q4 | Planned |
| [#22](https://github.com/openkcm/krypton/issues/22) | MasterKey Management — Shamir Secret Sharing | Q4 | Planned |

---

## Platform Mesh Integration

| # | Title | Quarter | Status |
|---|---|---|---|
| [#1](https://github.com/openkcm/openkcm-controller/issues/1) | OpenKCM Controller — Marketplace Enablement per Account | Q4 | 🔄 In Progress |
| [#2](https://github.com/openkcm/openkcm-controller/issues/2) | Platform Mesh Cluster Connectivity | Q4 | Planned |
| [#3](https://github.com/openkcm/openkcm-controller/issues/3) | Zero-Touch Encryption — Auto-provision Keys on Service Deployment | Q4 | Planned |
| [#5](https://github.com/openkcm/openkcm-controller/issues/5) | Tenant Lifecycle — Safe Account Deletion with Grace Period | Q4 | Planned |
| [#1](https://github.com/openkcm/platform-mesh/issues/1) | OpenKCM Integration into Platform Mesh Marketplace | Q4 | 🔄 In Progress |

---

## Customer UI — Key Governance

| # | Title | Quarter | Status |
|---|---|---|---|
| [#2](https://github.com/openkcm/cmk-ui/issues/2) | OpenKCM UI in Platform Mesh Portal — L1 Key Registration & Kill Switch | Q4 | 🔄 In Progress |
| [#3](https://github.com/openkcm/cmk-ui/issues/3) | Role-Based Access in UI | Q4 | Planned |

---

## Keystore Plugins

| # | Title | Quarter | Status |
|---|---|---|---|
| [#79](https://github.com/openkcm/keystore-plugins/issues/79) | OpenBao Transit — Customer Root Key Operations | Q2–Q3 | ✅ Done |
| [#80](https://github.com/openkcm/keystore-plugins/issues/80) | Pluggable Storage Backend for Service and Data Keys | Q4 | Planned |

---

## Identity & Access

| # | Title | Quarter | Status |
|---|---|---|---|
| [#62](https://github.com/openkcm/identity-management-plugins/issues/62) | Group-Based Access Control for Key Operations | Q4 | Planned |

---

_Last updated: 2026-08-20_
