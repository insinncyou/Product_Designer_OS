---
title: Design Review
description: Deliver prioritized, evidence-bound feedback on a proposed product experience.
category: product-design
version: 1.0.0
status: active
language: English
supported_tools: [ChatGPT, Claude, Codex, Cursor, Gemini]
inputs: [design_scope, design_evidence, user_goal, review_criteria]
outputs: [review findings, questions, prioritized next actions]
last_updated: 2026-07-17
---

# Design Review

## Purpose

Provide constructive, actionable review feedback for a defined design artifact. This prompt does not replace usability testing, accessibility audit, or stakeholder approval.

## When to use

- A flow, prototype, screen, or handoff needs structured feedback before a decision or build.

## When not to use

- You are auditing the system as a whole; use [Review Design System](../design-system/review-design-system.md).

## Required inputs

- `{{design_scope}}`: Screen(s), flow, platform, and release stage.
- `{{design_evidence}}`: Screenshots, prototype, copy, specifications, or notes.
- `{{user_goal}}`: User need and success condition.
- `{{review_criteria}}`: Product, usability, accessibility, content, or technical criteria.

## Optional inputs

- `{{business_goal}}`: Outcome or metric to balance with user needs.
- `{{constraints}}`: Known technical, legal, or time constraints.

## Instructions

```text
You are a product-design reviewer. Review the supplied artifact, not an imagined implementation.

Scope: {{design_scope}}
Evidence: {{design_evidence}}
User goal: {{user_goal}}
Criteria: {{review_criteria}}
Business goal: {{business_goal}}
Constraints: {{constraints}}

1. State the artifact(s) inspected and what cannot be assessed from the evidence.
2. Assess the user goal, task flow, information hierarchy, interaction feedback, content clarity, accessibility, and edge/error states where evidence allows.
3. List findings in priority order. For each include severity, evidence, impact, recommendation, and a question/TBD when needed.
4. Phrase feedback as observable behavior and risk, not personal preference. Separate confirmed issues from hypotheses.
5. Conclude with the three highest-value next actions and the validation needed before approval.
```

## Output requirements

- A concise Markdown review with evidence, severity, and recommended next actions.
- No claim of prototype, code, or user-test inspection unless it was supplied.

## Quality checklist

- [ ] Scope, user goal, and limitations are clear.
- [ ] Each finding connects evidence to user or business impact.
- [ ] Accessibility and error/empty states are considered where relevant.
- [ ] Priorities are justified and actionable.

## Example

**Input:** `design_scope: mobile checkout confirmation`; `user_goal: understand whether payment succeeded`; `design_evidence: confirmation screen screenshot`.

**Expected result:** Feedback about confirmation clarity, recovery path, and unverified screen-reader behavior.

## Tool-specific notes

- **ChatGPT / Claude / Gemini:** Attach the exact screens or prototype context and state any inaccessible interactions.
- **Codex / Cursor:** Link inspected files and keep review feedback separate from implementation changes unless requested.
