# RFC-0008: Lifecycle Specification Standard

- **Status:** Accepted
- **Author:** Architecture Board
- **Scope:** Standardizes how Lifecycle is specified within Domain Entity specifications, consistent with RFC-0000 through RFC-0007

This RFC does not define the concrete lifecycle of any specific entity. It proposes an architectural standard for how Lifecycle SHALL be specified wherever it appears in a Domain Entity specification. Concrete lifecycle definitions remain the responsibility of entity-specific RFCs.

---

## 1. Purpose

This RFC proposes an architectural standard for specifying Lifecycle within Domain Entity specifications. It defines what a Lifecycle specification MUST contain, how it relates to the entity it describes, and how it MUST be expressed when it touches other entities.

This RFC does not itself specify the lifecycle of Creator, Identity, Memory, Knowledge, Workspace, Project, Skill, or Artifact. It establishes the standard that such specifications, wherever they occur, SHALL follow.

---

## 2. Motivation

RFC-0001 through RFC-0005 define entities without a consistent standard for describing how those entities change state over time. Where lifecycle-adjacent language has appeared informally in prior discussion, it has lacked a common structure, leaving open questions about what a lifecycle specification must contain and how it may reference entities other than the one it describes.

Without such a standard, future entity-specific RFCs risk describing lifecycle inconsistently — using different structures, omitting invariants, or expressing cross-entity effects in ad hoc language rather than the canonical relationship vocabulary established by RFC-0006. This RFC exists to close that gap before further domain specification work proceeds.

---

## 3. Scope

This RFC applies to every Domain Entity specification, present and future, established under RFC-0001 and its specializations.

This RFC governs the structure and content required of a Lifecycle specification. It does not govern, and does not attempt to determine, what any specific entity's valid states, transitions, or invariants actually are — that determination belongs to the RFC that specializes the entity in question.

---

## 4. Architectural Principle

Lifecycle is a mandatory architectural aspect of every Domain Entity specification. Every entity specification SHALL include a Lifecycle section describing how instances of that entity may change state over time.

Lifecycle is not an Entity, a Relationship, a Boundary, an independent architectural primitive, or an implementation mechanism. It is an aspect of an entity's specification — a required part of describing the entity completely, in the same sense that an entity's properties, as established in that entity's canonical specification, and its boundary, as established under RFC-0007, are required parts of describing it completely.

This RFC does not introduce a new architectural primitive. It standardizes the form an already-necessary part of entity specification SHALL take.

---

## 5. Lifecycle Specification

A Lifecycle specification belongs to the Entity specification it describes. It is not a separate document, a separate entity, or a construct with standing independent of the entity it belongs to.

A Lifecycle specification SHALL specify:

- the valid states an instance of the entity may occupy;
- the valid transitions between those states;
- the invariants that SHALL hold throughout the lifecycle;
- terminal conditions, where applicable to the entity.

A Lifecycle specification MUST NOT introduce concepts, relationships, or boundaries beyond those already established for the entity by its governing RFC and by RFC-0006 and RFC-0007.

---

## 6. Architectural Rules

The following rules govern every Lifecycle specification.

A Lifecycle specification SHALL be written as part of the entity's own specification, not as a standalone architectural document.

A Lifecycle specification SHALL NOT redefine the entity's boundary, as established under RFC-0007, or any relationship the entity participates in, as established under RFC-0006.

A Lifecycle specification SHALL NOT introduce a new entity, relationship, or boundary in order to describe lifecycle behavior.

A Lifecycle specification MUST NOT describe implementation mechanisms — how a transition is technically triggered, recorded, or propagated is outside the scope of this RFC and of any Lifecycle specification written under it.

---

## 7. Cross-Entity Constraints

Where a Lifecycle specification must describe how one entity's lifecycle constrains, is constrained by, or otherwise touches another entity, it SHALL express that connection using only the canonical relationship vocabulary defined by RFC-0006 — *owns*, *contains*, *organizes*, *informs*, *derives from*, *supports*, *produces*, or *references*.

A Lifecycle specification SHALL NOT describe cross-entity effects using informal language. Phrasing such as an entity "owning its lifecycle," one lifecycle "depending on" another, an entity "participating in every lifecycle," or lifecycle "belonging to the domain model" MUST NOT appear in any Lifecycle specification, as such phrasing does not resolve to any relationship defined by RFC-0006 and reintroduces the ambiguity that RFC-0006 was written to eliminate.

