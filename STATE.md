---
id: STATE-ROOT-001
type: state-standard
status: draft
---

# Project state

## Purpose

Keep assignments and progress available across stages and agent handoffs.

`AgentState/` owns the current assignment, stage progress, decisions, and handoffs. Create records as work requires them. An assignment records its objective, permitted inputs, exact source read list, writable paths, stage, and next action. The source list begins empty.

Track analyser tool development and code analysis separately for each stage. Use `concept`, `design`, `implementation`, `testing`, `complete`, or `blocked` as applicable. Do not mark analysis complete because a tool was built.

A source manifest, when introduced, owns artifact identity, nesting, and source traceability. It does not replace the central process state.
