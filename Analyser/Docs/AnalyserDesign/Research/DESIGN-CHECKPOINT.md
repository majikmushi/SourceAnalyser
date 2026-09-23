---
id: STATE-ANL-RES-001
type: design-research-checkpoint
status: draft
stage: 00
---

# Design checkpoint before tool research

## Confirmed direction

Repository: `majikmushi/SourceAnalyser`, formerly `majikmushi/WiiArtDownloader`. Remote main remains at `7042f43007b536dac8fa5072b3d15efca7b91c5c` when checked during handoff preparation. The later discussion state is saved on checkpoint branch `docs/design-research-handoff`; the design task remains incomplete.

The confirmed outcome (D-018) is a reusable, staged source-analysis tool and process, initially supporting C#, that produces context-manageable chunks, preserves integrity and traceability, progressively records structure/behaviour/data/relationships, connects evidence, and supports behavioural specifications and verification for later refactoring or reimplementation. Work is reviewable and resumable. WiiArtDownloader is the first application.

Chunking means dividing source into manageable context-sized pieces (D-017). Basic chunking must not be made dependent on complete syntax, semantic or behavioural analysis. Recognition can improve boundary selection and enrich subsequent work without becoming a prerequisite for every chunk.

The original Stage 0 scratchpad and stage outline are idea sources, not an adopted solution (D-016). Preserve them and all six PROJECT.md objectives.

## Ideas discussed, not selected architecture

- Initially selected `.cs` inputs; exact C# version coverage to be established rather than assumed. Detailed input scope and exclusions remain draft.
- Consider the overall processing pipeline while implementing only bounded parts at a time. Stage order and contracts are not frozen.
- Let the next stage's required inputs and limitations determine how much information the preceding pass must establish.
- Explore simple pattern recognition and stateful scanning in successive passes, progressively opening selected regions and retaining useful information.
- A language syntax definition could describe patterns, state transitions, nesting and captured information. Expected nesting/length may be heuristic; actual source extent and budget must be measured.
- Language recognition, pass purpose, and next-stage requirements are distinct concerns. No custom syntax-file format, parser, state machine or plugin architecture has been selected.

## Why research now

Before designing recognition mechanisms, investigate existing Python or easily adaptable tools that report positions in source and ideally identify structure kinds or declared names. The investigation should distinguish lexical token recognition, structure recognition, symbol indexing and deeper analysis; these are different levels of capability.

Earlier conversation mentioned Pygments, Tree-sitter, Semgrep, Roslyn and CodeQL. These are discovery leads only, not a shortlist that must be retained. The incoming researcher may find better candidates. No fresh comparative investigation or trial was performed during this handoff task.

## Boundaries and unresolved issues

- No target source inspected; exact target-source read list remains `[]`.
- No installation, code, execution trial, benchmark, architecture selection or final project-role assignment has been performed or approved here.
- Context-budget units, split/overlap rules, supported syntax envelope, coordinate representation, metadata and stage acceptance gates remain open.
- Framework candidate `2c7872e70d68b690f99cc216fc07ba3411224aeb` remains proposed, not adopted.
- User explicitly wants a more suitable agent to conduct the research. NikolaTesla stops after the brief and checkpoint.
- The user approved saving this checkpoint. Read branch `docs/design-research-handoff`; the checkpoint has not been merged into main. Saving does not approve the remaining design candidates.

## Resume sequence

1. Read AGENTS.md and STATE-CURRENT-001, then this checkpoint and TASK-ANL-RES-001.
2. Use a cheaper, suitably capable agent for bounded tool discovery and documentation collection; the executor is not selected by this handoff.
3. Gather suggestions against the simple criteria in the brief. Record documented facts, links and unknowns without evaluating suitability or integration effort.
4. Return the organised material to the user and NikolaTesla; deeper reasoning and evaluation happen afterward.
