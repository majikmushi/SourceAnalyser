---
id: SRC-TRACE-001
type: source-analysis-standard
status: draft
stage: 00
---

# Source evidence and artifact traceability

## Purpose

Record candidate requirements for NikolaTesla's design review of source intake, fragment creation, and analysis records. This is neither an approved manifest contract nor a syntax-cutting algorithm.

## Intake and baseline

Store user-supplied files in `Analyser/Source/Incoming/`. A later named-file assignment must identify exact allowed paths and source revision or content identity, the selected scope, and permitted actions. Preserve the original source. Recording a file or generating a manifest does not authorize opening adjacent files or editing the source.

## Manifest and paired trees

The current proposal reserves one manifest under `Analyser/Output/` above parallel `SourceFragments/` and `AnalysisRecords/` trees. Candidate artifact fields are stable ID, type, original name, parent ID, sibling order, original file and exact revision, source range or boundary identity, and paired fragment/record paths. Track cutting state separately from analysis state. Child references should retain order and nesting, and recursive expansion of fragments should reproduce tagged source without loss or duplication. NikolaTesla must review the exact representation and checks before implementation. Record uncertainty rather than forcing a cut.

## Claims and representations

An analysis record identifies its source evidence and distinguishes observed facts, inference, unknowns, disputes, and proposed design. Retain source semantics independent of a diagram, pseudocode, target language, or file layout. Mark any projected, approximate, or unrecoverable representation explicitly. A successful parse or rendered view does not prove behavioural equivalence or authorize a new design.

## Source edits

Any future boundary annotation or source edit needs an assigned task, exact baseline, review of the change, and a check that program behaviour was not inadvertently altered. Source fragments are evidence; they are not claimed to compile independently.

No source files have been selected or inspected and no manifest entries exist yet.

Related documents: ARCH-PRJ-001, RULE-PRJ-001.
