# WiiCoverDownloader source analysis instructions

## Scope and rules

- Source: `oldsource/WiiCoverDownloader.cs`.
- This document defines the workflow. Committing it does **not** authorize starting any stage.
- The source may be edited progressively to support chunking and analysis. Keep the initial Git blob as a fixed baseline and track every source edit in Git and the manifest. Changes made solely for analysis must retain the program's behaviour; record any proposed behaviour change separately.
- The deliverables are analysis records and pseudocode for understanding and reimplementing selected behaviour in another language, potentially with a different architecture. They are not extracted C# files.
- Carry out only the stage expressly authorized by the user. Stop at each stage gate and report the results before proceeding.
- Do not infer implementation behaviour during Stage 1. Record uncertain boundaries or names as unresolved rather than guessing.

## Planned layout

```text
oldsource/WiiCoverDownloader.cs
source-analysis/
  manifest.yaml
  chunks/
    0001-<artifact-name>.md
    0002-<parent-name>/
      0002-<parent-name>.md
      0003-<child-name>.md
      0004-<nested-name>/
        0004-<nested-name>.md
        0005-<grandchild-name>.md
```

The sequence prefix reflects encounter order in the original file. A parent with children owns a same-named directory; its record lives inside that directory. A leaf has only a Markdown file. Nested directories continue recursively. Sanitize filenames, retain the original spelling in the manifest, and use sequence IDs to disambiguate overloads or repeated names.

## Stage 1 — Structural chunking

**Goal:** Create named, navigable artifact records and their nesting tree. Record only enough information to identify each artifact and locate it in the source. Source annotations are permitted when they make boundaries and references clearer.

1. Read from the beginning of the source to the end, assigning stable sequential IDs in encounter order.
2. Identify structural boundaries: namespaces, types, members, functions, constructors, substantial dictionary or lookup initializers, and other separately identifiable artifacts. Keep purely syntactic details brief. An artifact nested in another becomes its child.
3. Create one Markdown record per artifact. Include only its ID, original name, provisional kind, parent ID, source line range, and ordered references to direct children. Do not copy source bodies, describe behaviour, or write pseudocode.
4. Create `source-analysis/manifest.yaml` **beside** `source-analysis/chunks/`. Append an entry as each chunk is recorded. Each entry must contain sequence ID, original name, provisional kind, relative record path, parent ID (or null), source start and end lines **in the baseline revision**, and status `chunked`. Record the source path and baseline Git blob SHA at the top of the manifest; record the current source revision after each committed edit.
5. Where syntactically safe, add short C# comments with artifact IDs at boundaries in the source so manifest entries can be located after line numbers shift. Avoid inserting markers into strings, directives, expressions, or initializers where they could alter parsing. Use manifest-only anchors when a safe source marker is unavailable. Commit source annotations in small, reviewable batches and link each batch to the affected manifest entries.
6. Use a clearly labelled `unresolved` record when a boundary, kind, or nesting relationship cannot yet be established. Account for meaningful top-level material that does not belong to a named declaration (such as using directives or preprocessor regions).
7. Check that IDs and paths are unique, parent links resolve, children follow source order, and every intended structural artifact appears in the manifest. Source ranges may overlap for parents and children; this represents nesting, not duplicate ownership. Compare the edited source against the baseline to confirm Stage 1 changes are limited to annotations. Report the count, tree, source revisions, and unresolved boundaries.

**Gate:** Stop after the structural hierarchy and manifest are complete. Do not inventory members or interpret mechanisms in this stage.

## Stage 2 — Per-artifact inventory

For each chunk in manifest order, identify declarations, fields, properties, constants, parameters, return values, dictionaries and their shapes, calls, external dependencies, and state access. Expand its Markdown record with the inventory and cross-references to other artifact IDs. Source annotations or small structural edits may be made progressively when they improve traceability; record each change against the baseline and verify it does not change behaviour. Update its manifest status to `inventoried`. Resolve provisional names and boundaries where possible; report remaining uncertainties. Stop before behavioural analysis.

## Stage 3 — Behaviour and mechanisms

Work from leaf artifacts towards their parents. Describe purpose, inputs, outputs, state transitions, dictionary key/value semantics, decisions, loops, transformations, failures, side effects, ordering constraints, and edge cases. Write concise language independent pseudocode where it clarifies important behaviour. Distinguish directly observed behaviour from inference. Link to source ranges and related artifact IDs. For an oversized function, add explicitly labelled analytical subdivisions without claiming they are source declarations. Update statuses to `analysed` and stop for review. Source edits may clarify or separate mechanisms, but preserve a direct mapping to the baseline and validate any executable change.

## Stage 4 — Reimplementation map

Combine the analysed artifacts into a dependency map and identify mechanisms that can be reproduced independently. State the behavioural contract, necessary data, dependencies, and unresolved questions for each mechanism. Propose implementation chunks for another language without assuming that the C# nesting or architecture should be retained. Do not implement code unless separately authorized.
