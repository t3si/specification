---
id: T3S-ADR-140-001
urn: "urn:t3s:v0.2.1:adr:control:h:[pending]"
title: "Establishment of the T3S Canon and 10‑Block Taxonomy"
version: "0.2.1"
status: "Active"
steward: "urn:t3s:v0.2.1:steward:placeholder:h:[pending]"
classification: "Public"
criticality: "Tier-1"
license: "Apache-2.0"
copyright: "Copyright © 2026 The Systemic Stewardship Standards Initiative (T3SI)"
created: "2026-04-18"
updated: "2026-04-18"
supersedes: []
superseded_by: []
dependencies: []
---

# 140-001 Establishment of the T3S Canon and 10‑Block Taxonomy ^f3a1c0e4b912

## 140-001::010 Decision ^c91e4b0f2a33
T3S formally adopts a **10‑block canonical taxonomy**, consisting of:

* **000 — System Control**
* **100 — Governance**
* **200 — Architecture**
* **300 — Engineering**
* **400 — Infrastructure**
* **500 — Operations**
* **600 — Observability**
* **900 — Utilities**

The **000 Block** is designated as the **Markov Blanket** (machine‑readable control plane).
The **100–900 Blocks** constitute the **Observational Plane** (human‑authored governance and evidence).

This taxonomy is the **T3S Canon**, the authoritative structural backbone of the standard.

## 140-001::020 Context ^a4d9f1b2c0e8
Early T3S versions (`v0.1.0` → `v0.2.0`) lacked a stable, deterministic hierarchy.
By `v0.2.1`, the following had stabilized:

* the 10‑block structure
* the Markov Blanket concept
* the separation of machine vs. human planes
* the alignment with ITIL 4 SVS
* the use of deterministic folder prefixes
* the JSON‑LD system manifest

This ADR formalizes the taxonomy as a normative architectural decision.

## 140-001::030 Rationale ^e1b4c9f0a3d2

### 140-001::031 Deterministic Locality ^b0c4e1f9a233
Every artifact has a predictable, discoverable location.

### 140-001::032 Semantic Grouping ^d9a1b0c4f2e3
Each block corresponds to a coherent governance or operational domain.

### 140-001::033 ITIL Symmetry ^c0f9a1d2b344
The taxonomy aligns with ITIL 4 SVS, enabling:

* service configuration management
* governance alignment
* operational traceability

### 140-001::034 Ontological Safety ^f1c0b9e4a2d1
The 000 Block forms a machine‑readable Markov Blanket, ensuring:

* identity integrity
* provenance enforcement
* safety constraints
* semantic anchoring

### 140-001::035 Cognitive Load Reduction ^a9d1c0e4f233
A fixed, predictable structure reduces ambiguity for both humans and agents.

## 140-001::040 Alternatives Considered ^d0b1e4c9f2a3

### 140-001::041 Flat Namespace ^e4c0b9a1d3f2
Rejected due to lack of semantic grouping and deterministic locality.

### 140-001::042 Arbitrary Deep Hierarchy ^b1d0c4e9f3a2
Rejected due to inconsistent depth and brittle automation.

### 140-001::043 Two‑Block System ^c4e1b0f9a2d3
Rejected because it collapses governance, architecture, operations, and evidence.

### 140-001::044 Dynamic or Generated Taxonomy ^f9a0c1d2b3e4
Rejected because T3S requires stability and auditability.

## 140-001::050 Consequences ^a0d1c9f4b233

### 140-001::051 Positive ^d1b0e4c9f2a3
deterministic traversal

* semantic anchoring
* JSON‑LD mapping
* governance pipeline compatibility
* provenance tracking
* Markov Blanket enforcement

### 140-001::052 Negative ^c9e1a0b4d3f2

* strict discipline required
* reindexing required for structural changes
* governance gates must enforce compliance

## 140-001::060 Dependencies ^b4c0e1f9a233
This ADR is foundational and is depended upon by:

* ADR‑140‑002 (JSON‑LD Semantic Substrate)
* ADR‑140‑003 (Anchor & Leaf Protocol)
* ADR‑140‑004 (Dual‑Stack Documentation Model)
* ADR‑140‑009 (v0.2.x Index Model)
* ADR‑140‑010 (Three‑Plane System)
* ADR‑140‑013 (VFS Projection Model)
* ADR‑140‑014 (Structured Index Model, v0.3.0)
* ADR‑140‑015 (Ontology, v0.3.0)
* ADR‑140‑016 (Canon/Ontology/Reference/SDK Separation, v0.3.0)

## 140-001::070 Supersession ^e0c1b9a4d3f2
This ADR does not supersede any prior ADR.
It may be superseded if:

* the Canon expands
* the block taxonomy evolves
* the Markov Blanket model changes

## 140-001::080 Notes ^f4b1c0e9a233
This ADR establishes the structural spine of T3S.
All future architectural decisions must align with this taxonomy unless explicitly superseded.

---

## License
Copyright © 2026 The Systemic Stewardship Standards Initiative (T3SI). Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0.