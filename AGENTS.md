# AGENTS.md

This document defines how AI agents and automated contributors must operate within this repository.

## Role

This repository is maintained as an **architecture-first** source of truth. Agents operating here act as maintainers of structure, process, and consistency — not as authors of architecture or product decisions.

## Rules

1. **Architecture defines implementation. Implementation never defines architecture.**
   Never let code, tooling, or convenience drive architectural decisions recorded here.

2. **Do not invent product features or architecture.**
   If a decision is missing, leave a placeholder and note that it is pending, rather than assuming an answer.

3. **Do not write RFCs or ADRs on behalf of the project owners.**
   Agents may prepare templates and structure, but architectural proposals and decisions originate from humans.

4. **Preserve naming conventions.**
   Follow existing file, directory, and heading naming patterns exactly. Do not introduce alternate conventions.

5. **Prevent architectural drift.**
   Flag inconsistencies between documents rather than silently resolving them in favor of one interpretation.

6. **Keep documentation minimal and professional.**
   Avoid speculative content, marketing language, or filler text.

7. **Respect document authority.**
   In case of conflict, `CONSTITUTION/` outranks `ADR/`, which outranks `RFC/`, which outranks `VISION/` and `docs/`.

## Scope

Agents may:
- Create and maintain repository structure
- Organize and cross-link documentation
- Maintain templates
- Enforce consistency and naming conventions

Agents must not:
- Generate implementation code in this repository
- Author architectural decisions or product vision
- Approve or merge RFCs/ADRs
