# Architecture Questions

This document is the canonical registry of architecture questions discovered during architecture reviews. It exists to track unresolved architectural questions that deserve future attention, without treating them as confirmed defects in the architecture as it currently stands.

An Architecture Question is not an architecture defect. Recording one does not invalidate any accepted RFC, and no entry in this registry carries the authority to override or supersede an accepted architectural decision.

An Architecture Question represents uncertainty or an opportunity to improve architectural consistency — a place where the existing architecture admits more than one reasonable reading, or where a wording choice could, in principle, be sharpened. It is not a backlog item, an implementation task, or a substitute for the RFC or ADR process.

An Architecture Question should be resolved during an Architecture Consistency Review or by a future RFC revision, following the same review process established elsewhere in this repository. This document tracks the question until that resolution occurs; it does not resolve anything on its own.

This document is not an RFC, an ADR, technical debt, an implementation backlog, or a GitHub issue tracker. It is maintained as a living registry, updated as questions are raised, reviewed, and closed.

---

## Lifecycle

Every Architecture Question moves through the following lifecycle:

Open

↓

Under Review

↓

Resolved

↓

Closed

**Open.** The question has been identified and recorded, but no review of it has yet begun.

**Under Review.** The Architecture Board is actively evaluating the question.

**Resolved.** A decision about the question has been reached.

**Closed.** The decision has been incorporated into the architecture, and the question requires no further tracking.

---

## Resolution Types

An Architecture Question may be resolved in one of the following ways:

- No architectural change required.
- Clarified by Architecture Consistency Review.
- Resolved by RFC revision.
- Resolved by new RFC.
- Superseded by later architecture.

The resolution type is recorded against the question once it reaches Resolved status, and the question is moved to Closed once that resolution has been reflected in the relevant architecture.

---

## Active Questions

---

### AQ-0001

**Status:** Open

**Title:** Meaning of "explicit source material"

**Raised During:** RFC-0004 Review

**Background:**

RFC-0004 allows Knowledge to be derived from Memory or other explicit source material. RFC-0001 currently models Knowledge as being informed by Memory, without explicitly representing additional source categories.

**Question:**

Should the core domain model explicitly represent "explicit source material," or is it merely descriptive language that requires no architectural representation?

**Current Assessment:**

No confirmed architecture issue.

**Potential Resolution:**

Architecture Consistency Review.

---

### AQ-0002

**Status:** Open

**Title:** Workspace responsibility for Artifact context

**Raised During:** RFC-0005 Review

**Background:**

RFC-0005 states that Workspace keeps Artifacts situated within active work. The architectural intent appears to be organizational context rather than responsibility for Artifact persistence.

**Question:**

Is the current wording sufficiently clear that Workspace organizes Artifact context without becoming responsible for Artifact existence or preservation?

**Current Assessment:**

No confirmed architecture issue.

**Potential Resolution:**

Architecture Consistency Review.

---

## Review Principles

A new Architecture Question should be created only when all of the following are true:

- No confirmed architecture issue exists.
- The architecture allows more than one reasonable interpretation.
- The ambiguity could influence future architectural decisions.
- The question cannot be resolved by simply improving wording.

Architecture Questions should not be created for:

- Grammar.
- Wording.
- Documentation style.
- Implementation details.
- RFC-0008 migration items.
- Already accepted ADRs or RFC decisions.

Where an issue falls into one of these categories, it should be corrected directly as an editorial matter, or, where it concerns migration already governed by RFC-0008, tracked through the migration process that RFC establishes — not recorded here.
