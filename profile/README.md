<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->

# Welcome to the Open Key Chain Manager (OpenKCM)

👋 Welcome to the official OpenKCM. We are part of ApeiroRA which is an Important Project of Common European Interest.

## 🌐 ApeiroRA?

ApeiroRA is a reference blueprint for an open, flexible, secure, and compliant next-generation cloud-edge continuum and therefore a key contribution to IPCEI-CIS. At a high level, the projects of ApeiroRA allow users to provider-agnostically fetch, request and consume services, and for service providers to describe, offer and provision their services.

By being open source, ApeiroRA provides a cross-border spillover effect, solidifying the foundation and future of the project.

Learn more about ApeiroRA by checking out the official website at https://apeirora.eu/.

## 👥 Get Involved

We welcome contributions of all kinds, from code to documentation, testing, and design. If you're interested in getting involved, check out our open issues.
You can have look at our current road map to have a better overview of our planned features: [Road Map](https://github.com/openkcm/.github/blob/main/ROADMAP.md)

## 🌈 Code of Conduct

To facilitate a nice environment for all, check out [our Code of Conduct](https://github.com/openkcm/.github/blob/main/CODE_OF_CONDUCT.md).

## 👩‍💻 Useful Resources

- [Documentation](https://github.com/openkcm/documentation) - Architecture Decision Records (ADRs), use cases, and developer guides.

### Current Use Cases

OpenKCM provides cryptographic key management capabilities for cloud-native environments. Our current focus areas include:

- **L1 Key Operations** - Customer Master Key (CMK) operations including key creation, rotation, and lifecycle management via OpenBao Transit Keys
- **Crypto Layer (Krypton)** - Internal Versioned Key (IVK) management with algorithm-agnostic encryption and automatic key rotation
- **Tenant & System Management** - Multi-tenant isolation with secure identity propagation
- **Plugin Architecture** - Extensible keystore and identity management plugins for various backend integrations (AWS KMS, GCP KMS, Azure Key Vault, HSM/PKCS#11)
- **Platform Mesh Integration** - Seamless integration with the Apeiro Platform Mesh for multi-tenant key management
