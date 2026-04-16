---
id: "T3S-DOC-040-000"
urn: "urn:t3s:v0.2.1-alpha:root:control:h:[HASH_RESERVED]"
type: "t3s:root"
plane: "t3s:control"
root: "000_system"
domain: "integrity"
title: "Access and Integrity Anchor"
objective: "Define the cryptographic and procedural requirements for ensuring the integrity of the T3S framework."
description: "The authoritative anchor for identity verification, commit signing, provenance validation, and non-repudiation logic."
status: "draft"
version: "0.2.1-alpha"
steward: "urn:t3s:v0.2.1:steward:h:dab0d2c9622d"
criticality: "tier-1"
liability: "high"
sovereignty: "sovereign"
authority: 100
classification: "public"
license: "Apache-2.0"
copyright: "Copyright © 2026 The Systemic Stewardship Standards Initiative (T3SI)"
references:
  - t3s:predicate: "t3s:dependency"
    target: "urn:t3s:v0.2.1-alpha:branch:control:h:[HASH_RESERVED]"
    description: "Aligns access and integrity enforcement with the 010 Mandates."
  - t3s:predicate: "t3s:dependency"
    target: "urn:t3s:v0.2.1-alpha:branch:control:h:[HASH_RESERVED]"
    description: "Depends on the Persona and Identity Anchor (030-000) for steward and service identity semantics."
t3s:integrity: "sha256:[HASH_RESERVED]"
---

# 040-000 Access and Integrity Anchor

## 040-000::010 Purpose
This anchor defines the cryptographic and procedural requirements for ensuring the integrity of the T3S framework.  
It establishes the **Technical Guardrails** for identity verification, commit signing, provenance validation, and non-repudiation, aligning the repository with ITIL 4 **Information Security Management** and the constitutional mandates defined in **010-001**.

Integrity governance supports:

- Objective C — Digital Sovereignty & Verifiable AI  
- Objective G — Provenance Integrity & Stewardship Accountability  
- Objective H — Forensic Persistence & Lineage Tracking  
- Objective K — Deterministic Enforcement & Smart Gates  
- Objective N — Recursive Self-Correction & Entropy Management

## 040-000::020 Cryptographic Root of Trust
To ensure the **Markov Blanket** remains closed to unauthorized or anonymous influence, the following standards are mandated.

### 040-000::021 Commit Signing (Non-Repudiation)
- **Requirement:** All commits MUST be signed using a GPG or SSH key.  
- **Verification:** Identities are validated via the functional hash embedded in the Steward URN.  
- **Registry:** Public keys MUST be indexed in the `040.100-001` Trusted Keys Registry.  
- **Enforcement:** `060` automation pipelines SHALL reject any commit whose signature does not match the fingerprint associated with the Steward’s identity hash.

Commit signing ensures that all modifications maintain verifiable `t3s:provenance` and `t3s:lineage`.

### 040-000::022 Identity Mapping
- **Identifier:** Each contributor MUST be associated with a unique persistent URN  
  `urn:t3s:v0.2.1:steward:h:<hash>`.  
- **Persistence:** The `h:<hash>` suffix ensures identity remains static across path changes, repository migrations, or VFS remounts.  
- **Traceability:** All actions performed by an identity MUST be reflected in the artifact’s provenance chain.

### 040-000::023 Secret Segregation & Logic
- **Prohibition:** No private keys, raw entropy, or cryptographic seeds may be stored within the T3S repository.  
- **Principle:** The repository stores only the **proof** of identity (signatures, public keys), never the **source** of identity (private keys).  
- **Boundary:** This ensures the T3S graph remains sovereign, auditable, and free from embedded secrets.

### 040-000::024 Service-Class Identity Exceptions
Automated operational logging (500-block) permits **Service-Class Identities** provided that:

1. **Scoped Authority:** Restricted to append-only permissions within designated operational directories.  
2. **Traceability:** Each service key MUST be indexed in a subordinate registry and linked to a parent Steward-class identity.  
3. **Non-Repudiation:** Automated logs MUST carry a valid signature to prevent “Ghost Telemetry” and ensure forensic completeness.  
4. **Lifecycle Boundaries:** Service identities may not modify `tier-1` artifacts or alter lifecycle states.

## 040-000::030 Access Control Levels

| Tier    | Role            | Capabilities                                                                 |
| :------ | :-------------- | :--------------------------------------------------------------------------- |
| tier-1  | System Steward  | Merge authority; root holder; authority to promote artifacts to `active` or `immutable`. |
| tier-2  | Contributor     | Read/Write access to `draft` and `review` artifacts via Pull Request.       |
| tier-3  | Auditor         | Read-only access to forensic evidence, manifests, and lineage records.      |

Access levels MUST align with the `t3s:status` lifecycle and the enforcement semantics defined in **020-000**.

## 040-000::040 Integrity Assertion (ITIL 4 SVS)
The System Steward SHALL perform periodic **Integrity Audits** to ensure:

1. **Chain of Custody:**  
   No artifact has been modified without an associated and signed **140-series ADR**, and corresponding updates to `t3s:provenance` and `t3s:lineage`.

2. **Key Rotation:**  
   Periodic review of active public keys in the `040.100` block to retire stale or compromised identities.

3. **Breach Protocol:**  
   If a key is compromised, the steward MUST:  
   - mark the affected identity as `retired`  
   - re-verify all commits since the last known “Good State`  
   - regenerate any impacted `t3s:integrity` seals  
   - update lineage entries to reflect the remediation event  

Integrity Assertion ensures the T3S graph remains sovereign, trustworthy, and cryptographically sound.

---

## License
Copyright © 2026 The System Stewardship Standards Initiative (T3SI). Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0.