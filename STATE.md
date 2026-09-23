---
id: STATE-ROOT-001
type: state-standard
status: draft
---

# Project state standard

## Purpose

Keep assignments, decisions, progress, and handoffs recoverable without relying on conversation history.

`AgentState/CURRENT-ASSIGNMENT.md` owns the active objective, stage, exact permitted inputs and source-read list, writable paths, work completed, evidence, unresolved issues, next action, and completion conditions. The source list starts empty and remains empty until an explicit named-file assignment. `AgentState/DECISIONS.md` records adopted and proposed decisions with provenance; a candidate decision does not change project authority.

Track analyser development and code analysis separately for each stage. Use `concept`, `design`, `implementation`, `testing`, `complete`, or `blocked` as appropriate, with evidence for a completion claim. The work stages of one track do not advance automatically when the other advances. Stage-specific gates await NikolaTesla's design review.

When introduced after authorized source selection, the source manifest owns artifact identity, nesting, source revision, fragment/analysis pairing, and per-artifact progress. It does not replace this central process state. Source intake, analysis claims, project design decisions, and test results remain distinct records.

Related documents: ARCH-PRJ-001, RULE-PRJ-001, SRC-TRACE-001.
