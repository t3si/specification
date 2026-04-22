---
id: "T3S-ADR-140-007"
urn: "urn:t3s:v0.2.1:adr:control:h:[pending]"
type: "t3s:adr"
plane: "t3s:control"
title: "Metadata Schema Standard"
description: "Defines the human‑stack metadata header, the machine‑stack metadata schema, and the structural container system including t3s:structure and its subsystems: index, tree, namespace, and map."
status: "draft"
version: "0.2.1"
steward: "urn:t3s:v0.2.1:steward:h:[pending]"
created: "2026-04-21"
updated: "2026-04-21"
supersedes: []
superseded_by: []
dependencies:
  - "T3S-ADR-140-001"
---

# 140‑007 Metadata Schema Standard

## 140‑007::010 Context ^a1f3c9d20411
T3S requires a metadata schema that:

* supports **human‑stack readability**
* supports **machine‑stack governance**
* maps cleanly between the **VFS**, **SKG**, and **URN resolution**
* is **plane‑aware**, **governance‑aware**, and **structurally coherent**
* avoids hierarchical metaphors as conceptual primitives
* provides a **unified structural ontology** for agents and auditors

Earlier metadata patterns relied on:

* filesystem metaphors (`tree`)
* slug‑based routing (`namespace`)
* positional ordering (`index`)

These were useful but incomplete.
They lacked a **conceptual structural substrate** for the SKG.

This ADR introduces:

* the **structural container type** `t3s:structure`
* the **conceptual structural subsystem** `t3s:map`
* a clarified separation between human‑stack and machine‑stack metadata
* the **naming principle** governing type and property definitions

## 140‑007::020 Decision ^c7b84e2a9f52

#### A. Human‑stack metadata header (minimal)
Markdown artifacts (ADRs, specs, definitions) MUST include:

* `id`
* `urn`
* `type`
* `plane`
* `title`
* `description`
* `status`
* `version`
* `steward`
* `created`
* `updated`
* `supersedes`
* `superseded_by`
* `dependencies`

No governance metadata appears in the human header.
No structural metadata appears in the human header.

#### B. Machine‑stack metadata (authoritative)
Machine‑stack metadata is expressed in:

* `.t3s.json` sidecars
* the System Knowledge Graph (SKG)
* the Manifest

Machine‑stack metadata MUST include:
* **identity metadata**
* **governance metadata**
* **structural metadata**
* **semantic references**

#### C. Introduction of t3s:structure (container type)
`t3s:structure` groups all structural subsystems:

* `t3s:index` — physical / positional structure
* `t3s:tree` — human‑stack hierarchical structure
* `t3s:namespace` — machine‑stack logical structure
* `t3s:map` — conceptual / graph‑stack structure

#### D. Definition of t3s:map (conceptual structural subsystem)
`t3s:map` defines the **structural identity** of a node in the SKG.

Initial structural identities include:

* `t3s:anchor` — definitional structural node
* `t3s:unit` — atomic conceptual node
* `t3s:composite` — multi‑artifact conceptual node
* `t3s:cluster` — conceptual grouping
* `t3s:governed` — governance‑bound conceptual node
* `t3s:evidence` — observational conceptual node
* `t3s:reference` — referential conceptual node

These are **non‑hierarchical**, **non‑physical**, and **non‑positional**.

#### E. Governance metadata is mandatory
All machine‑stack artifacts MUST declare:

* `t3s:criticality`
* `t3s:liability`
* `t3s:sovereignty`
* `t3s:authority`
* `t3s:status`
* `t3s:integrity`
* `t3s:provenance`

Governance metadata is required for systemic governance and insurability.

## 140‑007::030 Rationale ^5e2d7b18ac94

### 140‑007::031 Naming Principle ^b0c4e1f9a233
> In T3S, types, properties, and attributes name themselves once their role is fully defined, unambiguous, and orthogonal to all other primitives.

This principle ensures:

* regulator legibility
* agentic reasoning clarity
* semantic safety
* ontological coherence
* avoidance of naming collisions

### 140‑007::032 Structural Quadrants ^d9a1b0c4f2e3
T3S structural systems fall into four quadrants:

| Subsystem 	| Purpose	| Axis |
| `t3s:index` 	| deterministic locality	| physical |
| `t3s:tree`	| human hierarchy	| human |
| `t3s:namespace` |	logical lineage	| machine |
| `t3s:map` 	| conceptual identity	| conceptual |


This quadrantal model resolves long‑standing ambiguity in the structural ontology.

### 140‑007::033 Container Types ^c0f9a1d2b344
`t3s:structure` is introduced as the container for all structural subsystems.
This avoids:

* property sprawl
* conceptual fragmentation
* inconsistent grouping
* ambiguous semantics

### 140‑007::034 Conceptual Structure (t3s:map) ^f1c0b9e4a2d1
`t3s:map` fills the conceptual gap between:

* physical structure (index)
* human structure (tree)
* logical structure (namespace)

It defines graph‑level structural identity, enabling:

* agent navigation
* conceptual grouping
* semantic topology
* non‑hierarchical organization

### 140‑007::035 Governance Metadata Requirements ^a9d1c0e4f233
Governance metadata is required for:

* NAIC‑grade insurability
* systemic safety
* provenance enforcement
* deterministic conflict resolution
* execution denial logic

## 140‑007::040 Consequences ^d3a91c0f7b68

**Positive**
* Unified structural ontology
* Clear separation of human vs. machine metadata
* Mandatory governance metadata
* Conceptual structural substrate (`t3s:map`)
* Containerization of structural systems (`t3s:structure`)
* Improved agent navigation and RAG performance
* Reduced ambiguity for auditors and implementers

**Negative**
* Requires migration of existing metadata
* Requires updates to SDKs and tooling
* Requires updates to documentation and training materials

## 140‑007::050 Status ^9f46e2ab31cd
**Status:** draft  
To be finalized alongside:

* ADR‑140‑008 (Machine‑Stack Metadata Schema)
* ADR‑140‑010 (Structural Subsystem Definitions)

---

## License
Copyright © 2026 The Systemic Stewardship Standards Initiative (T3SI). Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0.