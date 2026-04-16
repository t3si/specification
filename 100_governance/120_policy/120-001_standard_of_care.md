---
id: "T3S-DOC-120-001"
urn: "urn:t3s:v0.2.1-alpha:leaf:control:h:[HASH_RESERVED]"
type: "t3s:leaf"
plane: "t3s:control"
domain: "120_policy"
title: "Standard of Care Directive"
objective: "Define the minimum technical, operational, and governance requirements for all entities operating within the T3S Markov Blanket."
description: "The authoritative Standard of Care for the T3S framework, establishing verification gates, violation protocols, and sovereign governance requirements."
status: "draft"
version: "0.2.1-alpha"
steward: "urn:t3s:v0.2.1-alpha:steward:h:dab0d2c9622d"
criticality: "tier-1"
liability: "high"
sovereignty: "sovereign"
authority: 100
classification: "public"
license: "Apache-2.0"
references:
  - t3s:predicate: "t3s:dependency"
    target: "urn:t3s:v0.2.1-alpha:leaf:control:h:[HASH_RESERVED]"
    description: "Depends on the Systemic Stewardship Objectives (010-001) for constitutional enforcement."
  - t3s:predicate: "t3s:dependency"
    target: "urn:t3s:v0.2.1-alpha:leaf:control:h:[HASH_RESERVED]"
    description: "Depends on the Core Definitions (050.100-001) for predicate, provenance, and lifecycle semantics."
t3s:integrity: "sha256:[HASH_RESERVED]"
---

# 120-001 Standard of Care Directive

## 120-001::010 Purpose
This directive defines the **Standard of Care** for all entities operating within the T3S Markov Blanket.  
It transforms subjective governance expectations into **deterministic, machine-verifiable Boolean gates**, ensuring:

- sovereign containment (Objective C)  
- guardrail enforcement (Objective F)  
- provenance integrity (Objective G)  
- lineage fidelity (Objective H)  
- deterministic enforcement (Objective L)  
- recursive self-correction (Objective N)  

The Standard of Care is the **primary operational mandate** of the T3S framework.

---

## 120-001::020 Core Assertions (Verification Gates)
Every artifact, automation pipeline, and agentic action MUST satisfy the following assertions.  
Failure of **any** assertion renders the artifact **non-normative**.

### 120-001::021 Assertion of Structural Integrity (A0)
**Requirement:**  
Artifacts MUST adhere to the **Anchor and Leaf Protocol**, the **Stewardship Boundary**, and the **130-series Manifest Schema**.

**Boolean Gate:**  
verify_schema(artifact) == TRUE
&& verify_index(artifact) == TRUE
&& verify_boundary(artifact) == TRUE


### 120-001::022 Assertion of Provenance (A1)
**Requirement:**  
No artifact may exist without cryptographically verifiable `t3s:provenance` and a valid steward identity.

**Boolean Gate:**  
exists(artifact.provenance)
&& verify_signature(artifact.provenance) == TRUE


### 120-001::023 Assertion of Intent (A2)
**Requirement:**  
Every automated action MUST be semantically linked to a URN via JSON‑LD and resolvable through the 050‑series ontology.

**Boolean Gate:**  
artifact.intent_urn != NULL
&& resolve(artifact.intent_urn).status == "active"


### 120-001::024 Assertion of Locality (A3)
**Requirement:**  
Sensitive logic and identity data MUST remain within the sovereign boundary unless an explicit, steward-signed waiver exists.

**Boolean Gate:**  
artifact.storage_class == "sovereign"
|| exists(artifact.cloud_waiver) == TRUE


### 120-001::025 Assertion of Temporal Integrity (A4)
**Requirement:**  
All evidence (500-series) MUST be timestamped and anchored to the governance version active at execution time.

**Boolean Gate:**  
artifact.timestamp.governance_version
== active_governance_version_at_runtime


### 120-001::026 Assertion of State Fidelity (A5)
**Requirement:**  
The physical state of the infrastructure (400-series CMDB) MUST match the normative state defined in the 100-series governance domain.

**Boolean Gate:**  
compare(actual_state, normative_state) == MATCH


---

## 120-001::030 Violation Protocols
Any artifact or process returning `FALSE` for any Core Assertion is **non-normative** and MUST trigger enforcement.

### 120-001::031 Automated Halt
In high-liability domains (300/400-series), a violation MUST trigger:

- immediate pipeline failure  
- agentic suspension  
- VFS unmount (if applicable)  

This aligns with **Objective F (Guardrail Enforcement)** and **Objective L (Deterministic Enforcement)**.

### 120-001::032 Forensic Logging
All violations MUST be:

- recorded as `t3s:record` artifacts in the **500-series Evidence Database**  
- mirrored to the **600-series Observability** domain  
- linked to the violating artifact’s `t3s:lineage`  

This ensures sovereign traceability and supports **Objective G/H**.

---

## 120-001::040 Governance
The Standard of Care is the primary technical mandate of the **T3SI**.  
It is subject to:

- quarterly peer review  
- regulatory alignment updates (FinTech, EHS, critical infrastructure)  
- mandatory ADR documentation for any modification (140-series)  

No change may bypass the **Sovereign Canon** or the constitutional constraints defined in **010-001**.

---

## License
Copyright © 2026 The Systemic Stewardship Standards Initiative (T3SI). Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0.