---
id: REQ-SRC-001
type: source-analysis-requirements-discussion
status: draft
stage: 00
---

# Requirements for using the analyser on authorized C# source

## Purpose and standing

Define the intended analysis outcomes and limits before source intake, inspection, or architecture. Baseline: `majikmushi/SourceAnalyser` (formerly `majikmushi/WiiArtDownloader`) main at `7042f43007b536dac8fa5072b3d15efca7b91c5c`. WiiArtDownloader is the first analysis application of the reusable analyser. Exact source read list: `[]`. No source contents were read and no source-derived finding is asserted here.

All requirements are discussion drafts. Objective-derived requirements preserve ARCH-PRJ-001; candidate details need review. Proposed acceptance evidence is future work, not completed validation.

## Expected outcome

An evidence-based account of selected source structure, behaviour, data, and relationships, followed where selected by behavioural contracts and verification material that support decisions about refactoring or reimplementation. The account must expose incomplete knowledge and distinguish existing behaviour from intended replacement behaviour. The original file/class/language arrangement does not dictate a replacement design.

## Requirements and proposed acceptance evidence

| ID | Requirement | Basis / standing | Proposed acceptance evidence |
|---|---|---|---|
| REQ-SRC-101 | Before each source pass, bind exact permitted paths and revisions/content identities, objective, stage, outputs, and allowed actions. | RULE-PRJ-001; local constraint | A reviewed assignment names every source input; uploads or adjacent files are not implicit permission. |
| REQ-SRC-102 | Preserve the source baseline and trace each substantive observation to source revision and artifact/location. | ARCH-PRJ-001 objectives 2–4; objective-derived | A reviewer can navigate from each claim to the evidence used. Missing context is recorded explicitly. |
| REQ-SRC-103 | Establish selected structure before describing behaviour; progress through bounded, reviewable passes. | ARCH-PRJ-001 objective 3; provisional outline and scratchpad; candidate sequencing | Structural records do not imply behavioural analysis; subsequent claims show their required evidence and prior review state. |
| REQ-SRC-104 | Inventory definitions, interfaces, inputs/outputs, data structures, calls, and state access within the authorized scope. | ARCH-PRJ-001 objective 3; candidate inventory detail | A scope coverage record identifies inspected, excluded, and unresolved artifacts and records missing dependency context. |
| REQ-SRC-105 | Describe selected mechanisms including decisions, transformations, side effects, errors, and ordering constraints. | ARCH-PRJ-001 objectives 3, 5; objective-derived/candidate detail | Claims cite evidence; pseudocode or diagrams identify omissions and approximation instead of claiming full equivalence. |
| REQ-SRC-106 | Link supported call, data-flow, shared-state, and initialization relationships without reading unassigned dependencies. | ARCH-PRJ-001 objective 3; candidate relationship detail | Each relationship states evidence and confidence; unresolved endpoints remain unresolved until separately authorized. |
| REQ-SRC-107 | Distinguish observations, interpretations, assumptions, unknowns, disputes, proposals, and accepted decisions. | ARCH-PRJ-001 objective 4; STD-DOC-001; objective-derived | A reviewer can identify each claim's state and basis; tool success cannot promote inference to fact. |
| REQ-SRC-108 | Produce language-independent behavioural contracts for selected capabilities, separating existing behaviour from proposed changes. | ARCH-PRJ-001 objective 5 and purpose; objective-derived | Contracts identify inputs, outputs, state effects, errors and observable ordering where relevant, with traceable known limits. Bugs and quirks await Q-S2. |
| REQ-SRC-109 | Define verification cases and record actual results separately from planned checks and unsupported equivalence claims. | ARCH-PRJ-001 objective 5; SRC-TRACE-001; objective-derived | Each selected contract has an agreed verification basis and explicit evidence gaps; no execution inferred from static inspection. |
| REQ-SRC-110 | Record per-pass coverage, unresolved questions, reviewed outcomes and a precise next entry point independently of tool progress. | ARCH-PRJ-001 objective 6; STATE-ROOT-001; objective-derived | A fresh context can resume and distinguish an extracted artifact from an analysed or verified one. |

## Constraints

- No behaviour is inferred from the repository name, documentation wording, or the mere presence of a source path.
- Authorization to read is distinct from permission to run, annotate, modify, build, or test source. Future assignments must resolve these actions explicitly.
- The analyser must have validation evidence relevant to the intended pass before its outputs are relied on. Validation of the tool does not establish accuracy of all analysis claims.
- Missing project files, referenced libraries, generated content or runtime context may limit conclusions; they do not authorize scope expansion.
- A behaviour contract does not approve a replacement architecture or a target language. Architecture, implementation, and final agent/role assignment are outside this pass.

## Questions

| ID | Question | Why it matters / suggested discussion position |
|---|---|---|
| Q-S1 | Which capabilities should eventual analysis explain, and what decisions should that account support first? | Sets analysis depth and stopping criteria. Exact filenames/revisions can be supplied in a later source assignment; none are needed to discuss intended outcomes. |
| Q-S2 | Should later reimplementation preserve every observable behaviour, including defects and quirks, or separate behaviours to retain from approved corrections? | Recommend recording existing behaviour faithfully and making corrections separate explicit decisions. |
| Q-S3 | Should analysis initially be static only? What later runtime evidence, if any, would be needed to support the selected contracts? | Recommend static analysis first, with execution/testing only under a separate assignment; do not equate static findings with demonstrated runtime equivalence. |
| Q-S4 | What makes an analysis pass sufficient: structural coverage, reviewed behavioural coverage, contract cases, or a defined combination? Who accepts remaining unknowns? | Needs measurable per-scope completion criteria. Recommend explicit coverage and uncertainty review rather than unsupported “fully analysed” claims. |
| Q-S5 | What C# language/project/runtime baseline and supporting context will eventually be available, and which output forms are actually needed? | Determines what can be concluded and how it will be consumed. No source, project file, dependency or target platform is assumed. |

## Review boundary

Discuss Q-S1–Q-S5 and the analysis deliverables before architecture. Source selection remains a later exact-file authorization gate. Neither analysis nor verification has begun.

Related: ARCH-PRJ-001, RULE-PRJ-001, SRC-TRACE-001, STATE-CURRENT-001, REQ-ANL-001, and `DESIGN-INPUT-REVIEW.md` in this directory.
