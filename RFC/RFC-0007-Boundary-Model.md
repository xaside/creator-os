# RFC-0007: Boundary Model

- **Status:** Accepted
- **Author:** Architecture Board
- **Scope:** Establishes the canonical boundary model separating responsibilities among entities defined in RFC-0001 through RFC-0005, using the relationship vocabulary established in RFC-0006

This RFC does not introduce new entities and does not introduce new relationships. It defines where every entity's responsibility begins and ends, and becomes the canonical definition of responsibility boundaries throughout CreatorOS.

---

## 1. Purpose

CreatorOS already defines what exists, through the entities established in RFC-0001 and specialized in the RFCs that followed it, and how those entities relate, through the relationship vocabulary established in RFC-0006. What remains undefined, until this RFC, is where each entity's responsibility begins and ends — the limit beyond which one entity's concerns are no longer its own, and belong instead to another.

Architecture requires boundaries because entities remain coherent only when their responsibilities are explicitly limited. An entity without a clear boundary does not stay contained — it gradually absorbs responsibilities that were never meant to be its own, until its definition no longer matches what it actually does within the architecture. Boundaries exist to prevent exactly this kind of conceptual erosion, holding each entity to the responsibility it was defined to carry.

Without explicit boundaries, concepts drift, entities absorb responsibilities that belong elsewhere, architectural duplication emerges as the same responsibility is reinvented in more than one place, and the canonical vocabulary established in prior RFCs gradually loses its precision. Boundaries preserve conceptual integrity against all of these failure modes.

This RFC completes a three-part foundation. RFC-0001 through RFC-0005 established what exists. RFC-0006 established how what exists relates. This RFC establishes where each thing that exists stops being itself and starts being something else's concern. Without this third part, the first two remain incomplete — entities and relationships can be stated precisely and still be misapplied, if nothing defines the limits within which each entity's precise statement actually holds.

---

## 2. Conceptual Definition

A Boundary is the conceptual limit of an entity's responsibility: the point beyond which a given concern no longer belongs to that entity, regardless of how closely related it may seem.

Boundaries are semantic. They describe a limit of meaning and responsibility, not a physical or technical partition of any kind.

Boundaries are architectural. They exist at the same level of abstraction as the entities and relationships they separate, and are defined with the same rigor.

Boundaries are not implementation constraints. Nothing about how CreatorOS is eventually built determines where a conceptual boundary lies; the boundary is established independently, at the domain level, and any implementation must conform to it rather than the reverse.

Boundaries are not storage limits. A boundary says nothing about how information might eventually be held or organized in some technical system.

Boundaries are not deployment limits. A boundary does not correspond to any division of operational units, services, or environments.

Boundaries are not security boundaries. Access control, permissions, and protective measures are separate concerns entirely; a conceptual boundary defines responsibility, not who or what may access something.

---

## 3. Properties of Boundaries

Boundaries, as defined in this model, share the following essential properties.

**Explicit.** A boundary is stated, not assumed. Where an entity's responsibility ends is a matter of deliberate definition, not something inferred from convenience or habit.

**Semantic.** A boundary carries meaning about responsibility, not a mechanical or arbitrary line.

**Stable.** A boundary's location does not shift casually. Once established, it remains fixed unless deliberately revised through the process this RFC describes.

**Exclusive.** A responsibility lies on one side of a boundary or the other, never on both. Two entities do not share the same responsibility as a matter of ordinary architecture.

**Implementation-independent.** A boundary's location and meaning hold regardless of how, or whether, CreatorOS is technically realized.

**Canonical.** Each entity's boundary, once established across the RFCs that define it, is authoritative and is not redefined independently by later documents.

---

## 4. Responsibility

Every entity defined in this domain model has a responsibility: a specific concern that belongs to it and to no other entity.

Responsibility exists entirely inside its boundary. An entity is answerable for what falls within its boundary and only for that — nothing outside its boundary is properly its concern, however tempting it may be to let an entity's scope expand to cover a nearby gap.

Responsibility may be supported by another entity, in the sense established by the *supports* relationship in RFC-0006 — one entity may enable another's responsibility without assuming any part of it. Responsibility may be informed by another entity, in the sense established by *informs* — one entity may shape or contribute to another's responsibility without taking it over.

Responsibility may never silently migrate across boundaries. Where a responsibility appears to be shifting from one entity to another, this must occur, if at all, through deliberate architectural revision — never as an unnoticed side effect of how entities happen to interact in practice.

---

## 5. Boundary Separation

Adjacent entities remain distinct even when tightly related. Conceptual proximity — the fact that two entities are closely connected, frequently discussed together, or depend heavily on one another — never removes conceptual separation between them.

Identity is not Memory, even though Memory informs Identity closely, as established in RFC-0002 and RFC-0003. Memory is not Knowledge, even though Knowledge derives directly from Memory, as established in RFC-0003 and RFC-0004. Knowledge is not Skill, even though Knowledge supports Skills closely, as established in RFC-0004. Workspace is not Project, even though Workspace contains Projects, as established in RFC-0005. Project is not Artifact, even though Projects produce Artifacts, as established in RFC-0005.

