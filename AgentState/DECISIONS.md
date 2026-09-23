---
id: STATE-DEC-001
type: decision-register
status: draft
stage: 00
---

# Project decisions and proposals

| ID | State | Decision or question | Basis / next action |
|---|---|---|---|
| D-001 | confirmed | Treat the original Stage 00 design notes as transient scratchpad source. | User direction; exact-content move on branch in commit `f22aa7df0fe81b14f6c9ddc6ede401a4e956cbae`. |
| D-002 | accepted for draft | Use the two-track objective wording in ARCH-PRJ-001. | User confirmed the proposed wording; review the full edited document before commit. |
| D-003 | proposed | Use AgentZeroFramework commit `2c7872e70d68b690f99cc216fc07ba3411224aeb` as the explicit project baseline. | BASE-FWK-001; user review needed before recording active adoption. |
| D-004 | proposed | Create separate analyser-design and code-analysis branches with stage, standards, architecture, intake, and output locations. | ARCH-PRJ-001 and user direction to prepare structure before source upload. |
| D-005 | open | Select exact source files and revisions to analyse after upload. | Source read list stays empty until named-file authorization. |
| D-006 | confirmed for draft | Remove the two empty unrelated placeholder documents. | User directed cleanup; both files contain only a newline and no project information. |
| D-007 | planned handoff | NikolaTesla will flesh out requirements, architecture, and proposed stages; stage, role, and agent assignments will be aligned afterward. | User direction; see STATE-HANDOFF-001. This does not assign source access. |
| D-008 | confirmed for draft | Split the former Designer-only root agent instructions into a general `AGENTS.md` entrypoint and a scoped `AgentRoles/DESIGNER.md`. | User corrected the role/entrypoint conflation. Retain AGENT-ROOT-001 for the root logical entrypoint and introduce AGENT-DES-001 for the role. |

A proposal or accepted draft does not by itself activate a framework baseline, authorize source access, or grant repository mutation authority.

## NikolaTesla first-pass continuation

| ID | State | Decision or question | Basis / next action |
|---|---|---|---|
| D-009 | confirmed assignment; documentation draft | Limit this handoff pass to requirements, constraints, outcomes and questions for analyser development and authorized source analysis. Preserve objectives; stop before architecture, source analysis, implementation and final assignments. | Current user instruction; main baseline `7042f43007b536dac8fa5072b3d15efca7b91c5c`. Commit requires user review. |
| D-010 | proposed; awaiting discussion | Review REQ-ANL-001, REQ-SRC-001 and REVIEW-DES-001 in `Analyser/Transient/`. No requirements or architecture newly adopted. | Later user steering asks to establish purpose, what, limitations and bounds first. Resolve that scope before detailed requirements. |
| D-011 | confirmed scope; wording drafted | Develop a reusable analyser. C# remains the initial focus and WiiArtDownloader its first analysis application. Additional language support and multi-project representation remain unresolved. | User: “it will be reuseable”. Preserve all six existing objectives; refine the purpose without selecting architecture. |
| D-012 | confirmed repository rename | Current locator is `majikmushi/SourceAnalyser`; former locator was `majikmushi/WiiArtDownloader`. | User reported rename; GitHub metadata confirms repository ID `1383586805`, default branch `main`, still at `7042f43007b536dac8fa5072b3d15efca7b91c5c`. Rename does not approve the draft, a commit, or framework adoption. |

Earlier rows remain historical records; their old scaffold-review wording does not replace the current assignment. D-003 remains proposed. Neither source authority nor framework adoption has changed.

## Language and chunking discussion

