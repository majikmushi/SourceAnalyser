---
document_type: agent_ability_catalog
document_id: DOC-AI-ABILITY-001
title: AI Agent Ability and Routing Profiles
version: 0.1.0
status: working
updated: 2026-09-23
scope: GPT agents available to this project's current Work session
capability_evidence: official_documentation
routing_evidence: provisional_design
project_accuracy: unmeasured
---

# AI Agent Ability and Routing Profiles

## 1. Purpose and scope

Map available GPT models and reasoning levels to the aspects of project roles they are suited to perform. Use this catalogue to select the lowest-cost configuration that meets an assignment's capability and quality requirements.

This catalogue covers all six GPT models exposed for agent selection in the current session, at low, medium, and high reasoning: 18 configurations. Other historical GPT models, specialist models, and reasoning settings outside these three levels are outside this initial routing scope. Availability must be checked again when configuring an actual runner.

The catalogue documents ability and proposed routing. It does not start implementation, authorize source analysis, or launch agents.

## 2. Role, subtype, and agent configuration

| Element | Meaning |
|---|---|
| Role | Responsibility and authority: Designer, Tool Developer, Source Analyst, or Reviewer. |
| Role subtype | A capability-defined specialisation within a role, with a bounded task scope and acceptance criteria. |
| Agent configuration | Exact model ID, reasoning level, instructions, tools, and permitted context assigned to that subtype. |
| Assignment | The particular input, output, scope, constraints, and completion conditions for a task. |
| Qualification | Evidence that a configuration performs that subtype's work to the required standard. |
| Routing | Selection of the lowest expected total cost among eligible configurations. |

A model can support several role subtypes. Several model configurations can qualify for the same subtype. Qualification is specific to the work: success at metadata extraction does not establish architectural design ability.

**Agreed assignment:** Designer / Architectural Concept Designer uses **GPT-6 Astra / high** for high-level architectural concepts, system boundaries, major abstractions, and cross-stage trade-offs.

All Designer subtypes inherit the restriction against inspecting source code, source fragments, source-bearing diffs or tool output, and against changing implementation code. Capability or reasoning effort never expands access. Tool Developer, Source Analyst, and Reviewer assignments require their own explicit scopes.

These are instruction boundaries. Enforcing access mechanically requires runner/tool controls; this document alone does not provide that enforcement.

## 3. Evidence and accuracy

Three evidence categories are used:

- **Documented:** supported by the official sources linked below.
- **Provisional:** project routing recommendations inferred from documented model positioning and task requirements.
- **Measured:** results from project-specific evaluations. No such measurements have been collected for this catalogue.

The model names, supported low/medium/high settings, broad positioning, and published rates are documented. The detailed specialisations, task boundaries, and escalation choices below are provisional.

**Accuracy is unmeasured for every one of the 18 configurations.** No numerical accuracy, reliability percentage, or guaranteed ranking is assigned. Published broad model claims do not establish accuracy for this analyser. A confident answer or agreement between agents is not verification.

## 4. Available models

| Model | Exact selector | Documented positioning | Proposed project use |
|---|---|---|---|
| GPT-6 Astra | `gpt-6-astra` | Most capable model for complex reasoning and demanding work [S1] | Architectural concepts, ambiguous system decisions, difficult synthesis and review |
| GPT-6 Sol | `gpt-6-sol` | Complex coding and agentic workflows [S2] | Detailed design, tool development, mechanism analysis, technical review |
| GPT-6 Luna | `gpt-6-luna` | Efficient, focused work at volume [S3] | Bounded extraction, classification, document maintenance, focused implementation |
| GPT-5.6 Sol | `gpt-5.6-sol` | GPT-5.6 flagship for complex professional work [S4] | Alternative for demanding tasks where local evaluations justify it |
| GPT-5.6 Terra | `gpt-5.6-terra` | Balance of intelligence and cost [S5] | Alternative for bounded design, analysis, implementation, and review |
| GPT-5.6 Luna | `gpt-5.6-luna` | Cost-sensitive work at volume [S6] | Alternative for narrow extraction and routine document tasks |

The official Work model guidance describes improved coding and factual reliability for GPT-6 Sol and Luna, and continued availability of GPT-5.6 models during rollout [S7]. This supports evaluating the newer models first; it does not replace project qualification.

## 5. Reasoning levels

All six models support the three levels in this catalogue [S1–S6]. Use the exact value `medium` in configuration; “med” is a human abbreviation.

