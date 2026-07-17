---
title: Summarize Document
description: Create a traceable summary tailored to a defined audience and decision need.
category: writing
version: 1.0.0
status: active
language: English
supported_tools: [ChatGPT, Claude, Codex, Cursor, Gemini]
inputs: [source_document, target_audience, summary_goal]
outputs: [structured summary, key evidence, open questions]
last_updated: 2026-07-17
---

# Summarize Document

## Purpose

Condense supplied material into an audience-specific summary while retaining key evidence and uncertainty. This prompt does not replace review of source material for high-stakes decisions.

## When to use

- Stakeholders need an executive brief, handoff, or research readout from a long document.

## When not to use

- The source is incomplete, confidentially restricted, or needs fact checking before summary.

## Required inputs

- `{{source_document}}`: Full source text or approved excerpts.
- `{{target_audience}}`: Intended readers.
- `{{summary_goal}}`: Decision, action, or understanding the summary must support.

## Optional inputs

- `{{length_limit}}`: Maximum words or reading time.
- `{{required_sections}}`: Required headings.

## Instructions

```text
You are a documentation analyst. Summarize only the supplied source.

Source: {{source_document}}
Audience: {{target_audience}}
Goal: {{summary_goal}}
Length limit: {{length_limit}}
Required sections: {{required_sections}}

1. Extract the source's purpose, decisions, evidence, risks, and open questions.
2. Write a structured summary for the target audience. Attribute claims to the source where useful.
3. Separate direct facts from interpretations. Do not fill gaps; list them as `TBD` or open questions.
4. Include recommended next actions only when they are explicitly present in the source; otherwise label them as recommendations.
5. Verify the summary meets the length limit and does not alter certainty, numbers, or ownership.
```

## Output requirements

- A scannable Markdown summary with key points, evidence, and open questions.
- All content must be traceable to the supplied source or labelled as interpretation.

## Quality checklist

- [ ] The summary supports the stated audience and goal.
- [ ] Numbers, decisions, and uncertainty match the source.
- [ ] Important limitations and open questions are retained.
- [ ] Length and required sections are satisfied.

## Example

**Input:** `summary_goal: prepare a five-minute leadership readout`; `length_limit: 350 words`.

**Expected result:** A 350-word brief with decisions, evidence, risks, and explicit unknowns.

## Tool-specific notes

- **ChatGPT / Claude / Gemini:** Upload or paste the complete source so the summary is evidence-bound.
- **Codex / Cursor:** Read only the specified files and cite their relative paths in the output.
