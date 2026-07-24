# CreatorOS Architecture Strategy

## Document Status

| Attribute | Value |
|-----------|-------|
| Classification | Strategic Architecture Document |
| Status | Living |
| Owner | Architecture Board |
| Scope | Strategic evolution of CreatorOS |
| Review Cycle | Updated after each major architectural milestone |

Among the repository's governing documents, this is the only strategic document intentionally expected to evolve throughout the project's lifetime — where the Manifesto, Constitution, and Principles are built to remain valid indefinitely without revision, this document is designed to be updated as the project advances through its phases.

- **Status:** Living document
- **Author:** Architecture Board
- **Scope:** The strategic evolution of CreatorOS architecture, from concept to implementation

This document is not an RFC. It is not repository documentation in the sense of `docs/`, and it is not a technical specification. It is the canonical strategic document describing how CreatorOS evolves from vision to implementation, and it serves as the primary orientation document for architects, engineers, contributors, and AI assistants entering this repository at any point in its history.

It answers three questions: what is being built, why it is being built this way, and where the project currently stands in that journey.

---

## 1. Purpose

The role of this document is orientation. Where the Manifesto explains why CreatorOS exists, the Constitution defines what may never be compromised, the Principles guide architectural judgment, and the RFCs record specific architectural decisions, this document ties all of them together into a single account of the project's trajectory — what has been established, what is being worked on now, and what remains ahead.

This document describes the strategic evolution of CreatorOS from concept to implementation. It does not introduce architecture of its own; it situates the architecture recorded elsewhere within a larger sequence, so that anyone arriving at this repository can understand not only what has been decided, but how those decisions fit into the project's overall progression.

This document is expected to evolve as the project advances. Unlike the Manifesto or Constitution, which are designed to remain valid indefinitely without revision, this document contains sections whose entire purpose is to track where the project currently stands — and those sections are expected to be updated as the project moves forward. Section 8 draws the distinction between what is expected to remain stable here and what is expected to change.

This document also serves a coordinating function that no single RFC or governance document is positioned to serve on its own. An RFC records a specific decision; the Constitution records what may never be compromised; the Principles record how to choose among valid options. None of these, individually, is meant to describe how all of these pieces fit together across time, or to say where the project stands relative to its full intended trajectory. This document exists to fill precisely that gap — to be the one place a reader can go to understand the whole arc of the project, rather than needing to reconstruct it from the accumulated set of individual decisions.

---

## Document Hierarchy

This document occupies a specific place within the repository's overall hierarchy of authority, connecting the purpose-level documents above it to the decision-level documents below it:

MANIFESTO

↓

CONSTITUTION

↓

PRINCIPLES

↓

ARCHITECTURE_STRATEGY

↓

RFC

↓

ADR

↓

TECH

↓

Implementation

This document does not replace any of these documents. It does not restate the Manifesto's purpose, the Constitution's constraints, or the Principles' guidance, and it does not record decisions in the way RFCs and ADRs do. Instead, it connects them into a coherent strategic progression — showing how the commitments established above it are carried forward into the specific decisions and technical work recorded below it, and where the project currently stands along that progression.

---

## Using This Document

Different readers arrive at this repository with different immediate needs, and this document is written to serve all of them without requiring any of them to read the entire repository before finding their footing.

**Architects** should use this document to understand the current phase of work, the lifecycle a proposed change must pass through, and where a new architectural concept fits relative to what has already been established as stable.

**Engineers** should use this document to understand why architecture precedes implementation in this project, and to identify which phase of the lifecycle current work belongs to, so that implementation is not attempted ahead of the architecture it depends on.

**Contributors** should use this document as an entry point for understanding the project's overall trajectory before engaging with any specific RFC, ADR, or technical specification — it provides the context that makes those individual documents easier to place correctly.

**AI assistants** should use this document consistently with the role and limits defined in `AGENTS.md`, treating it as an orientation document rather than as a source of new architectural authority, and should defer to the Constitution and Principles wherever this document's strategic framing and those documents' constraints might appear to diverge.

The recommended reading order for anyone new to this repository is:

1. Manifesto
2. Constitution
3. Principles
4. Architecture Strategy
5. Relevant RFCs
6. ADRs
7. Technical Specifications (when available)

This order exists because each document depends on the ones before it to be correctly understood. Reading the Constitution before the Manifesto risks encountering constraints without knowing the purpose they protect; reading RFCs before this document risks encountering individual decisions without the strategic context that explains how they fit into the project's overall progression. Following the order above ensures that each document is read with the foundation it assumes already in place.

