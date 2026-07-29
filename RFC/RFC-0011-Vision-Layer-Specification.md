# RFC-0011: Vision Layer Specification

- **Status:** Accepted
- **Author:** Architecture Board
- **Scope:** Specializes the Vision document category introduced by RFC-0010

This RFC does not introduce Vision as a document category; RFC-0010 already did so. This RFC specializes Vision within the existing CreatorOS documentation architecture, defining its purpose, responsibilities, structure, boundaries, relationships, allowed and prohibited content, non-goals, invariants, lifecycle, and evolution.

This RFC does not modify the Manifesto, the Constitution, the Principles, RFC-0000, RFC-0010, AGENTS, Architecture Strategy, the AI Operating Manual, or the Authority Model those documents establish. Where anything in this RFC appears to conflict with one of them on a matter outside Vision's specialization, those documents govern.

---

## 1. Purpose

Vision exists to answer one architectural question that no other document category answers: what CreatorOS's product is for, and what it is meant to become, independent of why the project exists at all, how architectural decisions are made, and what has already been decided.

The Manifesto answers why CreatorOS exists, at the level of philosophy and continuity. The Constitution answers what may never be compromised. The Principles answer how to choose among valid architectural options. Architecture Strategy answers where the project's architecture currently stands and how it got there. RFCs and ADRs answer what has been proposed and decided. None of these is the place for the enduring, product-level account of what CreatorOS is building toward and for whom — that account would otherwise leak into whichever of these documents is nearest at hand, duplicating and destabilizing them in the process.

Vision is the canonical document category responsible for holding that account, so that no other category has to.

---

## 2. Authority and Hierarchy Position

RFC-0000 already defines document precedence and conflict resolution; RFC-0010 established Vision's position within that hierarchy, between Principles and AGENTS. This RFC does not modify that position and does not modify the Authority Model RFC-0000 expresses.

Hierarchy position establishes authority and conflict-resolution precedence only. It does not, by itself, establish semantic inheritance, derivation, dependency, or architectural influence between Vision and any other category. Those relationships are not inferred from Vision's position in the list — they are defined explicitly, and only, in Section 7 of this RFC.

---

## 3. Responsibilities

Vision SHALL be responsible for:

- long-term product direction;
- the enduring identity of the product, as experienced by creators;
- intended outcomes for creators and other stakeholders the product serves;
- ecosystem perspective — how CreatorOS's product relates to the broader environment, people, and systems it operates within;
- enduring product goals that remain stable across implementation cycles;
- product-level philosophy, as it applies to product decisions rather than to the project's existential purpose;
- strategic intent that informs, without dictating, future architecture.

Vision SHALL NOT be responsible for governance, architectural decision-making, or execution. Those responsibilities remain exactly where they already reside — in the Constitution, the Principles, RFC, ADR, and Architecture Strategy, respectively.

---

## 4. Scope

This RFC defines the complete architecture of the Vision document category. It does not define, and does not require changes to, the categories it specializes Vision in relation to.

Acceptance of this RFC does not require any change to the Manifesto, the Constitution, the Principles, RFC-0000, RFC-0010, AGENTS, Architecture Strategy, the AI Operating Manual, or the RFC or ADR lifecycles.

---

## 5. Vision Structure

Vision is a document category rather than a single mandatory document. The Vision category MAY contain one or more documents.

Each document within the Vision category SHALL address a distinct aspect of product vision. Collectively, these documents form the canonical Vision Layer.

Documents within Vision SHALL remain mutually consistent. The category, taken as a whole, SHALL present a coherent product vision; no document within it may state a product direction that contradicts another.

---

## 6. Boundaries

**Vision answers** what the product is for, what it is meant to become, and whom it is meant to serve.

**Vision never answers** why CreatorOS exists as a project (Manifesto), what may never be compromised (Constitution), how to choose among valid architectural options (Principles), what the current state of the architecture is (Architecture Strategy), what change is being proposed (RFC), or what has been decided (ADR).

**Architecture Strategy answers** how CreatorOS's architecture evolves from concept to implementation, and where the project currently stands in that progression.

