---
id: T3S-ADR-140-002
urn: "urn:t3s:v0.2.1:adr:control:h:[pending]"
title: "JSON‑LD Semantic Substrate & System Knowledge Graph"
version: "0.2.1"
status: "draft"
steward: "urn:t3s:v0.2.1:steward:placeholder:h:[pending]"
classification: "public"
criticality: "tier-1"
license: "Apache-2.0"
created: "2026-04-18"
updated: "2026-04-18"
supersedes: []
superseded_by: []
dependencies:
  - T3S-ADR-140-001
---

# 140-002 JSON‑LD Semantic Substrate & System Knowledge Graph ^c3f1a0e4b912

## 140-002::010 Decision ^a9d1c0f2b344
T3S formally adopts JSON‑LD as the canonical semantic substrate for all machine‑readable artifacts and establishes the **System Knowledge Graph (SKG)** as the unified semantic model that binds:

* manifests
* governance artifacts
* identity records
* operational evidence
* VFS projections
* Markov Blanket boundaries
* future ontology layers

JSON‑LD becomes the **mandatory encoding** for all structured system metadata beginning in v0.2.1.

The System Knowledge Graph becomes the **authoritative semantic representation** of the T3S environment.

## 140-002::020 Context ^d1b0e4c9f233
Prior to v0.2.1, T3S used:

* ad‑hoc JSON
* YAML fragments
* untyped metadata
* inconsistent schemas
* implicit relationships

This created:

* semantic drift
* inconsistent provenance
* brittle automation
* unclear identity boundaries
* difficulty in validating safety constraints

Event 2 introduced the first JSON‑LD manifest, which demonstrated:

* stable @id anchors
* deterministic linking
* compatibility with the Anchor & Leaf Protocol
* compatibility with the Markov Blanket
* compatibility with the emerging type system

By v0.2.1, JSON‑LD had become the de facto substrate.
This ADR formalizes it as the normative standard.

## 140-002::030 Rationale ^b4c0e1f9a2d3

### 140-002::031 Semantic Interoperability ^e4c0b9a1d3f2
JSON‑LD provides a W3C‑standard mechanism for expressing linked data, enabling:

* cross‑document linking
* schema evolution
* ontology layering
* machine reasoning

### 140-002::032 Deterministic Identity ^c9e1a0b4d3f2
@id anchors map cleanly to:

* URNs
* fragment hashes
* VFS paths
* Markov Blanket boundaries

### 140-002::033 Compatibility with the Anchor & Leaf Protocol ^f1c0b9e4a2d1
JSON‑LD allows:

* stable anchors
* deterministic leaf references
* machine‑verifiable provenance

### 140-002::034 Foundation for the Knowledge Graph ^a0d1c9f4b233
The SKG becomes the semantic “source of truth” for:

* governance
* architecture
* operations
* observability
* identity
* safety

### 140-002::035 Future‑Proofing ^d0b1e4c9f2a3
JSON‑LD is compatible with:

* RDF
* OWL
* SHACL
* SPARQL
* future ZK‑addressable metadata

## 140-002::040 Alternatives Considered ^f9a0c1d2b3e4

### 140-002::041 Raw JSON ^b1d0c4e9f3a2
Rejected due to lack of semantic meaning and linking.

### 140-002::042 YAML ^c4e1b0f9a2d3
Rejected due to lack of deterministic typing and linking.

### 140-002::043 XML ^e0c1b9a4d3f2
Rejected due to verbosity and lack of native linked‑data semantics.

### 140-002::044 Custom Schema Language ^a9d1c0e4f233
Rejected due to maintenance burden and lack of ecosystem support.

## 140-002::050 Consequences ^d1b0e4c9f2a3

### 140-002::051 Positive ^c0f9a1d2b344

* unified semantic model
* deterministic linking
* stable identity
* machine reasoning
* schema evolution
* compatibility with VFS
* compatibility with Markov Blanket

### 140-002::052 Negative ^e4c0b9a1d3f2

* requires strict schema discipline
* requires JSON‑LD tooling
* requires governance gates
* requires training for contributors

## 140-002::060 Dependencies ^b4c0e1f9a233
This ADR depends on:

* ADR‑140‑001 (T3S Canon)

This ADR is depended upon by:

* ADR‑140‑003 (Anchor & Leaf Protocol)
* ADR‑140‑004 (Dual‑Stack Documentation Model)
* ADR‑140‑007 (Manifest Schema Standard)
* ADR‑140‑010 (Three‑Plane System)
* ADR‑140‑013 (VFS Projection Model)
* ADR‑140‑015 (Ontology, v0.3.0)

## 140-002::070 Supersession ^f4b1c0e9a233
This ADR does not supersede any prior ADR.
It may be superseded if:

* the semantic substrate changes
* the SKG model evolves
* a new ontology layer replaces JSON‑LD

## 140-002::080 Notes ^a0d1c9f4b233
This ADR establishes the semantic spine of T3S.
All future machine‑readable artifacts must be expressed in JSON‑LD unless explicitly superseded.

---

## License
Copyright © 2026 The Systemic Stewardship Standards Initiative (T3SI).
Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License.
You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0.