---

## 2. Vision

CreatorOS is developed architecture-first. Every capability the project will ever have begins as an explicit architectural decision, recorded and reviewed before any implementation exists to realize it.

Architecture defines implementation. Implementation never defines architecture. This ordering is not a preference among equally valid alternatives — it is the foundational commitment this entire project is organized around, and every phase, process, and document described in this strategy exists to protect it.

The long-term vision is for CreatorOS to reach a state where its conceptual architecture is fully established, its technical architecture is fully specified in conformance with that conceptual foundation, and its implementation faithfully realizes both — with future evolution proceeding by extending this foundation rather than by redefining it. This document exists to track and guide the path toward that state.

This vision is deliberately paced rather than urgent. A project built architecture-first accepts a longer path to implementation in exchange for a foundation that does not need to be rebuilt once implementation begins. The strategy this document describes treats that trade as settled, not as something to be reconsidered under the pressure of any particular phase taking longer than initially expected.

---

## 3. Development Philosophy

The development of CreatorOS is governed by a small number of fundamental principles, distinct from the Architectural Principles established elsewhere but consistent with them, that shape how the project proceeds through each phase of its evolution.

**Architecture before code.** No implementation work begins until the architecture it depends on has been decided and recorded. This is not a matter of sequencing preference — it reflects the project's basic conviction that code written against undefined architecture produces systems that cannot be trusted to remain coherent.

**Conceptual stability.** Concepts, once established, are built to remain valid for a long time. The project favors spending the effort required to get a concept right at the architectural level over the alternative of revising it repeatedly as implementation reveals problems that architecture should have anticipated.

**Implementation independence.** Architecture is deliberately expressed in terms that do not depend on any particular technology, method, or tool. This allows the architecture to outlive any single implementation, and allows implementations to be replaced without requiring the architecture to be reconsidered.

**Incremental refinement.** The architecture is not expected to be perfect on first statement. It is expected to be refined deliberately, through the review processes this document describes, as understanding deepens and as new domain concepts require the existing foundation to be extended.

**Canonical definitions.** Every concept, relationship, and boundary has exactly one authoritative source. The project treats duplication of definitions as a structural risk, not a convenience, because divergent definitions are the earliest symptom of eventual architectural drift.

**Long-term maintainability.** Decisions are evaluated not only by whether they solve an immediate problem, but by whether they remain sound and understandable years later, to people who were not present when the decision was made.

These philosophies are not independent of one another; they reinforce a single underlying commitment. Architecture before code makes conceptual stability possible, because a concept defined ahead of implementation is defined on its own terms rather than shaped by whatever an early implementation happened to require. Implementation independence protects conceptual stability against a different threat — the temptation to treat a concept as settled only for as long as some particular technology remains convenient. Canonical definitions and incremental refinement work together: refinement is how the architecture improves, and canonical definitions are what keep that improvement from fragmenting into inconsistent, parallel versions of the same idea. Long-term maintainability is the outcome all the others are aimed at producing.

---

## 4. Architecture Lifecycle

CreatorOS architecture moves through a defined lifecycle, from initial vision through to realized implementation:

Vision

↓

Conceptual Architecture

↓

Domain Architecture

↓

Technical Architecture

↓

Implementation

**Vision** establishes why the project exists at all — the purpose, values, and long-term aspiration that give every subsequent stage its reason for being. This stage exists because no architecture, however well constructed, is meaningful without a clear account of what it is meant to serve.

**Conceptual Architecture** establishes the immutable constraints and guiding principles within which all further architecture operates — the Constitution and Principles that bound every decision that follows. This stage exists to fix the boundaries of what is negotiable before any specific domain concept is defined, so that domain work proceeds within known limits rather than discovering them after the fact.

**Domain Architecture** establishes the entities, relationships, and boundaries that make up the substance of what CreatorOS actually is — the vocabulary in which everything else will eventually be expressed. This stage exists to give the project a stable, precise language before any technical decision is made, so that technical decisions have something coherent to conform to.

**Technical Architecture** establishes how the domain architecture will be technically realized, at the level of structural and operational specification, without yet writing implementation itself. This stage exists to translate a stable conceptual language into a concrete technical plan, ensuring that translation is deliberate rather than improvised during implementation.

