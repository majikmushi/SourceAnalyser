---
id: STD-ANL-DES-001
type: analyser-design-standard
status: draft
stage: 00
---

# Analyser design standard

## Purpose

Define how tool requirements and implementation work advance without authorizing source analysis by implication.

1. Record each stage's inputs, expected artifacts, identity/traceability obligations, failure behavior, validation gate, and out-of-scope work before implementation.
2. Use bounded passes. Prefer deterministic extraction and checks; assign semantic interpretation only when source access and the work item authorize it.
3. Preserve file revision, order, nesting, names, and stable artifact identity. Uncertain C# boundaries require review; do not guess or silently change code.
4. Keep source fragments, analysis records, manifest state, and authoritative project decisions distinct.
5. Tool development may use synthetic fixtures. Tests against uploaded source require exact named-file authorization. Report actual check results separately from planned validation.
6. A tool or schema revision must not silently invalidate prior artifact IDs, claims, or source links; record migration or incompatibility.

Related documents: ARCH-PRJ-001, RULE-PRJ-001, SRC-TRACE-001.
