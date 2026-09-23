---
id: ARCH-PRJ-001
type: project-structure
status: draft
stage: 0
---

# Project structure

## Purpose

Develop a staged Python-assisted analyser and use it, when authorized, to turn C# source into bounded structural and behavioural records suitable for refactoring or reimplementation in another language. Design the tool and analyse the code as two related, separately tracked tasks. Use the lowest-cost qualified agent for bounded work.

## Documentation branches

- `Analyser/Docs/AnalyserDesign/`: standards, architecture, requirements mapped to stages, and stage-specific design and implementation documents.
- `Analyser/Docs/CodeAnalysis/`: the analysis plan and confirmed outputs from authorized source-analysis stages.

Each branch can use `Standards/`, `Architecture/`, and numbered, named `Stages/NN-Name/` folders where needed. Stage folders distinguish `Design/` from `Implementation/`. Existing documentation stays where it is until a move is agreed. Working drafts live in `Analyser/Transient/`; process state lives in `AgentState/`.

When source analysis is authorized, the working output has one manifest above parallel source-fragment and analysis-record trees. Each artifact has a stable ID and matching location in both trees. The detailed format belongs in the relevant stage design.

## Stages

| Stage | Analyser development | Code analysis |
|---|---|---|
| 00 Foundation | Establish requirements, document standards, high-level architecture, stage map, and Stage 1 design. | Define source scope and baseline method; do not inspect source by default. |
| 01 Chunk | Design and build structural chunking and validation. | Identify selected major artifacts one nesting level at a time; record structure without behaviour. |
| 02 Inventory | Support bounded per-artifact records. | Record definitions, data, interfaces, calls, and state access. |
| 03 Mechanisms | Support traceable behavioural records. | Describe decisions, transformations, side effects, errors, and useful pseudocode. |
| 04 Relationships | Support cross-artifact linking. | Resolve calls, data flow, shared state, and ordering. |
| 05 Portability | Support behavioural contract records. | Define selected mechanisms for implementation in another language. |
| 06 Verification | Support checks against recorded source evidence. | Capture cases and results needed to verify a new implementation. |

A stage may have multiple bounded passes. Review its design and outputs before proceeding. Tool tests against real source require explicit authorization for the named files.

## Integrity

Preserve stable artifact IDs, source order, nesting, and traceable source revisions. A later cutter must be able to reconstruct tagged source from its fragments and child references without loss or duplication. Do not guess uncertain syntax boundaries or silently change program behaviour. Source annotations or edits require an assigned task and a check against the baseline.
