---
title: Write Product Requirements Document
description: Draft a decision-ready PRD from supplied product evidence and constraints.
category: product-design
version: 1.0.0
status: active
language: English
supported_tools: [ChatGPT, Claude, Codex, Cursor, Gemini]
inputs: [problem_statement, target_users, evidence, goals, constraints]
outputs: [PRD, assumptions, open questions, acceptance criteria]
last_updated: 2026-07-17
---

# Write Product Requirements Document

## Purpose

Create a testable PRD that aligns product, design, engineering, and stakeholders around a bounded problem. This prompt does not invent strategy, user research, estimates, or approvals.

## When to use

- A team has enough discovery evidence to define a proposed feature, improvement, or experiment.

## When not to use

- The problem, target user, or desired outcome is not yet known; conduct discovery first.

## Required inputs

- `{{problem_statement}}`: User and business problem to address.
- `{{target_users}}`: Primary users and relevant segments.
- `{{evidence}}`: Research, data, existing behavior, and source links.
- `{{goals}}`: Desired outcomes and measurable success signals.
- `{{constraints}}`: Scope, platform, policy, technical, and timeline limits.

## Optional inputs

- `{{stakeholders}}`: Accountable owners and reviewers.
- `{{non_goals}}`: Explicit exclusions.
- `{{release_plan}}`: Proposed rollout or experiment plan.

## Instructions

```text
You are a product manager and product designer co-authoring a PRD. Use only supplied evidence.

Problem: {{problem_statement}}
Target users: {{target_users}}
Evidence: {{evidence}}
Goals: {{goals}}
Constraints: {{constraints}}
Stakeholders: {{stakeholders}}
Non-goals: {{non_goals}}
Release plan: {{release_plan}}

1. Validate required inputs. Mark missing decisions, metrics, ownership, and evidence as `TBD`; do not fabricate them.
2. Write Markdown sections: Summary, Problem, Users and jobs, Evidence, Goals and success metrics, Non-goals, Scope, User stories, Functional requirements, UX and accessibility requirements, Edge cases, Dependencies and risks, Measurement, Rollout, Open questions, and Acceptance criteria.
3. Make each requirement testable. Label recommendations and assumptions explicitly. Separate facts from proposed behavior.
4. Ensure scope is consistent with constraints and non-goals. Flag contradictions rather than resolving them silently.
5. Run a final traceability check: each major requirement must support a stated goal or constraint.
```

## Output requirements

- A GitHub-compatible Markdown PRD with measurable acceptance criteria.
- Explicit `TBD` items for missing evidence, owner, metric, or decision.

## Quality checklist

- [ ] Problem, users, goals, and non-goals are distinct.
- [ ] Requirements are testable and traceable to evidence or constraints.
- [ ] Accessibility, edge cases, risks, and measurement are addressed.
- [ ] Assumptions and open questions are visible.

## Example

**Input:** `problem_statement: New users abandon account setup before connecting a data source`; `goals: increase completed setup`; `constraints: web only, no new backend service`.

**Expected result:** A scoped onboarding PRD with measurable completion criteria and a TBD baseline metric.

## Tool-specific notes

- **ChatGPT / Claude / Gemini:** Provide research excerpts and distinguish decisions from ideas.
- **Codex / Cursor:** Write to a new path only after checking it; do not update production code or commit without authorization.
