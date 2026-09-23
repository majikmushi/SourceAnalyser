---
id: TASK-ANL-RES-001
type: research-task-brief
status: draft
stage: 00
---

# Tool suggestions: structural analysis of C# source

## Task

Find four to six tools that may help recognise structures in C# source. Look for Python tools or tools with a documented Python binding or command-line interface.

Simple criteria:

- Supports C# source.
- Reports positions in the source, preferably start and end locations.
- Ideally identifies the kind or name of a structure.
- Has accessible source code and documentation.

## Return

Provide one short table containing:

| Tool | Brief description | Python/API/CLI access | Reported positions | Kind/name information | Source link | Documentation link |
|---|---|---|---|---|---|---|

Use the maintainers' documentation for factual descriptions. Include a few short technical notes only where readily available. Mark missing details as unknown; do not infer them or pursue an extended investigation. If fewer than four suitable suggestions are readily found, return those found and note the gap.

This is collection and organisation only. Do not rank suitability, estimate integration effort, recommend architecture, inspect implementation source, install or test tools. Evaluation happens later using the gathered material.

## State and handoff

Pending collection by a cheaper, suitably capable agent; no agent assigned and no collection performed under this task. NikolaTesla prepares the brief only. Background is in DESIGN-CHECKPOINT.md if needed.

Save the table as STRUCTURAL-ANALYSIS-TOOLS-FINDINGS.md in this directory with id RES-ANL-TOOLS-001, type tool-research-findings, status draft and stage 00 in YAML front matter. Note the collection date. No target-source access or changes to project design are authorized. Check with the user before committing.
