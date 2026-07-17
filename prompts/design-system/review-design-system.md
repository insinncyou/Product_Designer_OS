---
title: Review Design System
description: Evaluate supplied design-system evidence for consistency, coverage, accessibility, and governance gaps.
category: design-system
version: 1.0.0
status: active
language: English
supported_tools: [ChatGPT, Claude, Codex, Cursor, Gemini]
inputs: [system_scope, system_evidence, review_criteria]
outputs: [prioritized review findings, evidence map, recommended actions]
last_updated: 2026-07-17
---

# Review Design System

## Purpose

Audit a design system using supplied documentation, tokens, component guidance, or implementation evidence. This prompt does not claim conformance for artifacts it cannot inspect.

## When to use

- You need a structured health check before a release, migration, or governance review.

## When not to use

- You need feedback on one screen or flow; use [Design Review](../product-design/design-review.md).

## Required inputs

- `{{system_scope}}`: Products, platforms, components, and release boundary.
- `{{system_evidence}}`: Links, files, screenshots, token exports, or excerpts to inspect.
- `{{review_criteria}}`: Required standards such as accessibility, naming, coverage, or governance.

## Optional inputs

- `{{severity_model}}`: Existing severity definitions.
- `{{known_constraints}}`: Delivery, technical, or ownership constraints.

## Instructions

```text
You are a design-system reviewer. Assess only the evidence provided.

Scope: {{system_scope}}
Evidence: {{system_evidence}}
Criteria: {{review_criteria}}
Severity model: {{severity_model}}
Constraints: {{known_constraints}}

1. List inspected artifacts and limitations before drawing conclusions.
2. Review consistency, token/component coverage, accessibility, documentation, contribution flow, and adoption only where evidence permits.
3. Report findings in a table: ID, severity, area, evidence, user/team impact, recommendation, and owner/TBD.
4. Use the supplied severity model; if none exists, define Critical/High/Medium/Low and label it as an assumption.
5. Separate verified findings from hypotheses. Do not state that code, Figma, or production behavior was checked unless it was supplied.
6. Conclude with a prioritized action plan and questions needed to complete the review.
```

## Output requirements

- A Markdown review with evidence limitations, prioritized findings, and actions.
- Every finding must point to supplied evidence or be labelled a hypothesis.

## Quality checklist

- [ ] Scope and inspected artifacts are named.
- [ ] Severity and impact are consistent.
- [ ] Accessibility and governance are considered when evidence exists.
- [ ] Recommendations are actionable without overstating certainty.

## Example

**Input:** `system_scope: web button and input components`; `review_criteria: WCAG 2.2 AA, token naming, documentation coverage`.

**Expected result:** A findings table that distinguishes missing evidence from confirmed component gaps.

## Tool-specific notes

- **ChatGPT / Claude / Gemini:** Attach the relevant guides, exports, or screenshots.
- **Codex / Cursor:** State files inspected and avoid claiming runtime verification unless tests were actually run.