A Relationship is not an Entity — a relationship, as defined in RFC-0006, is the connection between two entities, not a third entity in its own right. A Boundary is not a Relationship — a boundary defines the limit of a single entity's responsibility, while a relationship defines how two entities' distinct responsibilities connect.

The closeness of a relationship is never evidence that the boundary between the related entities should be dissolved. If anything, the entities most tightly connected are the ones for which boundary discipline matters most, since it is precisely these pairs that are most tempting to collapse into one.

A useful test for boundary separation is to ask whether one entity could change substantially while the other remained entirely unaffected in its own defined responsibility. Knowledge can be reorganized, corrected, or expanded without Memory's preserved record changing at all; Memory can gain or lose specific preserved experiences without Knowledge's existing organization becoming invalid. That each can change independently of the other, within its own responsibility, is evidence the boundary between them is intact.

---

## 6. Boundary Crossing

Entities legitimately interact across boundaries, and this RFC does not prohibit such interaction — it only governs what that interaction may and may not do to the boundaries themselves.

Interaction occurs through canonical relationships. Whenever one entity's responsibility touches another's, that interaction is expressed using the vocabulary established in RFC-0006 — *owns*, *contains*, *organizes*, *informs*, *derives from*, *supports*, *produces*, or *references* — never through an unstated or informal connection.

Interaction never transfers responsibility. An entity that interacts with another, through any of the canonical relationships, does not thereby acquire any portion of that other entity's responsibility, nor surrender any portion of its own.

Influence does not erase boundaries. That Memory informs Identity does not mean Identity's boundary has expanded to include what Memory does, or that Memory's boundary has expanded to include Identity's continuity.

Support does not erase boundaries. That Workspace supports Projects does not mean Workspace has taken on responsibility for what a Project accomplishes.

Derivation does not erase boundaries. That Knowledge derives from Memory does not mean Knowledge's boundary now includes Memory's responsibility for preservation, or that Memory has inherited Knowledge's responsibility for organization.

---

## 7. Boundary Violations

The following are architectural anti-patterns that this RFC exists to prevent.

**One entity redefining another.** Where a document begins describing one entity in terms properly belonging to another's definition, it has violated that entity's boundary and must be corrected. This weakens the architecture by making an entity's true responsibility unclear to anyone reading its definition.

**Responsibility duplication.** Where the same responsibility appears to be claimed by two entities, the architecture has lost the exclusivity property described in Section 3. This weakens the architecture by creating ambiguity about which entity is actually answerable for a given concern.

**Implicit ownership.** Where one entity is treated as though it owns another without that ownership being explicitly established through the *owns* relationship, a boundary has been crossed without acknowledgment. This weakens the architecture by introducing authority relationships that cannot be traced to any canonical source.

**Implicit derivation.** Where one entity is treated as though it derives from another without that derivation being explicitly stated, the same problem arises in a different form. This weakens the architecture by obscuring the actual origin and dependency structure of the domain.

**Concept merging.** Where two distinct entities are gradually treated as interchangeable — as when Memory and Knowledge are used as though they mean the same thing — the boundary between them has effectively dissolved. This weakens the architecture by collapsing distinctions that were deliberately established for good reason.

**Semantic drift.** Where an entity's meaning gradually shifts through repeated informal use, without any deliberate revision, its boundary becomes unstable. This weakens the architecture by making the entity's definition a moving target rather than a fixed point of reference.

Each of these violations shares a common root: a boundary that was not treated as exclusive, stable, and canonical was allowed to erode instead. None of them typically occurs as a single deliberate act — they accumulate gradually, through small, individually reasonable-seeming accommodations, which is precisely what makes vigilance against them a constant responsibility rather than a one-time check.

---

## 8. Boundary Invariants

The following invariants must always hold:

- Every entity has one responsibility boundary.
- Responsibilities never overlap silently.
- Relationships never redefine boundaries.
- Boundaries survive implementation replacement.
- Boundaries are implementation-independent.
- Canonical definitions always take precedence.

These invariants are non-negotiable within the scope of this RFC. Any future architecture that would require violating one of them, however convenient in other respects, must be revised rather than accepted as an exception.

---

## 9. Boundary Evolution

Boundaries may become more precise over time, as the architecture matures and edge cases reveal where further clarity is needed. Boundaries may never become ambiguous — evolution in this model moves in one direction only, toward greater clarity, never toward vagueness.

Boundary evolution requires architectural justification: a clear account of why the existing boundary is insufficiently precise. It requires RFC approval, following the same process by which the boundaries established in this document were themselves approved. And it requires preservation of canonical definitions — a boundary may be sharpened or clarified, but the entities and relationships it separates must retain the meanings already established for them elsewhere.

Boundary changes must strengthen conceptual clarity. Never weaken it. A proposed boundary change that would make responsibility less clear, rather than more, does not qualify as boundary evolution under this RFC, regardless of what practical convenience it might offer.

---

## 10. Future Specialization

Future RFCs may define specialized boundaries for Projects, Skills, Runtime, Context, Sessions, and other concepts as they are introduced or further elaborated.

However, no future RFC may weaken the canonical boundary model established here. All specialization must preserve explicit responsibility separation, adding precision to how boundaries apply in specific cases without eroding the exclusivity, stability, and implementation-independence that this RFC establishes as fundamental to what a boundary is within CreatorOS.