| Level | Intended use in this project | Limitation |
|---|---|---|
| Low | Explicit rules, clear inputs, few interacting constraints, readily checked output | Little budget for investigating ambiguity or reconciling many dependencies |
| Medium | Several dependent steps, bounded decisions, local relationships and trade-offs | Broad unresolved architecture can exceed the assignment's appropriate scope |
| High | Interacting constraints, difficult alternatives, subtle behaviour, complex review | Greater effort does not supply missing evidence or guarantee correctness |

These task matches are provisional. Reasoning effort controls reasoning allocation; it is not an accuracy setting. Higher effort may improve a difficult result, but does not establish that Luna high outranks Sol low, or Sol high outranks Astra low. Compare configurations on the same task.

More reasoning can increase latency and token consumption. API reasoning tokens are billed as output tokens [S8]. There is no fixed low-to-medium-to-high price multiplier in this catalogue.

## 6. Configuration ability matrix

Every row below is a proposed routing profile, with **unmeasured project accuracy**. “Limit” describes the initial assignment boundary, not a claim that the model is inherently incapable of other work. Required checks state how to establish correctness before accepting the output.

### 6.1 GPT-6 Astra

| Level | Role subtype and abilities | Initial limit / escalation condition | Required correctness checks |
|---|---|---|---|
| Low | Designer / Focused Decision Adviser; Reviewer / Decision Challenger. Evaluate a bounded architectural question against supplied constraints. | Avoid routine formatting and extraction where a cheaper qualified profile suffices. Increase effort when constraints conflict. | Trace the recommendation to requirements; identify assumptions and rejected alternatives. |
| Medium | Designer / System Design Synthesiser; Reviewer / Cross-Stage Consistency Reviewer. Reconcile stage interfaces, contracts, and competing design proposals. | Escalate unresolved foundational assumptions or extensive interacting trade-offs to high. | Check interface consistency, dependency completeness, and requirement coverage. |
| High | **Designer / Architectural Concept Designer.** Establish system boundaries, abstractions, responsibility allocation, conceptual alternatives, and architectural trade-offs. Also a candidate Reviewer / Architectural Reviewer when separately assigned. | Works from permitted requirements and design material; cannot resolve unseen source behaviour by assumption. Hand settled detail to cheaper profiles. | Review constraints, decision rationale, failure modes, open questions, and downstream consequences. |

### 6.2 GPT-6 Sol

| Level | Role subtype and abilities | Initial limit / escalation condition | Required correctness checks |
|---|---|---|---|
| Low | Tool Developer / Bounded Implementer; Designer / Specification Elaborator. Implement or describe a small component from a settled contract. | Requires explicit interfaces and scope. Escalate conflicting contracts or hidden dependencies. | Check compliance with the contract and targeted acceptance cases. |
| Medium | Designer / Detailed Technical Designer; Tool Developer / Component Developer; Source Analyst / Mechanism Analyst. Develop bounded technical designs, tools, and behavioural descriptions. | Source analysis requires explicit authorization. Escalate cross-stage conceptual changes. | Verify interfaces, state transitions, error paths, and evidence supporting behavioural claims. |
| High | Tool Developer / Complex Debugger; Source Analyst / Relationship Analyst; Reviewer / Technical Consistency Reviewer. Resolve coupled implementation problems and difficult cross-artifact relationships. | Cannot establish undocumented external behaviour without evidence. Route foundational architecture decisions to Astra high. | Check dependency paths, edge cases, counterexamples, and reproductions of reported defects. |

### 6.3 GPT-6 Luna

| Level | Role subtype and abilities | Initial limit / escalation condition | Required correctness checks |
|---|---|---|---|
| Low | Designer / Design Record Maintainer; Source Analyst / Metadata Recorder. Apply an agreed format, record explicit fields, classify using fixed rules. | No discretionary architecture decisions or inferred behaviour. Escalate ambiguous or missing fields. | Check schema, required fields, identifiers, and exact correspondence with permitted input. |
| Medium | Source Analyst / Local Inventory Analyst; Tool Developer / Focused Implementer. Inventory a bounded artifact or implement a small, explicit transformation. | Keep work local and verifiable. Escalate unresolved relationships or implicit state. | Check coverage, references, local cases, and omitted definitions. |
| High | Source Analyst / Bounded Mechanism Analyst; Reviewer / Local Consistency Reviewer. Trace local branches and compare a bounded record against explicit rules. | Do not assume more effort qualifies it for broad system reasoning. Escalate cross-artifact ambiguity to Sol. | Check branch coverage, state updates, error paths, and source-supported claims. |

### 6.4 GPT-5.6 Sol

