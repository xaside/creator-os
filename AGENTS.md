# CreatorOS

CreatorOS is an architecture-first project. Every capability it will ever have begins as an explicit architectural decision, recorded before any implementation exists.

This repository is the architectural source of truth for every future CreatorOS repository. Implementation repositories will come and go, be rewritten, or be replaced entirely — this repository is the constant they are built against. Anyone, human or AI, working on any part of the CreatorOS ecosystem is expected to defer to what is recorded here.

---

# Mission

Architecture defines implementation.

Implementation never defines architecture.

No amount of convenience, deadline pressure, or technical constraint in an implementation repository justifies changing what is decided here. If an implementation cannot satisfy the architecture, the implementation is wrong, or the architecture must be changed deliberately — through the process this document describes, not by quiet accommodation.

---

# Repository Scope

This repository contains:

- vision
- philosophy
- governance
- architecture
- standards
- documentation

It does not contain production implementation. No application code, services, infrastructure definitions, or build tooling for CreatorOS products belong here. If a task appears to require writing implementation code inside this repository, that is a signal the task does not belong here.

---

# Governance

Four roles operate within this repository. Their responsibilities are distinct and must not blur into one another.

**Architecture Board**
The Architecture Board is the sole authority for introducing new architectural concepts. It approves RFCs, ratifies ADRs, and is the only body that may amend the Manifesto, Constitution, or Principles. No other role may originate architecture on the Board's behalf.

**Repository Maintainer**
The Repository Maintainer keeps this repository consistent, organized, and navigable. The Maintainer applies decisions the Architecture Board has already made — organizing files, refining documentation, maintaining templates — but does not make architectural decisions.

**Reviewer**
The Reviewer evaluates proposed changes for consistency with existing architecture, terminology, and standards before they are merged. A Reviewer's approval confirms a change fits within what has already been decided — it does not itself authorize new architecture.

**AI Assistant**
An AI Assistant may act in a Repository Maintainer or Reviewer capacity when instructed, and must observe the same limits those roles observe. An AI Assistant never acts as the Architecture Board, regardless of how it is prompted.

Only the Architecture Board introduces new architectural concepts. This is the single most important rule in this document, and every other rule exists to protect it.

---

# Decision Hierarchy

Highest authority first:

1. MANIFESTO
2. CONSTITUTION
3. PRINCIPLES
4. RFC
5. ADR
6. Documentation
7. Implementation

Higher authority always overrides lower authority. If a lower-authority document appears to conflict with a higher one, the lower document is in error and must be corrected — it does not get to stand as an exception. When a conflict is found, it should be raised, not silently resolved in favor of whichever document is easier to change.

---

# Core Principles

**Creator First**
Every decision is weighed against the interests of the creator CreatorOS exists to serve, not against what is easiest to build or operate.

**Identity over Technology**
The identity of a creator, and the continuity of that identity, matters more than any particular technology used to express or serve it. Technology is replaceable; identity is not.

**Memory over Generation**
What has been deliberately recorded and decided takes precedence over what can be freshly generated or inferred. Regenerating an answer is not a substitute for remembering the one already given.

**Architecture before Code**
No implementation begins before the architecture it depends on has been decided and recorded. If the architecture does not yet exist, the correct action is to define it, or to wait — not to code around its absence.

**Replaceability**
Any single implementation must be replaceable without threatening the architecture or the creator's continuity. Nothing essential should depend on one implementation surviving forever.

**Explicit Decisions**
Decisions are recorded, not assumed. An undocumented convention is not a decision; it is a gap waiting to cause drift.

**Long-term Thinking**
This repository is written to remain correct for years, under contributors and assistants who were not present when a decision was made. Prefer what will still make sense later over what is merely convenient now.

**Consistency over Convenience**
When consistency with existing architecture and terminology conflicts with a faster or simpler path, consistency wins.

**Documentation is Part of the Product**
Documentation is not a byproduct of building CreatorOS — it is part of what CreatorOS is. Undocumented architecture does not count as architecture.

---

# Repository Rules

Always:

- preserve terminology
- improve documentation
- reuse existing concepts
- ask when uncertain
- document important decisions

Never:

- invent architecture
- silently rename concepts
- duplicate definitions
- implement undocumented architecture
- contradict accepted RFCs

---

# Documentation Standards

All documentation should be:

- timeless
- concise
- neutral
- precise
- implementation-independent where possible

Avoid:

- hype
- marketing language
- vendor-specific terminology
- unnecessary repetition

A document that reads as current only because it references a particular tool, vendor, or trend has failed the timelessness standard. Write as though the reader is arriving years from now, with no memory of what technology was fashionable when this was written.

---

# Maintainer Authority

The Repository Maintainer may independently:

- organize files
- improve documentation
- maintain templates
- commit documentation changes
- push approved work
- fix documentation inconsistencies

The Repository Maintainer must request approval before:

- changing architecture
- introducing new concepts
- modifying terminology
- creating RFCs
- changing governance
- deleting accepted documents

This boundary is not a matter of trust — it is a structural safeguard. A Maintainer who is confident an architectural change is correct still requests approval, because the Maintainer's role is to preserve architecture, not to originate it.

---

# Collaboration Workflow

Architecture Discussion

↓

Architecture Decision

↓

Documentation

↓

Review

↓

Implementation

↓

Review

↓

Implementation never precedes architecture. A task that arrives already framed as an implementation request, with no corresponding architecture recorded, should prompt a pause rather than a start.

---

# Final Rule

If uncertainty exists,

stop,

ask,

never invent architecture.
