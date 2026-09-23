---
id: ARCH-PRJ-001
type: project-structure
status: draft
stage: 00
---

# SourceAnalyser project objectives and structure

## Purpose

Develop a reusable, staged, Python-assisted analyser, initially focused on C# source. WiiArtDownloader is its first analysis application. The project has two related outcomes, tracked separately: an analyser that produces navigable, traceable source fragments and records; and an evidence-based account of selected source behaviour, data, and relationships for each authorized analysis project.

That account should support decisions about refactoring or reimplementing selected capabilities in another language. The original source remains evidence of existing behaviour; its file, class, and language structure does not dictate the replacement design.

The reusable scope is confirmed by the user in D-011. Support for additional languages remains undecided. How separate analysis projects are represented and stored remains a later design question; the current layout is not an approved multi-project architecture.

## Objectives

1. Develop and validate the analyser in bounded stages before relying on its output.
2. Preserve source revision, order, nesting, and stable artifact identity so extracted fragments remain traceable and reconstructable.
3. Record structure, interfaces, data, mechanisms, and cross-artifact relationships in successive reviewable passes.
4. Distinguish source observations from interpretations, proposals, and unresolved questions.
5. Produce behavioural contracts and verification evidence for capabilities selected for reimplementation.
6. Track analyser development and source analysis independently, with a review and resumable state at each stage.

## Framework relationship

[FRAMEWORK-BASELINE.md](FRAMEWORK-BASELINE.md) records the proposed AgentZeroFramework dependency and its exact candidate revision. A project-specific decision must adopt that baseline; a branch name or newly available revision does not change the active rules by itself. Project source, operational state, and evidence remain project-owned. The framework dependency is referenced, not copied into this repository.

## Documentation branches

- `AGENTS.md`: repository-wide entry point; `AgentRoles/`: scoped role instructions, currently only Designer.
- `Analyser/Docs/AnalyserDesign/`: analyser requirements, architecture, standards, and stage-specific design and implementation documents.
- `Analyser/Docs/CodeAnalysis/`: source-analysis plans and confirmed outputs from authorized stages.

Each branch has `Standards/`, `Architecture/`, and numbered `Stages/NN-Name/` folders. Stage folders distinguish `Design/` from `Implementation/` when implementation begins. Working drafts and source notes live in `Analyser/Transient/`; process state and decisions live in `AgentState/`. The source upload area is `Analyser/Source/Incoming/`. Existing documents remain at their current paths until a reviewed move.

When source analysis is authorized, `Analyser/Output/` will have one manifest above parallel source-fragment and analysis-record trees. Each artifact needs a stable identity and traceable relationship to the exact source revision. [SOURCE-TRACEABILITY.md](Analyser/Docs/CodeAnalysis/Standards/SOURCE-TRACEABILITY.md) records the requirements; a concrete manifest and entries await authorized source selection.

## Provisional stage outline

This outline preserves the existing proposal as design input. NikolaTesla will flesh out the requirements, architecture, and proposed stages; stage names, boundaries, and gates remain open until that design is reviewed. The later stage and role/agent alignment pass follows the design handoff in STATE-HANDOFF-001.

| Stage | Analyser development | Code analysis |
|---|---|---|
| 00 Foundation | Establish requirements, document standards, high-level architecture, stage map, and Stage 01 design. | Define source scope and baseline method; do not inspect source by default. |
| 01 Chunk | Design and build structural chunking and validation. | Identify selected major artifacts one nesting level at a time; record structure without behaviour. |
| 02 Inventory | Support bounded per-artifact records. | Record definitions, data, interfaces, calls, and state access. |
| 03 Mechanisms | Support traceable behavioural records. | Describe decisions, transformations, side effects, errors, and useful pseudocode. |
| 04 Relationships | Support cross-artifact linking. | Resolve calls, data flow, shared state, and ordering. |
| 05 Portability | Support behavioural contract records. | Define selected mechanisms for implementation in another language. |
| 06 Verification | Support checks against recorded source evidence. | Capture cases and results needed to verify a new implementation. |

A stage may have multiple bounded passes. NikolaTesla's design pass will define stage-specific gates; each stage's design and outputs require review before proceeding. Tool tests against real source require authorization for the exact named files.

## Integrity and authority

Preserve stable artifact IDs, source order, nesting, and traceable source revisions. A cutter must reconstruct tagged source from fragments and child references without loss or duplication. Do not guess uncertain syntax boundaries or silently change program behaviour. Source annotations or edits require an assigned task and a check against the baseline. Source fragments are evidence, analysis records contain claims, and a proposed replacement design needs its own decision and approval; none silently becomes another.
