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

Related documents: STATE-CURRENT-001, BASE-FWK-001, RULE-PRJ-001.