**Implementation** realizes the technical architecture in working form. This stage exists last, and only after the preceding four are sufficiently established, because implementation built without that foundation has nothing reliable to conform to, and tends to end up defining architecture retroactively — precisely the outcome this entire lifecycle exists to prevent.

Each stage in this lifecycle depends on the one before it being genuinely settled, not merely begun. A Domain Architecture built on a Conceptual Architecture that is still in flux inherits that instability, and a Technical Architecture built on an incomplete Domain Architecture will eventually need to be reworked once the missing domain concepts are finally defined. The lifecycle is sequential by necessity, not by convention — skipping ahead does not save time so much as defer the cost of the skipped stage to a point where it is more expensive to pay.

---

## 5. Project Phases

### Phase 1 — Vision

**Status: Completed.**

This phase established the foundational purpose documents of CreatorOS: the Manifesto, the Constitution, the Principles, and the initial documentation architecture governing how these and future documents relate to one another. It answered why CreatorOS exists and what may never be compromised in pursuing that purpose.

### Phase 2 — Foundation Architecture

**Status: Completed.**

This phase established the initial domain vocabulary of CreatorOS: the Core Domain model and its primary entities, along with the specializations of Identity, Memory, Knowledge, and Workspace, and the canonical Relationship and Boundary models that govern how these and future entities connect and remain distinct from one another.

Foundation is considered stable. It is not expected to be redefined by later phases; later phases are expected to build upon it, extending the vocabulary it establishes rather than revising the vocabulary itself.

### Phase 3 — Domain Architecture

**Status: Current phase.**

This phase extends the domain vocabulary to cover the remaining concepts required for a complete description of the CreatorOS domain: Project, Artifact, Skill, Context, Session, Lifecycle, State, Goal, Workflow, and Runtime.

This phase completes the domain language. Where Phase 2 established the stable core — the entities most central to the Creator's continuity — Phase 3 extends that core to cover the full range of concepts needed to describe purposeful work, capability, situational context, and the passage of time and state within CreatorOS, all while remaining consistent with the relationships and boundaries the Foundation phase already established.

### Phase 4 — Technical Architecture

**Status: Future phase.**

This phase's purpose is to translate the completed domain architecture into concrete technical specifications, describing how the concepts and relationships established in Phases 2 and 3 will be structurally and operationally realized — without yet constituting implementation itself.

Example technical specifications anticipated in this phase include: Repository structure, Services, Storage, Runtime, Plugins, Deployment, Persistence, and API design. This phase does not define specific technologies; it defines the structural and operational shape that any technology chosen must ultimately conform to.

### Phase 5 — Implementation

**Status: Future phase.**

Implementation begins only after technical architecture has been established. This ordering reflects the project's foundational commitment, restated throughout this document: implementation realizes what architecture has already defined, and does not itself originate architectural decisions.

---

## 6. Architecture Review Process

Every architectural change — whether extending the domain vocabulary, refining a boundary, or introducing new technical specification — proceeds through a defined review lifecycle:

Draft

↓

Architecture Review

↓

Cross-RFC Impact Review

↓

Accepted

**Draft** is the stage at which a proposed change is written out in full, in the form appropriate to its subject — typically as an RFC — laying out the reasoning, the proposed definitions, and their relationship to existing architecture.

**Architecture Review** evaluates the draft against the Constitution, Principles, and existing domain architecture, checking that it does not violate any established invariant, boundary, or canonical definition.

**Cross-RFC Impact Review** examines how the proposed change interacts with every other RFC already accepted, verifying that it does not create hidden contradictions, silent redefinitions, or duplicated concepts across the wider body of architecture.

**Accepted** is the final stage, reached only once both reviews are satisfied, at which point the change becomes part of the canonical architecture and is recorded accordingly, through the ADR or RFC-acceptance process already established elsewhere in this repository.

No change skips a stage in this lifecycle, regardless of how minor it may appear. A change that seems small enough to bypass Cross-RFC Impact Review is, more often than not, a change whose full consequences have not yet been traced — the review exists precisely to catch the cases that look small from the perspective of the single RFC being changed but are not small from the perspective of the architecture as a whole.

---

## 7. Current Project State

| Area | Status |
|------|--------|
| Vision | Complete |
| Foundation | Frozen |
| Domain Architecture | In Progress |
| Technical Architecture | Not Started |
| Implementation | Not Started |

**Current Phase.** The project is in Phase 3, Domain Architecture, actively extending the domain vocabulary beyond the entities established during the Foundation phase.

