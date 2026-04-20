---
id: T3S-ADR-140-003
urn: "urn:t3s:v0.2.1:adr:control:h:[pending]"
title: "Anchor & Leaf Protocol"
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
  - T3S-ADR-140-002
---

# 140-003 Anchor & Leaf Protocol ^e3c1a0f4b912

## 140-003::010 Decision ^b9d1c0e4a233
T3S adopts the **Anchor & Leaf Protocol** as the deterministic addressing model for:

* headings
* sections
* subsections
* fragments
* machine‑readable anchors
* cross‑document references
* VFS projections
* JSON‑LD @id bindings

The protocol defines:

1. **Anchors** — deterministic, index‑prefixed headings
2. **Leaves** — deterministic fragment identifiers derived from SHA‑256‑12 of the heading text
3. **Stable addressing** — headings never change identity unless intentionally superseded
4. **Deterministic linking** — all references use anchor + leaf pairs

This protocol becomes mandatory for all T3S documents beginning in v0.2.1.

## 140-003::020 Context ^d1b0e4c9f2a3
Before v0.2.1, T3S documents suffered from:

* unstable headings
* non‑deterministic section references
* broken links after refactors
* ambiguous cross‑document references
* inconsistent fragment identifiers
* difficulty mapping documents into the System Knowledge Graph

Event 2 introduced the first deterministic heading index (140-001::010) and demonstrated:

* stable machine‑readable anchors
* compatibility with JSON‑LD @id
* compatibility with the Markov Blanket
* compatibility with the VFS projection model

By v0.2.1, the Anchor & Leaf Protocol had become the de facto standard.
This ADR formalizes it.

## 140-003::030 Rationale ^c4e1b0f9a2d3

### 140-003::031 Deterministic Addressing ^f1c0b9e4a2d1
Every heading has a stable, predictable identity.

### 140-003::032 Machine‑Readable Anchors ^a0d1c9f4b233
Anchors (140-003::010) allow:

* automated traversal
* semantic extraction
* VFS mapping
* SKG integration

### 140-003::033 Collision‑Resistant Leaves ^d0b1e4c9f2a3
Leaves (^<sha256-12>) ensure:

* stable fragment identifiers
* safe cross‑document linking
* compatibility with ZK‑addressable metadata

### 140-003::034 Refactor‑Safe Linking ^e4c0b9a1d3f2
Links remain valid even if:

* files move
* folders change
* documents are reorganized

### 140-003::035 Ontological Alignment ^c9e1a0b4d3f2
The protocol aligns with:

* JSON‑LD
* the SKG
* the Markov Blanket
* the structured index model (v0.3.0)

## 140-003::040 Alternatives Considered ^f9a0c1d2b3e4

### 140-003::041 Natural Language Headings ^b1d0c4e9f3a2
Rejected due to instability and ambiguity.

### 140-003::042 Auto‑Generated Fragment IDs ^c4e1b0f9a2d3
Rejected because they change when headings change.

### 140-003::043 UUID‑Based Anchors ^e0c1b9a4d3f2
Rejected due to lack of semantic meaning and human readability.

### 140-003::044 No Fragment Hashes ^a9d1c0e4f233
Rejected because it breaks deterministic linking and SKG integration.

## 140-003::050 Consequences ^d1b0e4c9f2a3

### 140-003::051 Positive ^c0f9a1d2b344

* stable linking
* deterministic traversal
* machine‑readable structure
* SKG compatibility
* VFS compatibility
* future ZK‑proof compatibility

### 140-003::052 Negative ^e4c0b9a1d3f2

* requires strict discipline
* requires stable heading text
* requires governance gates to enforce compliance

## 140-003::060 Dependencies ^b4c0e1f9a233
This ADR depends on:

* ADR‑140‑001 (T3S Canon)
* ADR‑140‑002 (JSON‑LD Semantic Substrate)

This ADR is depended upon by:

* ADR‑140‑004 (Dual‑Stack Documentation Model)
* ADR‑140‑007 (Manifest Schema Standard)
* ADR‑140‑009 (v0.2.x Index Model)
* ADR‑140‑013 (VFS Projection Model)
* ADR‑140‑014 (Structured Index Model, v0.3.0)
* ADR‑140‑015 (Ontology, v0.3.0)

## 140-003::070 Supersession ^f4b1c0e9a233
This ADR does not supersede any prior ADR.
It may be superseded if:

* the addressing model changes
* the fragment‑hash protocol evolves
* the structured index model replaces anchor semantics

## 140-003::080 Notes ^a0d1c9f4b233
The Anchor & Leaf Protocol is the addressing spine of T3S.
All future documents must comply with this protocol unless explicitly superseded.

---

## License
Copyright © 2026 The Systemic Stewardship Standards Initiative (T3SI).
Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License.
You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0.