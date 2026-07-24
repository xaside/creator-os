# RFC-0005: Workspace Model

- **Status:** Accepted
- **Author:** Architecture Board
- **Scope:** Specializes the Workspace entity introduced in RFC-0001

This RFC does not redefine the core domain model established in RFC-0001. It specializes one entity from that model — Workspace — describing its purpose, boundaries, invariants, and relationships to Projects, Artifacts, Identity, Memory, and Knowledge in greater depth.

---

## 1. Purpose

Workspace organizes the Creator's active work. It is the entity in the CreatorOS domain model responsible for providing a bounded environment in which Projects and Artifacts can be arranged, navigated, and understood in relation to one another.

Workspace exists to give shape to activity, not to give shape to the Creator. Without a Workspace, Projects and Artifacts would have no consistent context in which to be organized — Workspace is what makes them navigable as a coherent body of active work, rather than a scattered and disconnected collection.

---

## 2. Conceptual Definition

Workspace is the organizing environment for a Creator's active work: the bounded space within which Projects are arranged and Artifacts are situated, so that ongoing work remains navigable and coherent.

Workspace is not Identity. Identity is the continuous thread of the Creator; Workspace is an environment that serves the Creator's activity, and does not itself carry the continuity that Identity represents.

Workspace is not Memory. Memory is intentionally preserved experience; Workspace may be informed by Memory, but Workspace organizes present and ongoing activity, not preserved experience as such.

Workspace is not Knowledge. Knowledge is organized understanding derived from Memory and explicit structure; Workspace may draw on Knowledge to shape how work is arranged, but Workspace itself is an organizing environment, not a body of understanding.

Workspace is not Skill. A Skill is a reusable capability; Workspace may be the setting in which a Skill is exercised, but Workspace is not itself a capability.

Workspace is not Project. A Project is a bounded unit of purposeful work with an expected beginning and end; Workspace is the broader environment in which one or more Projects exist, and it persists independently of any single Project's lifespan.

Workspace is not Artifact. An Artifact is a durable result of work; Workspace organizes Artifacts and gives them context, but the Workspace itself is not a result — it is the environment results exist within.

Workspace is not Implementation. No specific mechanism used to store, render, or synchronize a Creator's organizational environment constitutes Workspace itself. Workspace is the concept those mechanisms exist to serve.

---

## 3. Properties of Workspace

Workspace has the following essential properties.

**Organization.** Workspace arranges active work into a coherent structure, rather than leaving Projects and Artifacts as an undifferentiated collection.

**Boundedness.** Workspace has a defined scope — it organizes a particular body of active work, rather than being an unbounded or unlimited space encompassing everything a Creator has ever done.

**Navigability.** Workspace is structured so that its contents can be found, understood, and moved between, rather than requiring exhaustive search to locate anything within it.

**Persistence of structure.** The organizational structure Workspace provides persists over time, even as the specific Projects and Artifacts within it change.

**Support for active work.** Workspace exists to support what a Creator is currently doing or has recently done, distinguishing it from Memory's broader preservation of experience across all time.

**Distinction from identity.** Workspace organizes activity without defining who the Creator is. Its structure may change substantially without this implying any change to the Creator's continuity.

---

## 4. Workspace and Creator

Workspace serves the Creator without defining the Creator. It exists entirely in service of organizing the Creator's active work, and has no standing or purpose independent of that service.

Workspace may change as the Creator's work changes — reorganized, restructured, or rebuilt entirely as circumstances require — but the Workspace is not the Creator and does not determine identity. A Creator whose Workspace is completely reorganized has not changed in any way that touches their continuity; only the organizing environment around their activity has changed.

---

## 5. Workspace and Projects

Workspace contains or organizes Projects. Where a Project is a bounded unit of purposeful work, Workspace is the environment that gives that Project a place — situating it among other Projects, providing the context in which it can be found, tracked, and understood.

Projects are bounded units of purposeful work; Workspace provides the environment in which those projects live and are managed. Workspace's relationship to any individual Project is organizational rather than definitional: Workspace does not determine what a Project is or what it accomplishes, only where and how it sits within the Creator's broader active work.

---

## 6. Workspace and Artifacts

Workspace organizes Artifacts, giving them a place within the broader structure of active work even after the Project that produced them has concluded.

Artifacts may outlive Projects, and Workspace may help preserve their accessibility and context. Where a Project ends but its Artifacts persist, Workspace is what keeps those Artifacts situated in a way that remains navigable — without Workspace, a persisting Artifact would risk becoming disconnected from the context that made it meaningful.

---

## 7. Workspace and Identity

Workspace may reflect Identity without constituting it. The way a Creator chooses to organize their active work can express something about who they are — their preferences, their style, their priorities — but this expression does not make Workspace a source of Identity's continuity.

Workspace may express preferences, structure, or style, but it does not define who the Creator is. A Creator's Identity remains intact regardless of how their Workspace is arranged, reorganized, or replaced, consistent with the boundary established in RFC-0002 between what expresses Identity and what constitutes it.

---

## 8. Workspace and Memory/Knowledge

Memory and Knowledge may inform Workspace organization. What a Creator remembers, and what they have come to understand, can reasonably shape how their active work is arranged — organizational choices are rarely made without some basis in prior experience or understanding.

Workspace can be shaped by what the Creator remembers and understands, but it remains distinct from both. Memory preserves experience, and Knowledge organizes understanding; Workspace organizes active work, and while it may draw on either, it is not reducible to, nor a substitute for, either one.

---

## 9. Workspace Boundaries

Workspace does not define implementation, storage, runtime, synchronization, or presentation. These are matters of how CreatorOS is eventually built and operated, and Workspace's definition at the domain level does not extend into them.

Workspace is conceptually stable and implementation-independent. Its definition holds regardless of the mechanism eventually used to represent, store, or render it. A future architectural decision about how Workspace is technically supported must conform to what is defined here — the definition of Workspace does not bend to accommodate whatever a given implementation finds most convenient.

---

## 10. Workspace Invariants

The following invariants must always hold:

- Workspace organizes active work.
- Workspace is distinct from Identity.
- Workspace contains or organizes Projects.
- Workspace organizes Artifacts.
- Workspace may evolve deliberately.
- Workspace survives implementation replacement.

These invariants are non-negotiable within the scope of this RFC. Any future architecture that would require violating one of them, however convenient in other respects, must be revised rather than accepted as an exception.

---

## 11. Workspace Lifecycle

At a conceptual level, Workspace moves through the following stages, described here without reference to any technical mechanism:

**Creation.** A Workspace comes into being as an organizing environment for a body of active work.

**Organization.** Projects and Artifacts are arranged within the Workspace, given structure and relation to one another.

**Adaptation.** The Workspace's structure changes as the Creator's active work changes, accommodating new Projects and the conclusion of old ones.

**Navigation.** The Workspace is used to find, understand, and move between the Projects and Artifacts it organizes.

**Refinement.** The organizational structure of the Workspace is improved over time, as better ways of arranging active work become apparent.

**Deliberate revision or retirement.** A Workspace may be substantially reorganized or retired entirely, as an explicit, attributable act, without this implying any change to the Creator's continuity.

---

## 12. Future Specialization

Later RFCs may elaborate on specific workspace types, organizational structures, or workspace behaviors in greater depth than this document attempts.

Such future RFCs may add detail and refinement, but they may not change the canonical meaning of Workspace established here. Where a future RFC appears to require a different definition of Workspace than the one given in this document, the correct response is to revise this RFC directly, through the same deliberate process by which it was accepted — not to allow a competing definition to stand alongside it.