**Completed Milestones.** The Vision phase and the Foundation Architecture phase are both complete. The governing purpose documents, the core domain entities, and the canonical relationship and boundary models are all established and considered stable.

**Current Architecture Status.** The foundation of the domain — its most central entities and the rules governing how any entity may relate to or bound another — is settled and is not expected to be revised as later work proceeds. Work is currently focused on extending that foundation to describe purposeful work, capability, context, and state.

**Overall Progress.** The project has completed its purpose-setting and foundational conceptual work, and is in the middle portion of its conceptual domain work more broadly. Technical architecture and implementation remain ahead, and have not yet begun. Progress is best understood qualitatively, as steady advancement through a deliberately sequenced set of phases, rather than as a fixed proportion of a predetermined total.

A qualitative account is preferred over a numeric one deliberately. A percentage implies a precision about the total scope of the project that does not yet exist — the full extent of Phase 3 and the entirety of Phases 4 and 5 are not yet specified in enough detail to be measured against. What can be said reliably is which phases are behind the project, which phase it is currently in, and which phases remain ahead — and that is what this section reports.

---

## Next Milestone

**Current Objective.** Complete the Project domain model.

**Success Criteria.** Project entity approved through the Architecture Review Process.

**Next Planned Milestone.** Artifact domain model.

This section intentionally changes over time. It is expected to be updated as each milestone is reached, replacing the completed objective with the next one in sequence, consistent with the dynamic nature of this document described in Section 8.

---

## 8. Living Document

This document intentionally evolves. It is written to accommodate change in its account of the project's current standing, while remaining fixed in its account of the project's overall strategy and philosophy.

**Stable Sections.** Sections 1 through 4 and Section 6 — Purpose, Vision, Development Philosophy, Architecture Lifecycle, and the Architecture Review Process — describe the enduring shape of how CreatorOS is developed. These sections should almost never change, and any change to them should be treated with the same seriousness as a change to the Constitution or Principles.

**Dynamic Sections.** Sections 5 and 7 — Project Phases and Current Project State — describe where the project currently stands. These sections are expected to change throughout the life of the project, as phases complete, as new phases begin, and as the project's status shifts. Section 9, the Decision Log, is dynamic by design, growing over time as further milestones are recorded.

**Update Policy.** Stable sections change only through exceptional architectural review, applied with the same seriousness as a change to the Constitution or Principles. Operational sections change after major milestones, updated to reflect the phase and status the project has actually reached rather than the one anticipated at the time of the previous update. The Decision Log grows over time, with new entries added as milestones are reached and no existing entry removed or rewritten. Current State — the Next Milestone section and the status table and prose in Section 7 — is expected to evolve continuously, remaining the most frequently updated part of this document as the project advances.

---

## 9. Decision Log

This section records major architectural milestones as they occur. It is not populated retroactively beyond an initial example; future entries are added as milestones are reached.

**Milestone: Foundation Layer Frozen**

**Reason.** The Architecture Consistency Review of the Foundation phase — covering the Core Domain, Identity, Memory, Knowledge, Workspace, and the canonical Relationship and Boundary models — was completed, confirming that these concepts are coherent, mutually consistent, and ready to serve as a stable base for further work.

**Consequence.** Future RFCs build upon the established foundation rather than revising it. Any proposal that would require altering a Foundation-phase concept is treated as a change to the foundation itself, subject to the heightened scrutiny such a change warrants, rather than as an ordinary extension of the domain vocabulary.

---

## 10. Success Criteria

CreatorOS reaches architectural maturity when the following conditions are all satisfied.

**Conceptual architecture is complete.** The full domain vocabulary — entities, relationships, and boundaries — required to describe CreatorOS has been established, reviewed, and accepted, leaving no essential concept undefined.

**Technical architecture is complete.** The structural and operational specifications needed to realize the conceptual architecture have been fully defined, in conformance with every constraint the conceptual architecture establishes.

**Implementation conforms to architecture.** What has been built matches what has been architecturally specified, without unrecorded deviation, and any place where implementation could not satisfy architecture has been resolved by correcting the implementation or by deliberately revising the architecture through the established review process.

**Future evolution occurs without redefining the foundation.** Once these conditions are met, further growth of CreatorOS proceeds by extending its established architecture — adding to the vocabulary, refining boundaries with greater precision, specifying further technical detail — without requiring the foundation itself to be redefined or contradicted.

This document will be updated to reflect progress toward these criteria as each phase of the architecture lifecycle advances.
