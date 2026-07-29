# RFC-0000: Documentation Architecture

- **Status:** Accepted
- **Author:** Architecture Board
- **Scope:** The structure of the CreatorOS repository itself

This RFC is not a product RFC. It does not concern creators, identity, memory, or any other domain concept. Its subject is the documentation system of CreatorOS itself: how the repository is organized, how its documents relate to one another, and how architectural authority flows through it.

---

## 1. Context

CreatorOS is an architecture-first project. Its repository is not a place where implementation happens to be described — it is the canonical source of truth that every implementation is built against.

Because of this, the documentation system is not a separate concern layered on top of the architecture. It is part of the architecture. How documents are organized, how authority is assigned between them, and how concepts are defined and referenced are themselves architectural decisions, subject to the same rigor as any other. A repository that gets its documentation architecture wrong will drift, regardless of how sound its other decisions are, because drift enters through ambiguity about where the true answer lives.

---

## 2. Problem

Without an explicit documentation architecture, a repository accumulates a familiar set of failures. Definitions scatter across multiple documents, each written in good faith, each slightly different from the others. Authority becomes unclear — when two documents disagree, nothing indicates which one is correct. Documents mix registers that should stay separate: philosophy bleeds into governance, governance bleeds into implementation detail, and the resulting text serves no single purpose well.

The result is architectural drift, not through any single bad decision, but through the slow accumulation of small inconsistencies that nothing was structured to catch. A documentation system with clear hierarchy, clear scope per document, and a firm rule about canonical definitions prevents this class of failure before it starts, rather than correcting it after the fact.

---

## 3. Document Hierarchy

Each major document in this repository answers a distinct question, at a distinct level of authority, and must not contain what belongs to another.

**MANIFESTO** answers *why CreatorOS exists*. It must not contain governance, constraints, or implementation guidance. Its authority is the highest in the repository — everything else must be consistent with it, and it changes least often.

**CONSTITUTION** answers *what may never be compromised*. It must not contain guidance for choosing between valid options, or explanation of purpose — those belong elsewhere. Its authority is second only to the Manifesto: no architecture, principle, or decision may contradict it.

**PRINCIPLES** answers *how to choose between valid architectural options*. It must not define immutable constraints — that is constitutional territory — and must not describe implementation techniques. Its authority operates entirely within constitutional boundaries.

**VISION** is introduced as a document category by RFC-0010, at the hierarchy position established there. RFC-0011 defines Vision's architectural role, responsibilities, boundaries, relationships, and evolution — it does not redefine Vision's position in this hierarchy or the Authority Model this hierarchy expresses.

**AGENTS** answers *how work is performed within this repository*. It must not introduce architecture, philosophy, or product concepts; its subject is process and role, not substance.

**RFC** answers *what architectural change is being proposed and why*. It must not record a decision as though it were already settled, and must not contain implementation code. Its authority is provisional until it results in acceptance.

**ADR** answers *what has been decided, in a single, specific instance*. It must not contain open discussion or alternatives still under consideration — that belongs in the RFC that preceded it. Once accepted, an ADR is not edited; it is superseded.

**Documentation** (the general body of supporting material, guides, and references) answers *how existing, already-decided architecture is explained and navigated*. It must not introduce new concepts or decisions of its own. Its authority is subordinate to every document above it.

Authority decreases in the order listed. A document lower in this list may explain, elaborate, or reference what a higher document establishes — it may never redefine or contradict it.

---

## 4. Canonical Source Rule

Every architectural concept in CreatorOS has exactly one canonical source: the single document where it is properly defined.

All other documents that need to use the concept reference that canonical source rather than restating the definition in their own words. A second, independent definition of the same concept — however similar to the first — is not a convenience. It is the seed of a future contradiction, because the two definitions will not necessarily be updated together, and once they diverge there is no way to tell which is authoritative.

Where a concept appears to require redefinition to fit a new document, the correct response is to revisit and, if necessary, formally revise the canonical source — not to create a second one.

---

## 5. RFC Policy

RFCs exist to propose architectural change. An RFC records a proposal under discussion, not a decision already made — its purpose is to make the reasoning behind a potential change visible and reviewable before that change is adopted.

RFCs must be stable once numbered. An RFC's number and title, once assigned, are not reused or reassigned, even if the RFC is ultimately rejected — the record of the proposal having existed is itself part of the repository's history. RFCs must be easy to reference: a specific, stable identifier that other documents can point to without ambiguity.

An RFC does not, by itself, authorize implementation. It authorizes further architectural discussion, and, where accepted, the creation of the ADR or ADRs that formally record the resulting decision.

---

## 6. ADR Policy

ADRs record decisions that have already been made. Where an RFC is exploratory and open to revision during discussion, an ADR is a closed, specific statement of what was decided, why, and with what consequences.

The distinction is one of state, not subject matter: the same architectural question can pass through both. It begins as an RFC, where alternatives are considered and discussion occurs. Once the Architecture Board reaches a decision, that decision is recorded as one or more ADRs, each addressing a single, specific choice.

Use an RFC when a question is still open and reasoning needs to be shared before a decision is reached. Use an ADR when a decision has already been reached and needs to be recorded permanently and unambiguously.

---

## 7. Naming and Numbering

Documents in this repository are named and numbered for stable, predictable reference, not for aesthetic preference.

RFCs are named `RFC-NNNN-Short-Title.md`, using a zero-padded, sequential four-digit number assigned in the order the RFC is created. ADRs follow the equivalent pattern already established for that directory: `NNNN-short-title.md`, sequential and zero-padded.

Numbers are never reused. A rejected or withdrawn RFC keeps its number; the next RFC created takes the next number in sequence, regardless of what became of the ones before it. This guarantees that a reference to `RFC-0000`, made at any point in the repository's history, always resolves to the same document.

Naming exists to serve navigation and canonical reference above all else. A name should let a reader locate and cite a specific document without needing to search or guess.

---

## 8. Repository Navigation

A new contributor, human or otherwise, should read this repository in the order its authority is established, not in whatever order files happen to be encountered.

The recommended path begins with the root `README.md`, for orientation, followed by `MANIFESTO.md`, to understand why CreatorOS exists. From there, `CONSTITUTION/CONSTITUTION.md` establishes what may never be compromised, and `PRINCIPLES/PRINCIPLES.md` establishes how choices are made within that boundary. `VISION/README.md`, the category introduced by RFC-0010, follows next. `AGENTS.md` explains how work is actually performed. Only after this foundation should a contributor proceed to `RFC/` and `ADR/`, where the specific architectural decisions built on top of that foundation are recorded, and finally to `docs/` for supporting material.

This order is not arbitrary. It mirrors the authority hierarchy defined in Section 3: a reader who understands the highest-authority documents first will correctly interpret everything that follows.

---

## 9. Change Control

Documentation-level change in this repository is itself governed by the hierarchy it defines.

Higher-authority documents control lower-authority ones: a change to the Constitution can require corresponding revision of Principles, RFCs, or ADRs that depended on the prior constitutional state, but never the reverse. A lower-authority document may never be used to justify a change to a higher one.

Any change that alters a concept's canonical definition, or that alters the hierarchy or authority relationships described in this RFC, requires explicit architectural approval through the same process by which this RFC itself was approved. Such changes are not editorial — they are architectural, and must be treated with the same deliberation as any other decision recorded in this repository.
