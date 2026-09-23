# Purpose: staged C# source analysis

## Objective

Build an agent-friendly, Python-driven tool that reduces a C# source folder into a navigable set of source fragments and analysis documents. The result should contain enough structural, behavioural, and data information to reproduce selected capabilities, refactor the design, or re-engineer the system in another language.

The tool preserves the original source as evidence. It does not assume that the original classes, files, or C# implementation choices should be carried into the new design.

## Why this is needed

Large source files overwhelm a single analysis pass. Functions, data structures, UI code, and shared state can be nested or interleaved, making it difficult for an agent to establish boundaries and relationships reliably. The tool breaks the work into bounded, reviewable passes. Each pass handles one nesting level or one analysis concern, records its result, and leaves a clear next action.

## Core model

A Python script reads C# syntax to identify **selected major artifacts**, such as forms, substantial functions, dictionaries, and other important structures. Small declarations remain in their containing artifact until a later pass determines that they need separate treatment.

Processing starts at the source-file level. A later invocation opens one selected parent and handles only its immediate children. This continues recursively as far as useful. The source name of an artifact is retained; a type prefix and stable ID disambiguate its files and references.

The tool maintains one manifest above two parallel folder trees:

- **Source tree:** cut source fragments containing the original C# text, boundary comment tags, and references at the positions of extracted children. These fragments are evidence for analysis, not independently compilable C# files.
- **Analysis tree:** corresponding documents at the same relative positions. They begin as minimal structural records and gain definitions, pseudocode, data descriptions, and relationships in later stages.

The original source remains available. It may be annotated progressively with begin/end comment tags to make boundaries explicit. Every source edit must remain traceable to a revision and be checked for unintended behavioural changes.

## Intended stages

1. **Establish the baseline.** Record the source identity and revision, and define stable artifact IDs and naming rules.
2. **Cut the structure.** Select major artifacts one level at a time, mark their boundaries, create paired source and analysis files, and update the manifest. Do not infer behaviour during this stage.
3. **Inventory individual artifacts.** Identify definitions, signatures, inputs, outputs, data structures, calls, and state access within each bounded fragment.
4. **Describe mechanisms.** Record decisions, transformations, side effects, error handling, ordering constraints, and language-independent pseudocode for important behaviour.
5. **Resolve relationships.** Join the local findings into call, data, state, and initialization relationships across artifacts.
6. **Specify portable behaviour.** Define the contracts and verification material needed to reproduce selected capabilities in another language or architecture.

Each stage is reviewable before proceeding. The manifest tracks cutting and analysis progress separately, so an artifact with an established boundary is not mistaken for an analysed artifact.

## Expected result

The completed material should let an agent or engineer locate the source evidence for a claim, understand an individual mechanism without loading the entire original codebase, follow its dependencies, and identify what must be preserved when implementing it differently.

The analysis should distinguish facts observed in the source from interpretations and unresolved questions. It should capture externally visible behaviour and important data semantics without turning the documentation into a line-by-line C# translation.

## Integrity requirements

- Stable artifact IDs survive renaming and line-number changes.
- Parent/child references preserve source order and nesting.
- Expanding child references recursively reproduces the tagged source without lost or duplicated content.
- The source and analysis trees contain matching artifact IDs and paths.
- One manifest links each artifact's source fragment, analysis document, type, original name, parent, order, and separate processing states.
- Syntax boundaries and uncertain cases are reviewed rather than guessed; a mechanical cut never silently changes program behaviour.