| Level | Role subtype and abilities | Initial limit / escalation condition | Required correctness checks |
|---|---|---|---|
| Low | Tool Developer / Bounded Implementer; Reviewer / Contract Checker. Perform settled local work. | Use when availability or evaluation supports it; its listed token rates exceed GPT-6 Sol. | Check contract compliance and local acceptance cases. |
| Medium | Designer / Detailed Technical Designer; Tool Developer / Component Developer. Develop a bounded component and its documentation. | Require evidence before preferring it to GPT-6 Sol on quality or total cost. | Check interfaces, requirements, error handling, and verification results. |
| High | Source Analyst / Complex Mechanism Analyst; Reviewer / Technical Reviewer. Investigate difficult local behaviour or implementation defects. | Escalate unresolved conceptual architecture to the agreed Astra high subtype. | Check evidence, interacting states, counterexamples, and regression cases. |

### 6.5 GPT-5.6 Terra

| Level | Role subtype and abilities | Initial limit / escalation condition | Required correctness checks |
|---|---|---|---|
| Low | Designer / Design Record Maintainer; Reviewer / Checklist Reviewer. Normalize documentation and check explicit criteria. | Do not assume a cost advantage over GPT-6 Luna or Sol. Escalate interpretive decisions. | Check field accuracy, scope, and completion against the supplied checklist. |
| Medium | Designer / Bounded Specification Designer; Source Analyst / Local Inventory Analyst. Elaborate settled concepts or analyse a limited artifact. | Keep constraints explicit; escalate broad dependencies or conflicting evidence. | Check requirement coverage, references, and local completeness. |
| High | Designer / Component Design Reviewer; Source Analyst / Bounded Mechanism Analyst. Evaluate component trade-offs or local control flow. | Qualification for complex work remains unmeasured. Escalate unresolved architecture or coupled behaviour. | Check alternatives, error paths, assumptions, and evidence for conclusions. |

### 6.6 GPT-5.6 Luna

| Level | Role subtype and abilities | Initial limit / escalation condition | Required correctness checks |
|---|---|---|---|
| Low | Designer / Record Formatter; Source Analyst / Explicit Field Extractor. Copy, normalize, and classify under fixed rules. | Use a narrow input and deterministic checks; GPT-6 Luna has lower listed token rates. | Check exact values, required fields, and stable identifiers. |
| Medium | Source Analyst / Bounded Inventory Recorder; Reviewer / Record Completeness Checker. Produce a local structured record using a supplied definition. | Escalate interpretation and missing context rather than filling gaps. | Check coverage, unsupported claims, and consistency with permitted evidence. |
| High | Source Analyst / Local Flow Recorder; Reviewer / Bounded Rule Checker. Describe simple local flow or assess a short record against explicit rules. | Additional effort does not establish suitability for broad behavioural reconstruction. | Check branches, ordering, source traceability, and unresolved conditions. |

## 7. Cost reference

Published **Standard-speed ChatGPT/Codex credits per million tokens**, checked 2026-09-23 [S9]:

| Model | Input | Cached input | Output |
|---|---:|---:|---:|
| GPT-6 Luna | 2.5 | 0.25 | 12.5 |
| GPT-5.6 Luna | 5 | 0.5 | 30 |
| GPT-6 Sol | 50 | 5 | 250 |
| GPT-5.6 Terra | 50 | 5 | 300 |
| GPT-5.6 Sol | 100 | 10 | 500 |
| GPT-6 Astra | 250 | 25 | 1,250 |

These are token rates, not task prices, subscription allowances, or API dollar prices. Actual usage depends on token counts, caching, reasoning, retries, tools, service tier, and plan. Recheck rates before implementing cost-based routing. The currently exposed agent service tier is priority; these Standard figures therefore provide a comparison baseline, not an invoice estimate for this session. Published Work Fast mode consumes 2.5 times Standard credits for GPT-6 where available [S9].

Use **expected cost per accepted result**: include execution, verification, retries, and escalation. A configuration with lower token rates can still cost more overall if it requires repeated correction.

## 8. Initial routing policy

1. Establish the authorized role, subtype, input scope, output, and acceptance criteria.
2. Identify the required abilities, complexity, context, tools, and evidence.
3. Filter out unavailable configurations and those outside the role's access limits.
4. Use task-specific qualification results where available. Until then, label selection provisional and validate each result.
5. Select the lowest estimated total-cost eligible configuration. Preserve an explicit user model assignment, including Astra high for architectural concept design.
6. Stop or escalate when evidence is missing, boundaries are uncertain, acceptance checks fail, or the task exceeds the assigned capability scope.
7. Change reasoning effort or model based on the failure. Missing evidence calls for an authorized evidence request, not simply more reasoning.
8. Record the outcome so later routing uses measured performance.

Provisional starting choices:

