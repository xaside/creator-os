# RFC-0006: Relationship Model

- **Status:** Accepted
- **Author:** Architecture Board
- **Scope:** Establishes the canonical relationship vocabulary connecting entities defined in RFC-0001 through RFC-0005

This RFC does not introduce new domain entities. It defines the relationships that connect the entities already established — Creator, Identity, Memory, Knowledge, Workspace, Project, Skill, and Artifact — and becomes the canonical vocabulary for expressing relationships throughout the architecture.

---

## 1. Purpose

CreatorOS requires a canonical relationship model because architecture consists not only of entities, but of the relationships between them. A domain model that defines its entities precisely while leaving their relationships to informal, ad hoc language has only completed half its work — the connections between concepts carry as much meaning as the concepts themselves, and left unspecified, they become a source of ambiguity that no amount of precise entity definition can compensate for.

Relationships are first-class architectural concepts. They are not incidental descriptions added when convenient; they are defined, named, and constrained with the same rigor as the entities they connect. This RFC establishes that vocabulary so that every future document, regardless of what it specializes, expresses relationships in the same precise terms.

---

## 2. Conceptual Definition

A Relationship expresses a stable semantic connection between domain entities. It states, precisely and durably, how one entity stands in relation to another — not as a technical association, but as a fact about the architecture itself.

Relationships are conceptual. They exist at the same level of abstraction as the entities defined in RFC-0001 and specialized in the RFCs that followed it, independent of anything used to eventually realize them.

Relationships are not implementation mechanisms. Whatever technique might eventually be used to make a relationship operative is a separate concern, governed by later, implementation-facing decisions, not by this RFC.

Relationships are not references. A reference, in the technical sense, is a mechanism for locating one thing from another; a relationship, as defined here, is a semantic fact that may or may not eventually be supported by such a mechanism.

Relationships are not pointers. A pointer is a technical artifact with no inherent meaning beyond indicating location; a relationship carries specific, canonical meaning regardless of how — or whether — it is technically realized.

Relationships are not storage structures. How entities and their connections might eventually be recorded is entirely outside the scope of this RFC, which addresses only what the relationships mean.

---

## 3. Properties of Relationships

Relationships, as defined in this model, share the following essential properties.

**Semantic.** A relationship carries specific, meaningful content about how two entities stand in relation to one another — it is not a neutral or empty association.

**Explicit.** A relationship is stated, not inferred. Two entities are never understood to be related simply because they are discussed together or happen to co-occur.

**Directional.** A relationship, unless stated otherwise, has a specific direction — one entity stands in a particular relation to another, and reversing the two does not automatically preserve the same meaning.

**Stable.** A relationship's meaning does not change from one use to the next. Once defined, a relationship type means the same thing everywhere it is applied throughout CreatorOS.

**Implementation-independent.** A relationship's meaning holds regardless of how, or whether, it is technically realized. No implementation detail can alter what a relationship means at the architectural level.

**Canonical.** Each relationship type defined in this RFC has exactly one meaning, established here, that all future documents must reuse rather than reinterpret.

---

## 4. Canonical Relationship Types

The following relationship types constitute the canonical vocabulary for expressing connections between entities in CreatorOS.

### owns

**Definition.** *owns* expresses responsibility and authority: the owning entity holds ultimate responsibility for, and authority over, the owned entity.

**Meaning.** Where one entity owns another, the owned entity's standing within the architecture is answerable to the owner. Ownership is a strong, specific relationship, reserved for cases where this responsibility and authority genuinely exist.

**What it does not imply.** *owns* does not imply containment, organization, or derivation. Ownership does not mean the owner physically or structurally holds the owned entity, only that it bears responsibility and authority for it.

**Examples.** Creator owns Identity.

---

### contains

**Definition.** *contains* expresses conceptual containment: the containing entity encompasses the contained entity as part of its scope.

**Meaning.** Where one entity contains another, the contained entity exists within the conceptual boundary of the container. Containment describes scope, not authority or responsibility.

**What it does not imply.** *contains* does not imply ownership. A Workspace containing a Project does not thereby hold responsibility or authority over the Creator's activity within that Project — containment is scopal, not custodial.

**Examples.** Workspace contains Projects.

---

### organizes

**Definition.** *organizes* expresses structural organization without ownership: the organizing entity arranges and structures the organized entity, without holding authority over it or encompassing it as a matter of scope.

**Meaning.** Where one entity organizes another, it provides structure, arrangement, and navigability, but does not thereby claim ownership or strict conceptual containment.

**What it does not imply.** *organizes* does not imply containment, and it does not imply ownership. An entity can be organized by something that neither contains it in the strict conceptual sense nor holds responsibility for it.

**Examples.** Workspace organizes Artifacts.

---

### informs

**Definition.** *informs* expresses influence without control: the informing entity shapes or contributes to the informed entity, without determining or governing it.

**Meaning.** Where one entity informs another, it contributes relevant content or context that the informed entity may draw upon, but the informed entity retains its own distinct nature and is not reducible to what informs it.

**What it does not imply.** *informs* does not imply derivation, ownership, or control. An entity that informs another remains entirely distinct from it, and the informed entity is not defined by what informs it.

**Examples.** Memory informs Identity. Knowledge informs Skills.

---

### derives from

**Definition.** *derives from* expresses conceptual derivation: the deriving entity is built or produced from the entity it derives from, using it as foundational material.

**Meaning.** Where one entity derives from another, its existence depends on, and is constructed from, the entity that precedes it. Derivation describes a genetic or foundational relationship, not mere influence.

