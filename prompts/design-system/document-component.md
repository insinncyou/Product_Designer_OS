---
title: Document Component
description: Create complete, evidence-bound usage guidance for a reusable UI component.
category: design-system
version: 1.0.0
status: active
language: English
supported_tools: [ChatGPT, Claude, Codex, Cursor, Gemini]
inputs: [component_name, component_evidence, intended_users]
outputs: [component documentation, gaps, validation checklist]
last_updated: 2026-07-17
---

# Document Component

## Purpose

Document a reusable UI component so designers and engineers can use it consistently. This prompt does not invent APIs, accessibility behavior, or approved variants.

## When to use

- A component needs a first documentation page or an update after a verified change.

## When not to use

- The artifact is a page-level pattern rather than a reusable component.

## Required inputs

- `{{component_name}}`: Approved component name.
- `{{component_evidence}}`: Design specs, code API, tokens, accessibility notes, and known states.
- `{{intended_users}}`: People who will apply the guidance.

## Optional inputs

- `{{related_components}}`: Related or alternative components.
- `{{migration_notes}}`: Known deprecations or changes.

## Instructions

```text
You are a design-system technical writer. Create component documentation from verified evidence.

Component: {{component_name}}
Evidence: {{component_evidence}}
Users: {{intended_users}}
Related components: {{related_components}}
Migration notes: {{migration_notes}}

1. Validate the evidence and record missing information as TBD; do not infer behavior from the component name.
2. Create Markdown sections: Purpose, Anatomy, Variants and states, When to use, When not to use, Content guidance, Interaction behavior, Accessibility, Tokens, Implementation/API notes, Examples, Related components, and Change history.
3. Add tables only where they clarify variants, states, or properties. Keep design and implementation terminology aligned with supplied evidence.
4. Mark unverified accessibility behavior, responsive behavior, or API details as TBD and list owners/questions.
5. Finish with a validation checklist that a designer and engineer can apply before release.
```

## Output requirements

- Complete GFM component documentation with explicit unknowns.
- Guidance must distinguish usage policy from implementation detail.

## Quality checklist

- [ ] Purpose, scope, variants, states, and non-use cases are documented.
- [ ] Accessibility and content guidance are evidence-based or TBD.
- [ ] Tokens and related components are linked when supplied.
- [ ] Examples match the documented rules.

## Example

**Input:** `component_name: Status badge`; `component_evidence: four semantic states, text label required, color token list`.

**Expected result:** Documentation that specifies state meanings, label guidance, token usage, and missing keyboard behavior as TBD.

## Tool-specific notes

- **ChatGPT / Claude / Gemini:** Include screenshots or API excerpts alongside written specifications.
- **Codex / Cursor:** Link only verified local paths and do not change component code while documenting it unless explicitly asked.
