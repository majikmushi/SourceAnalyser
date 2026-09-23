---
id: STATE-HANDOFF-001
type: design-handoff
status: draft
stage: 00
---

# NikolaTesla design handoff

## Incoming purpose

Once this scaffold is reviewed and committed, the user will move into design mode with NikolaTesla to flesh out project requirements, analyser and analysis architecture, and the proposed stages. Treat ARCH-PRJ-001 objectives as the accepted drafting direction and the existing stage table and transient Stage 00 notes as inputs, not final architecture.

## Inputs

Start with AGENT-ROOT-001 and the scoped design instructions AGENT-DES-001, then ARCH-PRJ-001, BASE-FWK-001, RULE-PRJ-001, STD-DOC-001, STATE-ROOT-001, and STATE-CURRENT-001. Read STD-ANL-DES-001 and SRC-TRACE-001 as candidate design constraints. Inspect the original `Analyser/Transient/Stage 0 - Design.md` only as scratchpad source material. Resolve conflicts or new meaning explicitly rather than silently rewriting project rules.

## Requested design outputs

- Requirements for the analyser and source-analysis process, clearly separating their outcomes.
- Reviewed architecture and source/analysis representation requirements, including uncertainty and fidelity.
- Revised candidate stages, dependencies, handoffs, and acceptance criteria for both tracks.
- Decisions, unresolved questions, source references, and an exact next entry point recorded in `AgentState/`.

## Boundary and return

No source files are uploaded or authorized for analysis at this handoff. Do not fill unknown WiiArtDownloader behaviour from the repository name. The user intends to return after NikolaTesla's design pass for a stage, project-role, and agent-assignment alignment pass. Agent and role assignments must be based on the approved work and capability/authority requirements, not inferred from a model name. Changes to the framework baseline still need explicit adoption.

Related documents: ARCH-PRJ-001, STATE-CURRENT-001.

## First-pass resume note

The current user assignment starts the requirements discussion against main revision `7042f43007b536dac8fa5072b3d15efca7b91c5c`. Three discussion drafts under `Analyser/Transient/` record analyser requirements (REQ-ANL-001), analysis requirements (REQ-SRC-001), and input review (REVIEW-DES-001). The existing six objectives and standards are preserved. This is an incomplete design checkpoint, not completion of the design handoff.

The latest discussion priority is purpose, what the project should do, limitations and bounds. Resume at STATE-CURRENT-001 before resolving detailed requirements. Architecture, source inspection, implementation and final assignments remain outside this pass; the source-read list remains empty. The user approved committing this checkpoint. Detailed draft requirements still need discussion.

Subsequent scope discussion confirmed a reusable analyser and the user renamed the repository to `majikmushi/SourceAnalyser` (D-011/D-012). Draft title, purpose and repository references now reflect that distinction, retaining WiiArtDownloader as the first analysis application and preserving the six objectives. The checkpoint branch is `docs/design-research-handoff`, based on the main revision above. Reuse architecture is deferred.

## Pending research handoff

The user confirmed the outcome in D-018 and subsequently requested structural-analysis tool research, then clarified that a more suitable agent must conduct it. NikolaTesla prepared the research folder, TASK-ANL-RES-001 brief and STATE-ANL-RES-001 checkpoint only. Read `Analyser/Docs/AnalyserDesign/Research/README.md` to resume. Investigation is pending, no agent is assigned, and no findings or tests are claimed. The corrected task is collection only (D-020). Use `docs/design-research-handoff` for this saved checkpoint; it has not been merged into main.

## Note to AgentZero: prerequisite and delegation boundaries

Handover item: HANDOFF-FWK-001. Record the scope issue and proposed safeguards for the requested upstream changes and collection-task delegation. Both actions remain pending; no framework or role definition has been changed here.

### Observed failure

NikolaTesla expanded a request for simple tool suggestions and factual documentation collection into a brief requiring comparative evaluation, integration-effort assessment, shortlisting and recommendations. This exceeded the requested scope and undermined the intended cost split: a cheaper agent gathers and organises material, then a suitably capable Designer reasons over it. The request supplied enough information; this was a scope-control failure, not a missing-input problem. D-020 records the corrected collection brief.

Existing AGENT-DES-001 and RULE-PRJ-001 already require exact scope, bounded work and economical qualified execution. They do not explicitly describe the transition from a missing design prerequisite to a narrowly scoped collection task and back to Designer evaluation.

### Proposed instruction changes for review

Consider a prerequisite/delegation section in the Designer role instructions and a corresponding general task-scoping rule. Review the appropriate reusable AgentZero definition first; any project adoption remains explicit under BASE-FWK-001.

1. Identify the missing input before continuing design: state the information required and the decision or work it enables.
2. Classify the next task as collection, evaluation, design or implementation. Keep these separate unless the user explicitly combines them.
3. Delegate the smallest sufficient task. A collection brief specifies simple inclusion criteria, required facts, references and output format.
4. Keep judgement out of collection briefs. Do not add suitability ranking, integration estimates, recommendations or architecture decisions unless requested.
5. Define an uncertainty exit. Record unknowns or return a question instead of expanding the task to resolve design questions.
6. Check scope before issuing a brief. Every output must trace to the user's request or an agreed prerequisite; remove unsolicited additions. A Designer's belief that extra work might be useful is not an agreed prerequisite.
7. Resume evaluation/design after collection under a separately explicit task. Choose the lowest-cost qualified executor for each bounded task; a model or role name alone establishes neither capability nor authority.

Proposed core wording:

> The Designer's authority does not automatically extend to delegated tasks. Each task receives only the scope and judgement required for its stated outcome. Missing information authorizes identifying a prerequisite, not expanding the assignment.

### Requested follow-up

1. Locate the appropriate upstream reusable instructions and make the bounded prerequisite/delegation changes described above, following the upstream repository's applicable workflow. Identify any corresponding project-level update.
2. Delegate TASK-ANL-RES-001 to a cheaper, suitably capable collection agent. Use the corrected brief in `Analyser/Docs/AnalyserDesign/Research/STRUCTURAL-ANALYSIS-TOOLS-BRIEF.md`: simple tool suggestions, documented facts and links. Do not restore suitability ranking, integration assessment or recommendations to that task.
3. Return the organised collection material to NikolaTesla for the separate evaluation/design pass and report the upstream changes and their state.

Follow-up remains pending. This note records the issue, proposed safeguards and requested actions; it makes no framework responsibility or authority determinations.
