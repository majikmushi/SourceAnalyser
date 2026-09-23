---
id: STD-DOC-001
type: documentation-standard
status: draft
---

# Document standard

## Purpose

Keep controlled documents short, identifiable, traceable, and usable one stage at a time.

Every managed Markdown file begins with YAML metadata containing stable `id`, `type`, and document `status` (`draft`, `confirmed`, or `superseded`). Add `stage` to stage documents. A document's status says whether its content has been accepted; it is distinct from task/stage progress and from the confidence or decision state of an individual claim. Use one title and a short purpose. Reference related controlled documents by stable ID, with paths where useful.

An analysis claim cites its source file/revision and artifact location. Mark interpretation as inference and preserve confirmed, proposed, assumed, estimated, unknown, disputed, superseded, or rejected states where relevant. Do not turn a successful syntax parse or rendered view into a claim of semantic equivalence. Record review decisions and unresolved questions without silently promoting draft material.

Track assignments and per-track progress in `AgentState/`. Keep rough notes and unconfirmed source material in `Analyser/Transient/`; these scratchpad files are not controlled documents and may retain their original format. Intake and output area README files describe folder purpose only and do not constitute source evidence or an analysis result.

Related documents: RULE-PRJ-001, STATE-ROOT-001, SRC-TRACE-001.
