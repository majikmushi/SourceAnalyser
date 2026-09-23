---
id: STD-DOC-001
type: documentation-standard
status: draft
---

# Document standard

## Purpose

Keep documents short, identifiable, and usable one stage at a time.

Every managed Markdown file starts with YAML metadata containing a stable `id`, `type`, and `status` (`draft`, `confirmed`, or `superseded`). Add `stage` for stage documents.

The body has one title, a brief purpose, and the necessary content. Add open questions only when present. Reference related documents by stable ID. An analysis claim identifies its source evidence; an inference is labelled as such.

Track task and stage progress in `AgentState/`, not in duplicate document status lists.
