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
│   └── Krypton Integration in Showroom
│
├─ Q2 (Apr-Jun) ──── CMK INTEGRATION IN PLATFORM MESH
│   ├── Tenant management
│   └── CMK Core Deployment in Showroom
│
├─ Q3 (Jul-Sep) ──── 🎯 CRYPTO LAYER MVP (End of Summer)
│
├─ Q3 (Jul-Sep) ──── CMK DEVELOPMENTS
│   ├── Keystore plugin (OpenBao)
│   └── CMK UI adoption
│
├─ Q4 (Oct-Dec) ──── CMK INTEGRATION & HARDENING
│   ├── L1 (CMK) ↔ L2-L4 (Krypton) integration
│   ├── Seal/Auto-Unseal implementation
│   ├── HA & disaster recovery
│   ├── MongoDB KMIP integration validated
│   ├── Multi-tenant key isolation
│   ├── mTLS authentication
│   ├── In-memory + persistent storage
│   └── Production-ready Showroom deployment
| Milestone | Target Date | Description |
|-----------|-------------|-------------|
| 🔬 **LLD Complete** | Mar 2026 | Low-Level Design finalized, interfaces defined |
| 🚀 **Showroom Demo** | Jun 2026 | Krypton running on Platform Mesh with MongoDB |
| 🎯 **Crypto Layer MVP** | Aug 2026 | Production-ready KMIP server with multi-tenancy |
| 🔗 **Full Chain (L1-L4)** | Nov 2026 | CMK + Krypton integrated end-to-end |
```

---


## crypto layer: Krypton

| # | Title | State | Link |
|---|-------|-------|------|
| 68 | [EPIC](crypto) Krypton Layer - Investigation & Low-Level Design | OPEN | [#68](https://github.com/openkcm/krypton/issues/68) |
| 61 | [EPIC](crypto) Crypto Core & Edge Services Using KMIP 1.4 | OPEN | [#61](https://github.com/openkcm/krypton/issues/61) |
| 60 | [EPIC](crypto) Internal Versioned Key (IVK) Management (with Per-Version Algorithm Selection & Automatic L2.x Rotation) | OPEN | [#60](https://github.com/openkcm/krypton/issues/60) |



## openkcm-controller: Integration

| # | Title | State | Link |
|---|-------|-------|------|
| 1 | [EPIC](apeiro) Tenant Management: Remote KCP-Aware -> OpenKCM Controller | OPEN | [#1](https://github.com/openkcm/openkcm-controller/issues/1) |



## cmk backend: Adoption

| # | Title | State | Link |
|---|-------|-------|------|
| 38 | [EPIC](cmk) Adapt CMK Backend for Apeiro Platform Mesh | OPEN | [#38](https://github.com/openkcm/cmk/issues/38) |

| 39 | [EPIC](cmk) CMK Integration in Platform Mesh | OPEN | [#39](https://github.com/openkcm/cmk/issues/39) |


## cmk-ui: Adoption

| # | Title | State | Link |
|---|-------|-------|------|
| 4 | [Epic] CMK-UI: Tenant & System Management | OPEN | [#4](https://github.com/openkcm/cmk-ui/issues/4) |
| 3 | [EPIC](cmk) CMK UI - Propagate the security context from Platform Mesh | OPEN | [#3](https://github.com/openkcm/cmk-ui/issues/3) |
| 2 | [EPIC](apeiro) OpenKCM CMK UI Integration into Platform Mesh Portal | OPEN | [#2](https://github.com/openkcm/cmk-ui/issues/2) |


## keystore-plugins

| # | Title | State | Link |
|---|-------|-------|------|
| 80 | [EPIC](plugins) Crypto Keystore Storage as plugin for L2-4 Key Material | OPEN | [#80](https://github.com/openkcm/keystore-plugins/issues/80) |
| 79 | [EPIC](plugins) CMK Keystore Plugin for L1 Key Operations using OpenBao Transit Keys | OPEN | [#79](https://github.com/openkcm/keystore-plugins/issues/79) |


## identity-management-plugins

| # | Title | State | Link |
|---|-------|-------|------|
| 62 | [EPIC](plugins) CMK Identity Management Plugins to retrieve the list of groups associated to the user | OPEN | [#62](https://github.com/openkcm/identity-management-plugins/issues/62) |


_Last updated: 2026-02-11_