**Principles answer** how to choose among multiple valid architectural options.

**RFCs answer** what architectural change is being proposed and why.

**ADRs answer** what has been decided, in a single, specific instance.

**Documentation answers** how already-decided architecture is explained and navigated, including, where applicable, how Vision's content is explained to readers.

No two of these categories answer the same question. Where a document appears to answer a question already answered elsewhere, it is out of scope for that document, regardless of category.

**Compatibility note.** The existing file `VISION/Mission.md` predates this RFC. Manifesto answers why CreatorOS exists; Vision answers what the product is for and what it is intended to become — the distinction established above and in Section 1 (Purpose). Following acceptance of this RFC, `VISION/Mission.md` SHALL be reviewed for consistency with the Manifesto and with this distinction; until that review occurs, its content SHALL NOT be treated as precedent for the Vision Layer.

---

## 7. Relationships

The descriptions below are specific to Vision's relationships with the other canonical document categories, as defined by this RFC. They do not constitute the canonical Document Relationship vocabulary anticipated by RFC-0009, which remains deferred to future work; the relationship types named here are local to this RFC and are not to be reused elsewhere as though they were canonical.

| Category | Constrains Vision? | Vision Informs It? | May Reference? | May Redefine? | May Override? | Relationship Type |
|---|---|---|---|---|---|---|
| Manifesto | Yes | No | Yes | No | No | Vision is bounded by Manifesto |
| Constitution | Yes | No | Yes | No | No | Vision is bounded by Constitution |
| Principles | Yes | No | Yes | No | No | Vision is bounded by Principles |
| AGENTS | No (governs process, not content) | No | Yes | No | No | Vision's editing process is governed by AGENTS |
| Architecture Strategy | No | Only where product direction is relevant | Yes | No | No | Architecture Strategy may reference Vision for product context; Vision is not a dependency of it |
| RFC | No | Yes | Yes | No | No | Vision informs RFC proposals |
| ADR | No | No (contextual only) | Yes | No | No | ADRs may reference Vision for contextual motivation only |
| Documentation | No | Yes | Yes | No | No | Vision is explained by Documentation |

Vision SHALL NOT redefine, and SHALL NOT override, any category listed above, regardless of the relationship type recorded for it.

**Architecture Strategy.** Architecture Strategy MAY reference Vision for product context. Architecture Strategy is informed by Vision only where product direction is relevant to the strategic account it gives; Vision SHALL NOT become a mandatory dependency of Architecture Strategy, and Architecture Strategy remains complete and valid without referencing Vision at all. The relationship is directional — Vision may inform Architecture Strategy — without implying coupling between the two documents' lifecycles.

**ADR.** ADRs MAY reference Vision for contextual motivation. Vision is not amended or governed through ADRs, and no ADR may alter Vision's content. The relationship is weak and contextual: an ADR may cite Vision to explain why a decision serves the product, but Vision's standing does not depend on any ADR referencing it, and no ADR's validity depends on Vision.

**Note on Architecture Strategy naming.** The term "Vision" also appears in `ARCHITECTURE_STRATEGY.md` as the name of a historical project phase (Section 4, Architecture Lifecycle; Section 5, Phase 1) in which the Manifesto, Constitution, and Principles were established. That usage predates this RFC and refers to a phase of project history, not to the Vision document category defined by RFC-0010 and this RFC. The two SHALL NOT be conflated; this RFC does not require `ARCHITECTURE_STRATEGY.md` to be amended to resolve the naming coincidence, but any future reader encountering both usages SHALL treat them as distinct.

---

## 8. Allowed Content

Vision documents MAY contain:

- statements of long-term product direction;
- descriptions of the product's enduring identity as experienced by creators;
- descriptions of intended outcomes for creators and other stakeholders;
- statements of ecosystem perspective;
- enduring product goals not tied to a specific technical implementation;
- product-level philosophy and values as they apply to product decisions;
- statements of strategic intent that inform, without dictating, future architecture;
- shared terminology used to describe the product consistently.