**What it does not imply.** *derives from* does not imply that the derived entity is identical to, or interchangeable with, its source. Derivation describes origin, not equivalence.

**Examples.** Knowledge derives from Memory.

---

### supports

**Definition.** *supports* expresses enablement: the supporting entity makes possible, sustains, or facilitates the supported entity's function, without governing or controlling it.

**Meaning.** Where one entity supports another, its role is enabling — providing what is needed for the supported entity to function or persist, without directing what that function or persistence consists of.

**What it does not imply.** *supports* does not imply control. An entity that supports another is not thereby entitled to direct or determine it.

**Examples.** Workspace supports Projects. Knowledge supports Skills.

---

### produces

**Definition.** *produces* expresses intentional creation: the producing entity brings the produced entity into existence through deliberate action.

**Meaning.** Where one entity produces another, the produced entity's existence is the direct, intended result of the producer's activity. Production is a stronger relationship than mere influence or support — it denotes origination.

**What it does not imply.** *produces* does not imply ongoing ownership or continued control after the point of creation. Production describes origination, not an enduring relationship of authority.

**Examples.** Creator produces Artifacts.

---

### references

**Definition.** *references* expresses explicit conceptual reference: one entity points to or cites another as relevant, without any further claim about their relationship.

**Meaning.** Where one entity references another, it acknowledges a connection worth noting, without asserting ownership, containment, organization, derivation, support, or production.

**What it does not imply.** Reference does not imply ownership. Reference does not imply containment. Reference does not imply derivation. *references* is deliberately the weakest relationship in this vocabulary, and must not be used as a substitute for a more specific relationship where a more specific one actually applies.

---

For every relationship in this vocabulary, a definition, its precise meaning, what it explicitly does not imply, and representative examples are provided above. Future documents must draw their relationship language from this section rather than introducing informal alternatives such as "linked to," "connected with," "associated with," "related to," or "belongs with" — none of which carries the precision this architecture requires.

---

## 5. Relationship Composition

Relationships compose to describe the architecture as a whole, without altering one another's individual meaning.

Consider the following sequence: Creator owns Identity. Identity is informed by Memory. Knowledge derives from Memory. Workspace contains Projects. Projects produce Artifacts.

Read together, these relationships describe a coherent picture of how the Creator's continuity, preserved experience, organized understanding, active work, and durable outputs stand in relation to one another. But each relationship in the sequence retains exactly the meaning defined for it in Section 4 — composing several relationships into a larger picture does not permit any one of them to be read more loosely, or to borrow meaning from its neighbors.

Composition must not change the meaning of the individual relationships. A chain of relationships does not create a new, implicit relationship between its endpoints unless that relationship is separately and explicitly stated. That Knowledge derives from Memory, and Memory informs Identity, does not by itself establish any direct relationship between Knowledge and Identity — such a relationship, if it exists, must be stated on its own terms.

---

## 6. Relationship Constraints

The following constraints govern how relationships may be used and combined.

One relationship cannot silently imply another. Each relationship type defined in Section 4 stands entirely on its own; asserting one does not automatically assert any other, however commonly they might co-occur in practice.

*contains* does not imply *owns*. Conceptual containment describes scope; it says nothing about responsibility or authority.

*references* does not imply *derives from*. Citing another entity as relevant does not establish that one was built from the other.

*supports* does not imply *controls*. Enabling something does not grant authority to direct it.

*organizes* does not imply *contains*. Providing structure and arrangement does not, by itself, establish that the organizing entity encompasses the organized one as a matter of conceptual scope.

Relationships must never be inferred merely because two entities frequently appear together. Co-occurrence in discussion, documentation, or practice is not evidence of a relationship; a relationship must be explicitly asserted, using the vocabulary defined here, before it may be treated as part of the architecture.

---

## 7. Relationship Invariants

The following invariants must always hold:

- Every relationship has one canonical meaning.
- Relationship semantics never depend on implementation.
- Relationships are directional unless explicitly stated otherwise.
- Relationships never redefine entity boundaries.
- Relationships survive implementation replacement.

These invariants are non-negotiable within the scope of this RFC. Any future architecture that would require violating one of them, however convenient in other respects, must be revised rather than accepted as an exception.

---

## 8. Relationship Evolution

New relationship types may be introduced where genuinely needed, but only under the following conditions.

A new relationship type requires architectural justification: a clear account of why the existing vocabulary is insufficient to express the connection in question. It requires non-overlap with existing relationships: a proposed relationship that duplicates the meaning of *owns*, *contains*, *organizes*, *informs*, *derives from*, *supports*, *produces*, or *references* is not a new relationship, and should not be introduced as one. It requires a canonical definition, given with the same precision as those in Section 4 — a definition, its meaning, what it does not imply, and examples. And it requires approval through the RFC process, in the same manner by which this RFC itself was approved.

Existing relationship meanings may not drift over time. A relationship type's definition, once established, is fixed unless this RFC itself is formally amended; it does not gradually shift in meaning through informal reinterpretation across later documents.

---

## 9. Future Specialization

Future RFCs may introduce specialized relationships for particular domains, where a genuine architectural need for additional precision exists and the conditions in Section 8 are satisfied.

However, no future RFC may redefine *owns*, *contains*, *organizes*, *informs*, *derives from*, *supports*, *produces*, or *references*. These eight relationship types are the canonical relationship vocabulary for CreatorOS, and their meanings, as established in this document, are the fixed foundation on which any further specialization must build.
