---
id: T3S-DOC-120-001
urn: "urn:t3s:policy:standard-of-care"
title: "Standard of Care Directive"
version: 0.1.0-alpha
status: Genesis
steward: "System Steward"
classification: "Public"
criticality: "Tier-1"
license: "CC-BY-4.0"
copyright: "Copyright © 2026 The System Stewardship Standards Initiative (T3SI)"
---

# 120 Standard of Care

## 1.0 Purpose
This directive defines the minimum technical and operational requirements (The Standard of Care) for all entities operating within the T3S Markov Blanket. It transforms subjective "Beliefs" into objective "Booleans."

## 2.0 Core Assertions (The Verification Gates)
To maintain the Standard of Care, every system artifact and agentic action must satisfy the following assertions:

### 2.1 Assertion of Provenance (A1)
* **Requirement:** No artifact shall exist without a cryptographically signed parentage.
* **Boolean Gate:** `exists(artifact.signature) && verify(artifact.signature) == TRUE`

### 2.2 Assertion of Intent (A2)
* **Requirement:** Every automated action must be linked to a specific URN from the 100-block Strategy or Policy domain.
* **Boolean Gate:** `artifact.metadata.intent_urn != NULL && is_valid(intent_urn) == TRUE`

### 2.3 Assertion of Locality (A3)
* **Requirement:** Sensitive system logic and identity data must reside within the "Local-First" sovereign boundary unless an explicit "Cloud-Second" waiver is attached.
* **Boolean Gate:** `artifact.storage_class == 'Sovereign' || exists(artifact.cloud_waiver) == TRUE`

### 2.4 Assertion of Temporal Integrity (A4)
* **Requirement:** All evidence generated (500-block) must be timestamped against the version of the Governance block (100) active at the time of execution.
* **Boolean Gate:** `artifact.timestamp.governance_version == active_version_at_runtime`

### 2.5 Assertion of State Fidelity (A5)

* **Requirement:** The physical state of the infrastructure (400-block) must be periodically reconciled against the Normative State defined in the Governance block (100).
* **Boolean Gate:** compare(actual_state, normative_state) == MATCH

## 3.0 Violation Protocols
Any artifact or process that returns `FALSE` on any Core Assertion is considered "Non-Normative."
* **3.1 Automated Halt:** In high-hazard blocks (300/400), a `FALSE` result must trigger an immediate pipeline failure.
* **3.2 Forensic Logging:** All failures must be recorded in the 600-block (Observability) for human-in-the-loop remediation.

## 4.0 Governance
The Standard of Care is subject to quarterly peer review and must be updated to reflect emerging regulatory requirements, with a primary focus on high-hazard and highly regulated sectors (e.g., FinTech, EHS, and critical infrastructure).

---
## License
Copyright © 2026 The System Stewardship Standards Initiative (T3SI).
This documentation is licensed under the Creative Commons Attribution 4.0 International License (CC-BY-4.0).