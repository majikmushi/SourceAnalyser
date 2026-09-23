---
id: RULE-PRJ-001
type: project-rules
status: draft
---

# Project work rules

## Scope and authority

Classify each assignment as design-semantic work, bounded execution/tool work, or source analysis. A Designer can propose or revise project meaning only within an expressly assigned scope. A Runner executes a bounded, resolved task; a role or model name alone does not grant source access, design authority, commit permission, merge permission, or proof of capability. Use deterministic tools and the lowest-cost qualified executor for bounded work where qualification and permission are established. Escalate unresolved architectural meaning to an authorized Designer.

Keep analyser development and code analysis in separate documentation and state tracks. Completing or testing the tool does not complete analysis of source.

## Source access

The current source read list is empty. A future upload into `Analyser/Source/Incoming/` is storage, not permission to open or analyse its contents. A source-analysis assignment must list exact allowed paths and revisions, analysis objective, stage, permitted outputs, and whether source edits or tool tests are allowed. Do not broaden that list by browsing adjacent files, generated output, or search results. Record observations with source evidence; label inference and uncertainty.

## Bounded passes and gates

Read the project entry documents and current assignment, then load only standards and references needed for the current pass. Persist objective, inputs, decisions, evidence, unresolved questions, outputs, next entry point, and completion conditions. Review stage results against its approved gate before declaring completion. An unresolved source boundary is reviewed, not guessed. A source fragment is evidence; an analysis claim and an approved replacement design require separate validation and authority.

## Repository changes

Read before write. Work on a non-default branch unless the user directs otherwise. Limit changes to assigned paths, preserve unrelated work, and check the resulting diff. Ask the user to review the exact proposed change before committing; commit only after that approval. Commit approval does not grant merge approval. Source annotations or edits require their own assignment and baseline check.

Related documents: AGENT-ROOT-001, BASE-FWK-001, ARCH-PRJ-001.