| Aspect of work | Starting configuration | Escalation target |
|---|---|---|
| Design document formatting and explicit metadata | GPT-6 Luna / low | Luna medium, then Sol if interpretation is required |
| Local inventory or a simple settled implementation | GPT-6 Luna / medium | GPT-6 Sol / medium |
| Bounded mechanism description | GPT-6 Luna / high if locally checkable; otherwise Sol / medium | GPT-6 Sol / high |
| Detailed component design and tool development | GPT-6 Sol / medium | GPT-6 Sol / high |
| Cross-artifact technical analysis | GPT-6 Sol / high | Astra medium or high under an appropriate authorized role |
| High-level architectural concept design | **GPT-6 Astra / high** | User decision for unresolved requirements |
| Routine compliance checks | Deterministic checks where available; Luna / low for bounded semantic checks | Sol / medium for ambiguous findings |

GPT-5.6 configurations remain candidates when availability, compatibility, or measured performance justifies them. They are not mandatory steps in an escalation ladder.

An escalation preserves access restrictions. Assigning a more capable model does not permit a Designer to read source. Any handoff must preserve artifact IDs, input revisions, completed work, failed checks, and unresolved questions.

## 9. Accuracy measurement and qualification

Measure by **model + reasoning level + role subtype + task class + prompt/tool configuration**. Record the actual model revision where available. Retest material configuration changes.

| Dimension | Measurement |
|---|---|
| Structural accuracy | Correct names, kinds, boundaries, parents, and source ordering against verified references |
| Completeness | Required items captured; report omissions separately from incorrect additions |
| Behavioural fidelity | Correct branches, state changes, outputs, side effects, and error handling |
| Traceability | Claims linked to supporting evidence; unsupported claims counted |
| Design quality | Requirement coverage, consistent interfaces, justified trade-offs, and acknowledged assumptions |
| Instruction adherence | Scope violations, unauthorized reads/writes, and ignored stage boundaries |
| Implementation correctness | Acceptance cases passed and defects found through execution or review |
| Operational reliability | Valid outputs, successful tool use, recovery, and reproducibility |
| Efficiency | Actual cost, latency, retries, review effort, and escalation rate per accepted result |

Store sample count, task difficulty, reference method, evaluator, date, failures, and uncertainty alongside any score. Never present a small sample as universal accuracy. Define acceptance thresholds per task class before comparing candidates.

Use synthetic fixtures for tool-development qualification until actual-source access is explicitly authorized. Architecture qualification uses permitted requirements and design material. Numerical qualification results can be added to this document later; none are claimed in this version.

## 10. Relationship to other project documents

This file owns the capability catalogue, configuration profiles, evidence status, and routing recommendations. The proposed root documents have complementary responsibilities:

- `AGENTS.md`: entry instructions and active assignment boundaries.
- `AI_ROLES.md`: responsibilities, subtype definitions, and inherited permissions.
- `AI_ROUTING.md`: selection procedure and runtime routing policy.
- `AI_WORKFLOW.md`: stages, handoffs, outputs, and review points.

Those four documents are planned; this file does not imply they already exist. Existing design material is in [Analyser/Docs/PURPOSE.md](Analyser/Docs/PURPOSE.md) and [Analyser/Docs/Stage 0 - Design.md](Analyser/Docs/Stage%200%20-%20Design.md).

## 11. Sources

Official documentation checked 2026-09-23. Detailed project routing assignments are design recommendations, not vendor benchmarks.

- [S1 — GPT-6 Astra](https://developers.openai.com/api/docs/models/gpt-6-astra)
- [S2 — GPT-6 Sol](https://developers.openai.com/api/docs/models/gpt-6-sol)
- [S3 — GPT-6 Luna](https://developers.openai.com/api/docs/models/gpt-6-luna)
- [S4 — GPT-5.6 Sol](https://developers.openai.com/api/docs/models/gpt-5.6-sol)
- [S5 — GPT-5.6 Terra](https://developers.openai.com/api/docs/models/gpt-5.6-terra)
- [S6 — GPT-5.6 Luna](https://developers.openai.com/api/docs/models/gpt-5.6-luna)
- [S7 — Work and Codex model guidance](https://learn.chatgpt.com/docs/models)
- [S8 — Reasoning models](https://developers.openai.com/api/docs/guides/reasoning)
- [S9 — ChatGPT and Codex pricing](https://learn.chatgpt.com/docs/pricing)

## 12. Changelog

| Version | Date | Change |
|---|---|---|
| 0.1.0 | 2026-09-23 | Initial catalogue: six available models, 18 reasoning profiles, capability-based role subtypes, limitations, cost reference, and accuracy qualification method. |
