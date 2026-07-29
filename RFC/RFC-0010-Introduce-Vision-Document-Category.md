# RFC-0010: Introduce Vision Document Category

- **Status:** Draft
- **Category:** Governance
- **Author:** Architecture Board
- **Scope:** Introduces Vision as an official document category; does not define the Vision Layer itself, which is deferred to RFC-0011

---

## 1. Summary

This RFC introduces Vision as an official document category within CreatorOS. Vision becomes a first-class architectural document category alongside the existing repository document categories.

This RFC does not define the Vision Layer itself. This RFC only introduces the category into the repository architecture. The architecture of the Vision Layer is intentionally deferred to RFC-0011.

---

## 2. Motivation

CreatorOS currently defines the following document categories:

- Manifesto
- Constitution
- Principles
- AGENTS
- RFC
- ADR
- Documentation

Product context currently has no canonical architectural location. As a result, product-level information risks being distributed across multiple architectural documents, creating duplication, inconsistent ownership, and unclear responsibilities.

Introducing Vision as its own document category separates product context from architectural governance while preserving the existing Authority Model.

---

## 3. Scope

This RFC:

- introduces Vision as a document category;
- amends RFC-0000's Document Hierarchy;
- updates the canonical list of document categories;
- updates repository governance where necessary.

This RFC does not define:

- Vision semantics;
- Vision's architectural role;
- Vision responsibilities;
- Vision document structure;
- Vision relationships;
- Vision lifecycle.

Those are defined by RFC-0011. None of these topics include Vision's position within the Document Hierarchy or the Authority Model that hierarchy expresses; that position is established by this RFC and by RFC-0000, and is not redefined by RFC-0011.

---

## 4. Architectural Decision

CreatorOS SHALL recognize Vision as an official document category. Vision becomes part of the repository governance model. Vision exists as a peer document category alongside the existing architectural categories.

This RFC introduces the category only. No behavioral rules are introduced by this RFC.

---

## 5. Amendment to RFC-0000

RFC-0000 Section 3 (Document Hierarchy) is amended. The canonical list of document categories SHALL become:

- Manifesto
- Constitution
- Principles
- Vision
- AGENTS
- RFC
- ADR
- Documentation

RFC-0000 remains the canonical source defining document categories. RFC-0010 extends RFC-0000 rather than replacing it.

---

## 6. Repository Impact

Acceptance of this RFC requires repository-wide migration. Every document that enumerates document categories must be updated. This includes, but is not limited to:

- RFC-0000
- AGENTS
- repository indexes
- repository READMEs
- navigation
- diagrams
- hierarchy descriptions

After migration, every canonical hierarchy must contain Vision.

---

## 7. Authority

This RFC does not modify:

- Constitution
- Authority Model
- Principles
- RFC lifecycle
- ADR lifecycle
- Architecture Strategy

Only the set of document categories changes.

---

## 8. Backward Compatibility

Existing architectural documents remain valid. Existing governance remains valid. Existing RFCs remain valid. Existing ADRs remain valid.

This RFC introduces one additional document category without modifying existing authority relationships.

---

## 9. Future Work

RFC-0011 will define:

- purpose of Vision;
- Vision's architectural role;
- responsibilities;
- invariants;
- relationships;
- allowed content;
- prohibited content;
- evolution rules.

RFC-0010 intentionally leaves those questions unanswered. RFC-0011's definition of Vision's architectural role does not extend to Vision's position in the Document Hierarchy, which is established by this RFC and by RFC-0000.

---

## 10. Rationale

The CreatorOS architecture distinguishes between:

- philosophy;
- governance;
- architecture;
- implementation.

Product context is a distinct architectural concern. Creating a dedicated document category preserves Separation of Concerns while avoiding unnecessary authority expansion.

RFC-0010 introduces only the minimum architectural change required to establish Vision as a canonical document category.
