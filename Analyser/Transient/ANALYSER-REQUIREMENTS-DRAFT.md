---
id: REQ-ANL-001
type: analyser-requirements-discussion
status: draft
stage: 00
---

# Analyser requirements for discussion

## Purpose and standing

First-pass requirements for developing the reusable Python-assisted analyser described in ARCH-PRJ-001. This draft preserves those objectives; it neither selects architecture nor authorizes implementation. Baseline: `majikmushi/SourceAnalyser` (formerly `majikmushi/WiiArtDownloader`) main at `7042f43007b536dac8fa5072b3d15efca7b91c5c`. Reusability is confirmed in D-011; C# remains the initial focus and WiiArtDownloader the first application.

All acceptance evidence below is proposed future evidence, not a test result. “Objective-derived” means traceable to the existing project direction, not newly approved. “Candidate” requires discussion before adoption. The original scratchpad remains unchanged.

## Expected outcome

A reusable, validated, resumable analyser that produces navigable source fragments and associated records with traceable identities, source order, nesting, and revision provenance. Its outputs must support later analysis without making a successful extraction a claim of understood or equivalent behaviour.

## Requirements and proposed acceptance evidence

| ID | Requirement | Basis / standing | Proposed acceptance evidence |
|---|---|---|---|
| REQ-ANL-101 | Develop and validate capabilities in bounded, reviewed increments before relying on their outputs. | ARCH-PRJ-001 objectives 1, 6; objective-derived | Each increment identifies inputs, outputs, exclusions, failure cases, actual check results, and review outcome. |
| REQ-ANL-102 | Associate extracted artifacts with exact source identity/revision, original name, location, parent, and sibling order. | ARCH-PRJ-001 objectives 2, 3; objective-derived | Every artifact traces to its source and has an unambiguous position in the retained structure. |
| REQ-ANL-103 | Preserve stable artifact identity through renaming and line-number changes; do not silently invalidate prior references when tool or schema versions change. | Scratchpad; STD-ANL-DES-001 clauses 3, 6; candidate detail | Planned change cases demonstrate retained identity or an explicit reviewed migration; split/merge identity remains Q-A4. |
| REQ-ANL-104 | Preserve order, nesting, and complete content coverage so reconstruction loses or duplicates nothing. | ARCH-PRJ-001 integrity; objective-derived | Reconstruction comparison against an explicitly selected baseline; exact original-byte versus tagged-source target awaits Q-A3. |
| REQ-ANL-105 | Process an explicitly selected scope in bounded passes; retain smaller declarations within their parent until separately selected. | Scratchpad; candidate granularity | A pass records its selected parent and children, retains unselected content, and does not expand scope implicitly. |
| REQ-ANL-106 | Report ambiguous or unsupported syntax boundaries and keep affected work unresolved instead of guessing a cut. | ARCH-PRJ-001 integrity; STD-ANL-DES-001; objective-derived/candidate failure detail | Ambiguous fixture cases preserve source and expose a reviewable diagnostic without a false success state. |
| REQ-ANL-107 | Keep fragments, claims, project decisions, and extraction/analysis progress distinguishable and navigable. | ARCH-PRJ-001 objectives 3, 4, 6; objective-derived | Each output can be identified by purpose and provenance; extraction completion cannot mark semantic analysis complete. |
| REQ-ANL-108 | Support records that progressively capture structure, interfaces, data, mechanisms, relationships, and portability evidence. | ARCH-PRJ-001 objectives 3–5; objective-derived | Each required record category can retain evidence, uncertainty, and review state without replacing earlier evidence. |
| REQ-ANL-109 | Record sufficient input, tool/configuration identity, result status, and checkpoint information to resume and explain a run. | STATE-ROOT-001; STD-ANL-DES-001 clause 6; candidate run detail | A fresh context identifies completed, failed, and pending work without conversation history; rerun policy awaits Q-A5. |
| REQ-ANL-110 | Validate initially against explicitly scoped synthetic fixtures; use real source only under a separate exact-file assignment. | STD-ANL-DES-001 clause 5; local constraint | Test records identify fixture/source provenance and the authorization applicable to real-source tests. No tests authorized by this draft. |
| REQ-ANL-111 | Preserve original source as evidence; annotation or modification requires separate authorization and comparison against its baseline. | RULE-PRJ-001; SRC-TRACE-001; local constraint | Extraction does not silently alter originals; any future authorized edit has a distinct reviewed change and validation record. |