Vision MAY define terminology describing the product. Vision SHALL NOT redefine terminology that is already canonically defined elsewhere, including the domain terminology established by RFC-0001, RFC-0002, RFC-0003, RFC-0004, and RFC-0005. This preserves the Canonical Source Rule established by RFC-0000: where a concept already has a canonical definition, Vision references it rather than restating or redefining it.

---

## 9. Prohibited Content

Vision SHALL NOT contain:

- implementation;
- technical architecture;
- governance;
- coding standards;
- RFC decisions;
- ADR decisions;
- roadmaps;
- tasks;
- backlogs;
- execution plans;
- project management;
- operational procedures;
- process documentation.

**Compatibility note.** The existing file `VISION/Roadmap.md` predates this RFC. "Roadmaps," as prohibited above, refers to dated, task-based, or execution-level sequencing of work — the kind of content that belongs to Architecture Strategy, RFC, or operational planning, not to Vision. Following acceptance of this RFC, `VISION/Roadmap.md` SHALL be reviewed for conformance with this section; until that review occurs, its content SHALL NOT be treated as a precedent for what Vision documents may contain.

---

## 10. Non-Goals

Vision does not optimize for, and does not define, any of the following:

- delivery;
- implementation;
- prioritization;
- releases;
- scheduling;
- resource allocation;
- project management;
- execution;
- operational planning.

These concerns belong to Architecture Strategy, RFC, ADR, and operational documentation. Vision's silence on them is intentional, not an omission to be corrected by a future revision of Vision itself.

---

## 11. Architectural Invariants

The following invariants SHALL hold at all times:

- Vision SHALL remain product-oriented.
- Vision SHALL remain technology-independent.
- Vision SHALL NOT redefine the Manifesto.
- Vision SHALL NOT redefine the Constitution.
- Vision SHALL NOT redefine the Principles.
- Vision SHALL NOT replace Architecture Strategy.
- Vision SHALL NOT contain implementation decisions.
- Vision SHALL describe enduring product identity and intended future direction rather than execution.
- Vision SHALL NOT contain governance rules.
- Vision SHALL NOT record architectural decisions; architectural decisions are recorded only through RFC and ADR.
- Vision documents SHALL remain internally consistent; two Vision documents SHALL NOT state contradictory product direction.
- Vision SHALL remain consistent with the Manifesto, the Constitution, and the Principles at all times.
- Vision SHALL NOT be treated as authoritative for architectural conflict resolution beyond the precedence already established by RFC-0000.

---

## 12. Lifecycle

Vision changes when the Architecture Board determines that the enduring product-level intent of CreatorOS has genuinely shifted — not in response to routine product activity, individual features, or short-term execution changes.

The Architecture Board approves changes to Vision content. The Repository Maintainer MAY organize, edit for clarity, and correct inconsistencies within already-approved Vision content, consistent with the Maintainer Authority established in AGENTS.md, and MUST NOT introduce new product concepts or direction without approval.

Introducing a new Vision document, or changing stated product direction, identity, intended outcomes, or goals in a way that is not purely editorial, SHALL require RFC approval. Editorial clarity improvements, formatting, and correction of terminology already established elsewhere SHALL NOT require RFC approval.

Vision and Architecture Strategy remain independent documents. Architecture Strategy MAY reference Vision for product-level orientation; Vision's content does not automatically change when Architecture Strategy's current project state changes, and Architecture Strategy does not automatically change when Vision changes.

An RFC MAY reference Vision as motivating context. Vision's content is not altered by an RFC's acceptance unless that RFC explicitly amends Vision, following the same explicit-amendment convention RFC-0010 used to amend RFC-0000.

ADRs do not amend Vision. Vision is not a decision record and has no ADR-equivalent lifecycle state.

---

## 13. Evolution

Vision is expected to evolve as the product it describes evolves. Evolution SHALL be intentional and SHALL occur through the RFC process described in Section 12; unrecorded change to Vision's stated direction is drift, not evolution, consistent with the Constitution's treatment of evolution generally.

Where Vision's direction changes substantially, prior content SHOULD be superseded rather than silently deleted, preserving the historical record of what the product's direction previously was. Vision SHALL NOT be rewritten in place in a way that erases traceability of a prior stated direction.