Where a cross-entity lifecycle effect cannot be expressed using the existing relationship vocabulary, this indicates either that the effect does not belong in the Lifecycle specification, or that a gap exists in the relationship vocabulary that must be raised for architectural review under RFC-0006 — not resolved through informal phrasing.

---

## 8. Lifecycle Transitions

A transition SHALL be defined as a change from one valid state to another, as enumerated in the entity's Lifecycle specification. A Lifecycle specification SHALL enumerate valid transitions explicitly; a transition not enumerated is not valid.

Lifecycle transitions MAY produce observable domain effects. The nature, propagation, or processing of such effects as domain events is outside the scope of this RFC. This RFC does not introduce Domain Events as an architectural concept, and no Lifecycle specification written under this RFC SHALL do so.

---

## 9. Lifecycle Invariants

A Lifecycle specification SHALL state the invariants that hold across all valid states and transitions of the entity's lifecycle.

Lifecycle invariants SHALL preserve the architectural continuity of the entity — a Lifecycle specification MUST NOT define a transition or state that would violate an invariant already established for the entity by its governing RFC, including, where the entity is subject to it, the continuity established for Identity under RFC-0002.

Lifecycle invariants stated in an entity's Lifecycle specification are subordinate to, and MUST NOT contradict, the invariants already established for that entity elsewhere. Where an apparent conflict exists, the entity's governing RFC prevails, consistent with RFC-0000's canonical source rule.

---

## 10. Specialization

Future entity-specific RFCs, and revisions to existing ones, SHALL include a Lifecycle section conforming to this standard.

A Lifecycle specification MAY be as simple as a single valid state with no transitions, where an entity's nature warrants it. This RFC does not require lifecycle complexity where none is architecturally justified; it requires only that whatever lifecycle an entity has be specified in the form this RFC establishes.

---

## 11. Out of Scope

This RFC does not define:

- the concrete lifecycle of Creator, Identity, Memory, Knowledge, Workspace, Project, Skill, or Artifact;
- domain events or any mechanism for observing, recording, or propagating lifecycle transitions;
- implementation mechanisms for enforcing, storing, or executing lifecycle transitions;
- runtime behavior of any kind.

These remain the responsibility of entity-specific RFCs and, where applicable, later Technical Architecture work, consistent with the Architecture Lifecycle established in `ARCHITECTURE_STRATEGY.md`.

---

## 12. Architectural Decision

This RFC proposes that Lifecycle be recognized as a mandatory aspect of Domain Entity specification, governed by the standard set out in Sections 5 through 9, and that all future and revised entity specifications conform to it.

This RFC does not itself decide the lifecycle of any specific entity. Acceptance of this RFC establishes only the standard; concrete lifecycle content is decided separately, through the entity-specific RFCs this standard governs.

---

## 13. Migration

RFC-0008 establishes a new architectural standard. Previously accepted RFCs remain valid. RFC-0008 does not retroactively invalidate any previously accepted RFC.

Existing entity specifications that do not yet include a Lifecycle section conforming to this standard MAY require future alignment. The initial migration targets are:

- RFC-0002 (Creator Identity)
- RFC-0003 (Memory Model)
- RFC-0004 (Knowledge Model)
- RFC-0005 (Workspace Model)

Migration SHALL be handled through future revision RFCs, each proposed, reviewed, and accepted according to the process established by RFC-0000. No existing RFC is amended by the acceptance of RFC-0008 alone.

---

## 14. Consequences

If accepted, this RFC would require every future Domain Entity specification to include a Lifecycle section conforming to the standard set out here, and would establish a documented expectation that existing entity specifications lacking such a section be brought into alignment through subsequent revision RFCs.

Acceptance would also constrain how cross-entity lifecycle effects may be described going forward, requiring the canonical relationship vocabulary of RFC-0006 in place of informal phrasing, which would reduce ambiguity in future entity specifications at the cost of requiring more deliberate phrasing when a cross-entity effect does not map cleanly onto an existing relationship type.

Acceptance would not, by itself, change the current content of RFC-0002 through RFC-0005; it would only establish the standard those RFCs are expected to be brought into alignment with over time.