## Constraints and deliberately unresolved choices

- Confirmed purpose of chunking (D-017): divide source material into small, context-manageable chunks. A syntax artifact and a context chunk are not assumed to be identical. Proposed acceptance detail: assess a chunk together with required supporting context against an agreed working budget. Budget, measurement and boundary policy remain unresolved; structural extraction is one candidate approach.

- C# is explicitly confirmed as the initial language (D-013). Chunking was raised as a preference (D-014); the user clarified that the old documentation supplies potentially useful ideas for scope and design (D-016). Its mechanisms and stage arrangement remain candidates, not adopted requirements. Define needs before choosing an approach.

- Reusability is confirmed. Candidate consequence: project-specific source, selection and analysis state must be distinguishable from reusable tool behaviour. Storage, project configuration and isolation mechanisms are not selected. Evidence beyond the first application will be needed before claiming demonstrated reuse.

- Python-assisted development is the existing project direction. Whether parsing must be Python-only is unresolved; no parser, library, algorithm, schema, or interface has been selected.
- Prefer deterministic extraction/checks and appropriately qualified, economical execution. Model names do not decide authority or quality. Final role and agent assignments are deferred.
- Existing standards are draft candidate constraints. Proposed additions here do not silently amend them or adopt the framework baseline.
- One manifest, paired trees, comment tags, and immediate-child traversal are existing design candidates; requirements concern their intended outcomes, not approval of those mechanisms.
- No assumed OS, C# version, project size, runtime availability, speed target, or external-service permission. These affect later design and need explicit answers.

## Questions

| ID | Question | Why it matters / suggested discussion position |
|---|---|---|
| Q-A1 | Reusable scope is confirmed (D-011). Which host OS and dependency/runtime limits apply, and is support beyond C# a future goal? | Reusability is no longer open. Platform requirements and broader language scope remain undecided. |
| Q-A2 | What makes an artifact significant enough to extract, and who approves selection? Should a pass handle only immediate children of one selected parent? | Prevents uncontrolled fragmentation. Review the scratchpad's selective, one-level approach. |
| Q-A3 | Must reconstruction recover original bytes, including encoding, line endings, comments and whitespace, as well as any tagged derivative? Are annotations needed at all? | Distinguishes exact evidence preservation from text/semantic equivalence. Recommend exact original recovery; tagging remains optional and separately authorized. |
| Q-A4 | How should identity behave on moves, splits, merges, deletion, and substantive revision? | Stable identity must not conceal changed meaning. Recommend retained lineage with explicit change records; mechanism deferred. |
| Q-A5 | What must resume/rerun guarantee: no duplicate artifacts, preserved reviewed claims, detection of stale analysis, and which repeatable outputs? | Defines reliability before selecting persistence or update mechanisms. Recommend all three integrity guarantees; do not promise deterministic semantic interpretations. |
| Q-A6 | What source sizes, pass/context limits, turnaround expectations, and agent cost limits should development target? | Enables measurable acceptance criteria without inventing thresholds. |

## Review boundary

Discuss Q-A1–Q-A6, retain or amend the requirements, and record accepted/deferred items before requesting an architecture pass. No architecture or implementation gate is passed by this document.

Related: ARCH-PRJ-001 (`PROJECT.md`), STD-ANL-DES-001, SRC-TRACE-001, STATE-CURRENT-001, and `DESIGN-INPUT-REVIEW.md` in this directory.
