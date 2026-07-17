---
title: Synthesize Research
description: Turn supplied research evidence into traceable findings, opportunities, and open questions.
category: research
version: 1.0.0
status: active
language: English
supported_tools: [ChatGPT, Claude, Codex, Cursor, Gemini]
inputs: [research_material, research_questions, decision_context]
outputs: [research synthesis, evidence map, opportunities, limitations]
last_updated: 2026-07-17
---

# Synthesize Research

## Purpose

Synthesize provided qualitative or mixed-method research into traceable patterns that support a stated decision. This prompt does not claim statistical significance or generalize beyond the sample.

## When to use

- Interview notes, survey results, support feedback, or observations need an evidence-led readout.

## When not to use

- Raw data lacks adequate consent, anonymization, or permission for the requested use.

## Required inputs

- `{{research_material}}`: Anonymized notes, quotes, data, and source identifiers.
- `{{research_questions}}`: Questions the synthesis must answer.
- `{{decision_context}}`: Product or design decision this will inform.

## Optional inputs

- `{{sample_description}}`: Recruitment, sample size, and limitations.
- `{{analysis_method}}`: Existing coding scheme or synthesis method.

## Instructions

```text
You are a UX research analyst. Synthesize only the supplied, authorized research material.

Material: {{research_material}}
Questions: {{research_questions}}
Decision context: {{decision_context}}
Sample: {{sample_description}}
Method: {{analysis_method}}

1. State the material reviewed, sample limitations, and unanswered questions before analysis.
2. Code recurring behaviors, needs, barriers, contexts, and language. Keep source IDs or quote references traceable without exposing personal data.
3. Produce: Executive summary, Findings, Evidence for each finding, Tensions or counterexamples, Opportunities, Implications for the decision, Limitations, and Open questions.
4. Distinguish direct evidence, interpretation, and recommendation. Do not turn frequency alone into importance or claim causality without support.
5. Do not create personas, jobs, metrics, or quotes that are not supported. Flag insufficient evidence as TBD.
6. Check that every major conclusion answers a research question or is explicitly out of scope.
```

## Output requirements

- A Markdown synthesis linking findings to anonymized evidence.
- Explicit limitations, counterexamples, and uncertainty.

## Quality checklist

- [ ] Research material and sample limits are stated.
- [ ] Each finding has traceable evidence.
- [ ] Evidence, interpretation, and recommendation are separate.
- [ ] Personal and sensitive data are not repeated unnecessarily.

## Example

**Input:** `research_questions: What blocks first-time setup?`; `research_material: 8 anonymized interview summaries`.

**Expected result:** A synthesis with evidence-linked setup barriers, counterexamples, and validated next questions.

## Tool-specific notes

- **ChatGPT / Claude / Gemini:** Remove personal data before upload and retain source IDs for traceability.
- **Codex / Cursor:** Read only approved research files and avoid committing raw participant data or secrets.
