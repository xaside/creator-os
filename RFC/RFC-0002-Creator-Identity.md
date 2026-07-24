# RFC-0002: Creator Identity

- **Status:** Accepted
- **Author:** Architecture Board
- **Scope:** Specializes the Identity entity introduced in RFC-0001

This RFC does not redefine the core domain model established in RFC-0001. It specializes one entity from that model — Identity — describing its boundaries, invariants, and relationships to the rest of the domain in greater depth.

---

## 1. Purpose

Identity is the continuous thread of the Creator across time. It is what remains coherent while everything else changes: the implementations that support the Creator, the outputs the Creator produces, and the contexts in which the Creator operates.

The purpose of this RFC is to give Identity a precise architectural definition — one specific enough to guide decisions about what may and may not be treated as identity, and stable enough to remain valid regardless of how CreatorOS is eventually implemented.

---

## 2. Conceptual Definition

Identity is the continuous coherence of a Creator: the thread that makes a body of experience, expression, and work recognizably one Creator's, across time and across change.

Identity is not Memory. Memory is preserved experience; Identity is the continuity that experience contributes to, not the experience itself.

Identity is not Knowledge. Knowledge is organized understanding; Identity is what persists independently of how well or how much is understood at a given time.

Identity is not Skill. A Skill is a capability the Creator can exercise; Identity is not defined by any capability, nor lost if a capability changes or disappears.

Identity is not Output. Output is what a Creator produces at a given moment; Identity is not reducible to any output, nor is it invalidated by output that varies over time.

Identity is not Artifact. An Artifact is a durable result; Identity is not stored within any artifact, nor dependent on any artifact's continued existence.

Identity is not Implementation. No mechanism used to support, express, or record the Creator constitutes Identity itself. Identity is what the implementation exists to serve, not a property of the implementation.

---

## 3. Properties of Identity

Identity has the following essential properties.

**Continuity.** Identity does not begin anew at each moment; it extends forward from what came before, in an unbroken thread.

**Coherence.** Identity holds together as a recognizable whole. It is not a mere sequence of disconnected states, but a continuity that can be understood as belonging to one Creator.

**Persistence.** Identity endures through time and through change in what surrounds it, rather than being tied to any single moment, context, or supporting mechanism.

**Intentional evolution.** Identity is capable of change, but only change that is deliberate. It is not static, but its movement is chosen, not accidental.

**Canonical reference.** Identity, like every concept in this domain model, has exactly one canonical definition and one authoritative reference point. It is not redefined independently by whatever happens to be interacting with it at a given time.

**Belonging to exactly one Creator.** Identity is never shared, split, or held jointly. Each Creator has one Identity, and each Identity belongs to exactly one Creator.

---

## 4. Identity and Change

Identity is capable of evolving without losing continuity. A Creator's perspective, values, or expression can shift, sometimes substantially, while Identity remains intact — provided the change is genuinely the Creator's own, rather than something that happened to the Creator as an incidental effect of something else.

Accidental drift is not identity evolution. A change that occurs as a side effect of implementation behavior, technical limitation, or unexamined process is not the Creator evolving — it is a failure to preserve continuity, and must be recognized as such rather than mistaken for growth.

Identity changes must be explicit and deliberate. Where Identity evolves, that evolution should be attributable to a real, intentional shift, not inferred after the fact from a difference in observed behavior. The absence of an identifiable, deliberate cause for a change is itself evidence that continuity has been broken rather than extended.

---

## 5. Identity and Memory

Memory informs Identity without replacing it. What a Creator has experienced and preserved contributes to the continuity that Identity represents, but Identity is not simply the sum of remembered experience.

Remembered experience does not automatically become identity. Something can be preserved in Memory — recorded, retained, available for reference — without thereby becoming part of what defines the Creator's continuity. Memory is broader and more inclusive than Identity; not everything worth remembering is identity-defining.

The boundary here is between what has been experienced and what is continuous. Experience is the raw material Memory preserves; continuity is the thread that Identity maintains through and across that material. Identity draws on Memory, but is not equivalent to it, and a change in what is remembered does not, by itself, constitute a change in Identity.

---

## 6. Identity and Knowledge

Knowledge may reflect Identity but does not define it. The organized understanding a Creator has accumulated can reveal something about who the Creator is, but Identity does not derive its continuity from that understanding.

Knowledge can support the interpretation of Identity — it can help make sense of why a Creator holds certain values or approaches things in a certain way — but Identity remains primary. Where Knowledge and Identity appear to diverge, Identity is not adjusted to match whatever the current state of Knowledge suggests; instead, the divergence itself is worth examining, since Knowledge is expected to evolve in ways that Identity's continuity is not.

---

## 7. Identity and Output

Output may express Identity without constituting it. What a Creator produces at any given time can be a genuine expression of who the Creator is, shaped by their continuity, values, and perspective — but the output is not itself the source of that continuity.

Artifacts can reflect Identity, but they do not create it. An Artifact might be an accurate and meaningful expression of a Creator's Identity at the time it was produced, yet Identity does not depend on that Artifact's existence, accuracy, or persistence. Identity precedes and outlasts any single output; no output, however representative, is a substitute for the continuity that produced it.

---

## 8. Identity Boundaries

Identity does not control implementation, storage, runtime, or presentation. These are matters of how CreatorOS is built and operated, and Identity's definition does not extend into them.

Identity is conceptually stable and implementation-independent. It is defined entirely at the level of the domain model, without reference to any mechanism by which it might eventually be supported. A future decision about how Identity is technically supported must conform to the definition given here — the definition does not adjust to accommodate whatever a given implementation finds convenient.

This boundary exists precisely so that Identity can survive any number of implementation changes without itself needing to change. An architecture that ties Identity's definition to a specific technical mechanism has violated this boundary, regardless of how well that mechanism currently functions.

---

## 9. Identity Invariants

The following invariants must always hold:

- Each Creator has exactly one Identity.
- Identity is continuous.
- Identity changes only deliberately.
- Identity is never reset implicitly.
- Identity survives implementation replacement.

These invariants are non-negotiable within the scope of this RFC. Any future architecture, however useful in other respects, that would require violating one of these invariants must be revised rather than accepted as an exception.

---

## 10. Future Specialization

Later RFCs may elaborate further on Identity — for instance, describing in greater depth how Identity relates to specific mechanisms of continuity, or how intentional evolution is recognized and distinguished from drift in particular circumstances.

Such future RFCs may add detail and refinement, but they may not change the canonical meaning of Identity established here. Where a future RFC appears to require a different definition of Identity than the one given in this document, the correct response is to revise this RFC directly, through the same deliberate process by which it was accepted — not to allow a competing definition to stand alongside it.
