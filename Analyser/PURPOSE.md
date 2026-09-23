# Purpose: staged C# source analysis

## What are we building

Build an agent-friendly, Python-driven tool that reduces a C# source folder into a navigable set of source fragments and analysis documents. The result should contain enough structural, behavioural, and data information to reproduce selected capabilities, refactor the design, or re-engineer the system in another language.

The tool preserves the original source as evidence. It does not assume that the original classes, files, or C# implementation choices should be carried into the new design.

## what we want to achieve
The completed material should let an agent or engineer locate the source evidence for a claim, understand an individual mechanism without loading the entire original codebase, follow its dependencies, and identify what must be preserved when implementing it differently.

The analysis should distinguish facts observed in the source from interpretations and unresolved questions. It should capture externally visible behaviour and important data semantics without turning the documentation into a line-by-line C# translation.


## Why this is needed

Large source files overwhelm a single analysis pass. Functions, data structures, UI code, and shared state can be nested or interleaved, making it difficult for an agent to establish boundaries and relationships reliably. The tool breaks the work into bounded, reviewable passes. Each pass handles one nesting level or one analysis concern, records its result, and leaves a clear next action.

