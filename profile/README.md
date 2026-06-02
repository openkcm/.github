<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->

# Welcome to the Open Key Chain Manager (OpenKCM)

👋 Welcome to the official [OpenKCM](https://openkcm.io/). We are part of ApeiroRA which is an Important Project of Common European Interest.

## 🔐 What Is OpenKCM?

**OpenKCM (Open Key Chain Manager)** is an open-source, vendor-neutral key management system built on the [OASIS KMIP](https://www.oasis-open.org/committees/kmip/) standard. It gives organizations full control over their encryption keys — without locking them into a single cloud provider.

OpenKCM consists of two layers:

- **CMK (Customer Managed Keys)** — The management and control plane. It handles tenant onboarding, key lifecycle operations (enable, rotate, disable, delete), policy enforcement, and end-to-end audit logging.
- **Krypton** — The cryptographic execution layer. It manages the full key hierarchy (L1 → L2 → L3 → L4/DEK), performs sub-millisecond encryption at the edge via a split-execution architecture, and connects to any external root key provider (AWS KMS, Azure Key Vault, Google Cloud KMS, Thales HSM, OpenBao, and more).

### Key Capabilities

| Capability                   | Description                                                                                                                           |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| **KMIP Standard**            | No proprietary APIs — any KMIP-compatible database (MongoDB, MariaDB, VMware) integrates with zero code changes                       |
| **Flexible Key Hierarchy**   | Define your own keychain depth — from a two-level startup setup to a deep, geographically partitioned enterprise hierarchy            |
| **Customer Key Sovereignty** | The customer's root key (L1) never leaves their own vault — Krypton holds a reference, not the key                                    |
| **Edge Performance**         | Krypton Gateway runs as a local sidecar, delivering sub-millisecond encrypt/decrypt without upstream round-trips for every operation  |
| **Top-Down Revocation**      | Revoke a key at any level — everything below becomes instantly unreadable. The customer's "Red Button"                                |
| **Provider-Agnostic L1**     | Switch root key providers (cloud KMS, HSM, open-source vault) at any time — no re-encryption, no downtime                             |
| **Zero-Downtime Rotation**   | Lazy re-wrapping via Internal Versioned Keys (IVK) — no batch jobs, no maintenance windows                                            |
| **FIPS 140-2/3 Compliance**  | NIST-approved algorithms only (AES-256-GCM, RSA-OAEP, HKDF) — no fallbacks                                                            |
| **End-to-End Audit Logging** | Every key operation logged with a correlation ID across the full chain — SIEM-ready, regulation-compliant (DORA, NIS2, PCI-DSS, GDPR) |
| **Keystore Models**          | Provider Managed, BYOK, or HYOK (Hold Your Own Key — recommended)                                                                     |

### Who Is It For?

- **Platform engineers** who need to encrypt data at rest across multiple services without building a custom KMS
- **Enterprise architects** designing multi-region, multi-department key hierarchies with data residency requirements
- **Regulated industries** (banking, healthcare, defense, public sector) that require FIPS compliance, audit trails, and cryptographic key sovereignty
- **Organizations seeking digital sovereignty** — no dependency on any single cloud provider, open-source, auditable

## 🌐 ApeiroRA?

ApeiroRA is a reference blueprint for an open, flexible, secure, and compliant next-generation cloud-edge continuum and therefore a key contribution to IPCEI-CIS. At a high level, the projects of ApeiroRA allow users to provider-agnostically fetch, request and consume services, and for service providers to describe, offer and provision their services.

By being open source, ApeiroRA provides a cross-border spillover effect, solidifying the foundation and future of the project.

Learn more about ApeiroRA by checking out the official website at https://apeirora.eu/.

## 👥 Get Involved

We welcome contributions of all kinds, from code to documentation, testing, and design. If you're interested in getting involved, check out our open issues.
You can have look at our current road map to have a better overview of our planned features: [Road Map](https://github.com/openkcm/.github/blob/main/ROADMAP.md)

## 🌈 Code of Conduct

To facilitate a nice environment for all, check out [our Code of Conduct](https://github.com/openkcm/.github/blob/main/CODE_OF_CONDUCT.md).

## 👩‍💻 How to Start

You can try out OpenKCM by following our documentation. We are actively developing both the CMK control plane and the Krypton crypto layer. Check out the documentation for architecture decisions, setup instructions, and integration guides.

- [Documentation](https://github.com/openkcm/documentation) — Architecture Decision Records (ADRs), use cases, business case, and developer guides
- [Road Map](https://github.com/openkcm/.github/blob/main/ROADMAP.md) — Planned features and milestones

### Architecture at a Glance

```
Customer's HSM / Cloud KMS (L1 — root key, never leaves customer's vault)
  └─ Krypton Core (regional — L2/L3 key wrapping)
       └─ Krypton Gateway (edge sidecar — L4/DEK operations, sub-ms latency)
            └─ Application (MongoDB, PostgreSQL, etc. — connects via KMIP)
```

### Current Focus Areas

- **CMK Control Plane** — Tenant onboarding, key lifecycle (ENABLE / ROTATE / DISABLE / DELETE), policy enforcement, audit logging
- **Krypton Crypto Layer** — Internal Versioned Key (IVK) management, algorithm-agnostic encryption, split-execution architecture
- **Keystore Plugins** — Extensible plugin interface for root key providers (AWS KMS, GCP KMS, Azure Key Vault, Thales Luna HSM, Securosys HSM, OpenBao)
- **Identity Management** — Multi-tenant isolation with secure identity propagation (mTLS, OIDC)
- **Platform Mesh Integration** — Seamless integration with the Apeiro Platform Mesh for multi-tenant key management

<p align="center"><img alt="Bundesministerium für Wirtschaft und Energie (BMWE)-EU funding logo" src="https://apeirora.eu/assets/img/BMWK-EU.png" width="400"/></p>
