# CreatorOS Architectural Principles

## 1. Purpose

Principles guide architectural judgment. They exist for the situations the Constitution does not resolve on its own — the many points where more than one architectural choice would satisfy every constitutional constraint, and a decision must still be made.

Principles do not replace the Constitution. They operate entirely within its boundaries, never against them. Where a principle and a constitutional article appear to conflict, the article prevails and the principle is misapplied.

When multiple architectural choices are valid, Principles provide the basis for determining which one better serves CreatorOS. They are the reasoning tools used to choose well among options that are all, strictly speaking, permitted.

These Principles are not implementation guidelines, coding standards, or technical best practices. They say nothing about how a system should be built in a technical sense. They exist purely to inform architectural judgment — the recurring question of which of several permissible paths CreatorOS should take.

---

## 2. Continuity over Convenience

Prefer solutions that preserve long-term continuity, even when they require greater short-term effort.

Convenience is temporary. A convenient shortcut solves the problem in front of it and then disappears, leaving no lasting trace beyond whatever it cost the system's coherence. Continuity compounds — a decision that preserves it makes every subsequent decision easier to keep coherent as well, while a decision that sacrifices it for expedience leaves a debt that grows harder to repay the longer it is deferred.

Where a choice must be made between what is easiest now and what preserves coherence over time, the latter is preferred, deliberately and consistently.

---

## 3. Identity over Implementation

Architecture should preserve the creator's identity independently of any implementation used to express it.

Implementations may change — they are expected to, repeatedly, over the life of the system. Identity must remain coherent through all of it. An architecture that ties a creator's continuity to the survival of a particular implementation has confused the vessel for the thing it carries, and has built a fragility into the system that should not exist.

The test of any architectural decision touching identity is whether it would still make sense after every current implementation has been replaced. If it would not, the decision has not adequately separated identity from implementation.

---

## 4. Memory over Inference

When explicit knowledge exists, it has priority over generated or inferred knowledge.

Inference complements memory. It fills gaps where no explicit record exists, and it can be useful for that purpose. It never replaces memory where memory is available — a plausible inference is not an acceptable substitute for a recorded fact, no matter how convincingly it is produced.

Architectures should be built to prefer the recorded answer over the inferred one whenever both exist, and to treat inference as a fallback rather than a default.

---

## 5. Explicit over Implicit

Architectural intent should be documented and visible, not left to be inferred from behavior or convention.

Hidden assumptions create architectural drift. An assumption that is never written down cannot be checked, challenged, or consistently applied — it simply persists until someone acts against it without realizing a rule existed at all. Explicitness is what allows an architectural decision to be relied upon by people who were not present when it was made.

Where an architectural intention exists, it should be stated plainly, in a place others can find it, rather than left to be reconstructed from how the system happens to behave.

---

## 6. Composition over Monolith

Favor systems that can evolve through well-defined components rather than tightly coupled structures.

A system composed of distinct, well-bounded parts can change one part without requiring the rest to change with it. A system that is monolithic in structure resists this kind of evolution — any change risks touching everything, which makes every change more expensive and more dangerous than it needs to be.

The goal of this principle is adaptability, not fragmentation. Splitting a system into components has no value in itself; it has value only insofar as it makes the system easier to evolve deliberately over time.

---

## 7. Canonical Source

Every architectural concept has exactly one canonical definition.

Other documents reference that definition rather than redefining it. A concept explained twice, in two places, in two sets of words, is a concept waiting to diverge — the two explanations will not stay identical forever, and once they part ways there is no way to know which one is authoritative.

Avoid duplication. Avoid parallel terminology for the same idea. Where a concept must be discussed in a new document, the correct approach is to reference its canonical source, not to restate it in different language.

---

## 8. Replaceability

No implementation should become irreplaceable.

Architecture should outlive every implementation built to satisfy it. An implementation that cannot be replaced without threatening the architecture around it has become a liability disguised as an asset — its continued existence is no longer a choice but a dependency the system cannot escape.

Replaceability is a design objective rather than an emergency response. It is planned for from the outset, not improvised after an implementation has already become too entangled to remove safely.

---

## 9. Deliberate Evolution

CreatorOS is expected to evolve, and this expectation shapes how its architecture is built.

Evolution is intentional, documented, and reviewable. A change that meets these three conditions is evolution, regardless of its size. A change that meets none of them is not evolution, no matter how beneficial it happens to be in the moment.

Incremental architectural drift is not evolution. The distinction is not about the pace or scale of change but about whether the change was decided and recorded, or simply allowed to accumulate unnoticed.

---

## 10. Simplicity through Clarity

Prefer architectures that are easier to understand rather than merely shorter to describe.

Clarity reduces long-term complexity, because an architecture that is genuinely understood can be reasoned about, extended, and corrected by people who did not design it. Brevity without clarity achieves the opposite: a short description that conceals rather than reveals how a system actually behaves.

Complexity should exist only where it creates enduring value. Where complexity exists for any other reason — habit, accident, or unexamined precedent — it should be treated as a cost to be reduced, not a feature to be preserved.

---

## 11. Documentation as Architecture

Architecture exists only when it is documented.

Documentation is an architectural artifact in its own right, not a report written about architecture after the fact. A decision that lives only in discussion or in the practice of those who made it has not yet become architecture — it becomes architecture at the point it is recorded.

It is not secondary work. Producing documentation is part of producing architecture, and an architectural decision is not complete until its documentation exists.

---

## Final Principles

The statements below distill the preceding sections into a form suitable for quotation and quick reference throughout this repository. They are not a substitute for the reasoning above; they are a memory aid for judgments the reasoning already justifies.

- Continuity over convenience.
- Identity over implementation.
- Memory over inference.
- Explicit over implicit.
- Composition over monolith.
- One concept. One definition.
- Replaceability by design.
- Deliberate evolution, not drift.
- Clarity over brevity.
- Architecture through documentation.
