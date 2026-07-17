---
title: Generate Design Decision
description: Document a design decision with evidence, alternatives, trade-offs, and follow-up.
category: design-system
version: 1.0.0
status: active
language: English
supported_tools: [ChatGPT, Claude, Codex, Cursor, Gemini]
inputs: [decision_statement, context, evidence, alternatives]
outputs: [design decision record, assumptions, follow-up actions]
last_updated: 2026-07-17
---

# Generate Design Decision

## Purpose

Create a concise, traceable Design Decision Record (DDR) for a design-system or product-design choice. It does not make the decision on behalf of accountable owners.

## When to use

- A team needs to record why a component, token, pattern, or governance choice was made.

## When not to use

- The decision is not yet framed or evidence is unavailable; first conduct discovery or research.

## Required inputs

- `{{decision_statement}}`: The decision being proposed or recorded.
- `{{context}}`: Problem, affected users/systems, constraints, and owner.
- `{{evidence}}`: Research, accessibility requirements, metrics, or references.
- `{{alternatives}}`: Options considered, including status quo when relevant.

## Optional inputs

- `{{decision_status}}`: Proposed, accepted, superseded, or rejected.
- `{{implementation_plan}}`: Rollout, migration, and dependencies.

## Instructions

```text
You are a design-system documentation lead. Create a Design Decision Record from the supplied evidence.

Decision: {{decision_statement}}
Context: {{context}}
Evidence: {{evidence}}
Alternatives: {{alternatives}}
Status: {{decision_status}}
Implementation plan: {{implementation_plan}}

1. Validate that the decision, context, evidence, and alternatives are present. Do not invent validation, stakeholder approval, or outcomes.
2. Produce Markdown with: Decision, Status, Context, Evidence, Options considered, Rationale, Consequences, Risks and mitigations, Assumptions/TBD, and Follow-up.
3. For every option, state benefits, costs, and why it was selected or not selected. Separate facts from recommendations.
4. Identify accessibility, consistency, implementation, and migration implications when evidence supports them. Mark missing analysis as TBD.
5. Verify the record enables a future reader to understand what was decided, why, and what remains unresolved.
```

## Output requirements

- A single Markdown DDR with named owner/status when supplied.
- Traceable evidence and explicit trade-offs; no fabricated approval or result.

## Quality checklist

- [ ] Decision scope and affected systems are clear.
- [ ] Alternatives include reasons, not just names.
- [ ] Facts, assumptions, and recommendations are distinguished.
- [ ] Consequences, risks, and follow-up are actionable.

## Example

**Input:** `decision_statement: Use semantic color tokens for component states`; `alternatives: primitive tokens only, semantic tokens`; `evidence: dark-mode migration requires stable meaning`.

**Expected result:** A DDR explaining the selected semantic-token approach, migration consequences, and unresolved naming questions.

## Tool-specific notes

- **ChatGPT / Claude / Gemini:** Paste approved evidence and name unknown approvers as TBD.
- **Codex / Cursor:** Save only after checking the target directory and existing filenames; do not modify an ADR/DDR without authorization.
