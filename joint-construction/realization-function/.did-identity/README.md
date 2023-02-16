---
description: DID Introduction
---

# .DID identity

DID, or Distributed Digital Identity. Compared with the traditional PKI (Public Key Infrastructure) based identity system, the DID digital identity system based on blockchain has the following advantages: it guarantees the authenticity and trustworthiness of data, protects the privacy and security of users, and is highly portable.

De-centralization: based on blockchain, it avoids the control of identity data by a single centralized authority.

Autonomous control of identity: Based on DPKI (Distributed Public Key Infrastructure), each user's identity is not controlled by a trusted third party, but by its owner, and individuals can manage their own identities.

Trusted data exchange: The data related to the identity is anchored on the blockchain, and the authentication process does not depend on the user who provided the identity.

A user's DID digital identity consists of three components: a DID identifier, a DID document, and verifiable credentials. Each DID must have a unique DID document, but can have an unlimited number of verifiable credentials.

DID Identity: The digital identity is identified by the DID, so the DID identity should be unique within the application and self-discoverable across applications. \_id", and the unique number identifier "account\_address".

DID document: The DID document is used to describe the characteristics of the digital identity and has a one-to-one correspondence with the DID identifier; the DID document records the account public key, the account status, and the authorized management account, and provides extensible fields for flexible configuration by the user with business scenarios. The authentication behavior of the transactions related to digital identity services will be based on the public key in the DID document.

Verifiable credentials: Verifiable credentials are used to describe the real-world identity attributes of a digital identity holder, which will record information such as the issuer, expiration date, and the attributes proven. The verifiable credentials are issued by an authority, and a digital identity can have a variable number of verifiable credentials.

Illustration of DID account structure

<mark style="color:blue;">**Account Schematic**</mark>

In particular, "verifiable credential" is the most important application value. Verifiable credentials can be understood as a "pass" that A gives to B, so B can access A with this "pass", which is a kind of proof and recognition. A DID account can hold verifiable credentials from multiple applications to achieve unified account login, thus avoiding duplicate application account registration in different platforms. In addition, verifiable credentials can also be used for process proof, such as the whole process of a product from component to production, then to quality inspection and sales, etc. Trusted credentials can be issued by the corresponding organization, so as to achieve credible traceability and credible tracking through the whole process of trusted authorization.