| ID | State | Decision or question | Basis / next action |
|---|---|---|---|
| D-013 | confirmed | C# is the initial source language. | User explicitly answered C#. Do not repeat the C versus C# question. |
| D-014 | preferred direction; details open | Focus the first source-processing stage on chunking and review the original documentation before refining it. | User: “ideally chuncking - what is in the old project documentation”. Stage 01 Chunk already appears in ARCH-PRJ-001. Selection, fidelity and acceptance details remain unresolved. |
| D-015 | proposed terminology clarification | Use analysis project for the selected codebase effort, stage for a major outcome, pass for a bounded traversal or review within a stage, and step for an operation within a pass. | User challenged ambiguous “first analysis” wording. These definitions clarify discussion; they do not approve a revised stage map. |
| D-016 | confirmed clarification | Retain the old chunking documentation as ideas that may inform scope and design. Its mechanisms and stage arrangement are not adopted requirements or a chosen approach. | User: “take that as some ideas - for our scope and design process that may become useful”. Qualifies D-014: continue scope and outcome definition before selecting or refining a chunking design. Preserve the original material and existing objectives. |

## Chunking purpose clarification

| ID | State | Decision or question | Basis / next action |
|---|---|---|---|
| D-017 | confirmed meaning | Chunking means breaking source material into small, context-manageable chunks. | User clarified the purpose explicitly. The earlier assistant emphasis on structural units was too narrow. Structural boundaries may help, but are candidate means rather than the definition. Size measure, context budget, supporting context and boundary policy remain open. |

## Confirmed project outcome — D-018

State: confirmed by the user's “exactly” in response to the outcome summary below. This confirms the project outcome, not the remaining draft requirements, architecture, stage gates, framework adoption, source access or commit permission.

A reusable, staged source-analysis tool and process, initially supporting C#, that:

- Breaks source into context-manageable chunks while preserving source integrity and traceability.
- Supports progressive analysis of structure, behaviour, data and relationships.
- Builds a connected, evidence-based account of how the selected code works.
- Produces behavioural specifications and verification material to support refactoring or reimplementation.
- Keeps work reviewable and resumable, with uncertainties recorded explicitly.

WiiArtDownloader is the first application of that tool and process. The existing six project objectives are preserved. Old chunking mechanisms remain candidate ideas under D-016.

## Research handoff — D-019

State: confirmed task direction. The user requests a research folder and saved state for investigation of Python or easily adaptable structural-analysis tools, with source positions and preferably structure type/name, source/documentation links and technical details. The user then explicitly clarified that a more suitable agent must perform the investigation rather than NikolaTesla.

NikolaTesla's current action is limited to the brief and checkpoint under `Analyser/Docs/AnalyserDesign/Research/`. Investigation is pending and no investigator is assigned. The intervening pipeline, stateful scanning and language-definition discussion is recorded as candidate ideas in STATE-ANL-RES-001, not adopted architecture. Existing commit and source-access boundaries remain in force.

Related documents: STATE-CURRENT-001, BASE-FWK-001, RULE-PRJ-001, TASK-ANL-RES-001, STATE-ANL-RES-001.

## Collection scope correction — D-020

Confirmed user correction: the tool task is simple suggestions and factual documentation collection for a cheaper agent. The first brief exceeded this scope by requiring detailed comparison, integration-effort assessment, shortlisting and recommendations. TASK-ANL-RES-001 is narrowed to a few criteria and one short table with source/documentation links. Missing facts remain unknown. Deeper reasoning is a separate later task. This corrects the execution scope of D-019 without changing the project outcome or granting commit permission.

## AgentZero instruction-improvement note — D-021

Confirmed user direction: add the proposed prerequisite/delegation safeguards to the AgentZero handover. HANDOFF-FWK-001 in `AgentState/DESIGN-HANDOFF.md` records the failure, existing instruction coverage, seven proposed safeguards and core wording. The note requests review; no role, project rule or upstream framework instruction is modified or adopted by it. Commit permission remains separate.

## Requested follow-up — D-022

User requested upstream instruction changes and delegation of the collection task, followed by return of material for later design evaluation. The user then corrected the added ownership and authority declarations as outside this project-design task. HANDOFF-FWK-001 records only the issue, suggested safeguards and requested follow-up. Those actions remain pending.

## Checkpoint commit — D-023

The user instructed “Commit it” after reviewing the handover contents. Save the accumulated design drafts, simple collection brief, checkpoint and upstream issue note on `docs/design-research-handoff`. Remove the rejected responsibility/authority declarations. This checkpoint preserves incomplete work; it does not mark requirements, architecture, research or Stage 00 complete. No merge was requested.
