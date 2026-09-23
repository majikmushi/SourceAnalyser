---
id: AGENT-ROOT-001
type: agent-entrypoint
status: draft
---

# Agent entry point

This file applies to every agent working in this repository. Read PROJECT.md for objectives, FRAMEWORK-BASELINE.md for the proposed framework dependency, RULES.md for project limits, DOC_STANDARDS.md for controlled documents, and STATE.md plus AgentState/CURRENT-ASSIGNMENT.md for the active stage and exact permissions. Load only additional material required for the current task.

Classify the work before acting: source/design semantics require a scoped Designer assignment; bounded implementation, source analysis, or validation requires its own resolved task and authority. AgentRoles/DESIGNER.md contains role-specific design instructions. No model name, role label, repository access, or uploaded file grants authority by itself. Role and agent assignments for later stages remain open until design review.

The exact source-read list is empty. Preserve separate analyser-development and code-analysis states. Follow RULE-PRJ-001 for bounded passes, evidence, branch handling, and the user-review gate before any commit. A change to framework meaning or the project baseline requires a recorded decision; a Runner does not promote its output into authoritative design state.
