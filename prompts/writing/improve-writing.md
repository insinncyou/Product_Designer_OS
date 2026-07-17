---
title: Improve Writing
description: Improve a draft's clarity, structure, and accessibility without changing supported meaning.
category: writing
version: 1.0.0
status: active
language: English
supported_tools: [ChatGPT, Claude, Codex, Cursor, Gemini]
inputs: [source_draft, target_audience, writing_goal]
outputs: [revised draft, change summary, unresolved issues]
last_updated: 2026-07-17
---

# Improve Writing

## Purpose

Improve readability, structure, and precision while preserving the draft's supported meaning. This prompt does not verify external facts or create new policy.

## When to use

- A document is accurate but difficult to scan, overly dense, or inconsistent.

## When not to use

- The task requires a new document from source evidence; use [Generate Markdown](./generate-markdown.md).

## Required inputs

- `{{source_draft}}`: Text to revise.
- `{{target_audience}}`: Readers and level of expertise.
- `{{writing_goal}}`: Desired outcome, such as brevity, plain language, or executive readability.

## Optional inputs

- `{{style_guide}}`: Required voice, terminology, or Markdown conventions.
- `{{non_negotiable_terms}}`: Terms that must not change.

## Instructions

```text
You are an editor. Revise the draft below without adding unsupported facts or changing approved decisions.

Draft: {{source_draft}}
Audience: {{target_audience}}
Goal: {{writing_goal}}
Style guide: {{style_guide}}
Terms to preserve: {{non_negotiable_terms}}

1. Identify ambiguity, repetition, unexplained jargon, and structural problems.
2. Rewrite for the stated audience and goal. Keep facts and certainty levels intact; label any unclear source statement as `TBD` rather than guessing.
3. Preserve required terminology and meaningful Markdown structure.
4. Return: (a) revised draft, (b) a short change summary, and (c) unresolved questions or risks.
5. Check that no claim, metric, attribution, or commitment was introduced without support.
```

## Output requirements

- A complete revised draft, followed by concise change and issue summaries.
- Clear, audience-appropriate language with preserved factual meaning.

## Quality checklist

- [ ] No unsupported facts or commitments were added.
- [ ] Required terms and intended meaning remain intact.
- [ ] Headings, lists, and links remain usable.
- [ ] Open ambiguities are visible.

## Example

**Input:** `writing_goal: reduce a release note to plain English for customers`.

**Expected result:** A shorter release note and a note identifying any unclear technical claim.

## Tool-specific notes

- **ChatGPT / Claude / Gemini:** Paste the draft and request tracked changes only if the tool supports them.
- **Codex / Cursor:** Inspect the target file before editing and show a diff; do not overwrite unrelated content.
