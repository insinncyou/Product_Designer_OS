---
title: JTBD Interview Guide
description: Create a neutral jobs-to-be-done interview guide focused on a past behavioral switch.
category: research
version: 1.0.0
status: active
language: English
supported_tools: [ChatGPT, Claude, Codex, Cursor, Gemini]
inputs: [research_objective, participant_profile, product_context]
outputs: [interview guide, probes, consent and synthesis notes]
last_updated: 2026-07-17
---

# JTBD Interview Guide

## Purpose

Prepare a neutral interview guide to understand the circumstances, motivations, anxieties, and trade-offs around a real past switch or attempt to make progress. It does not generate interview findings or validate a market.

## When to use

- You need to learn why people adopted, rejected, or changed a product, workflow, or workaround.

## When not to use

- You need a usability-test script for a prototype rather than a retrospective behavior interview.

## Required inputs

- `{{research_objective}}`: Decision the interviews should inform.
- `{{participant_profile}}`: Who qualifies and relevant context.
- `{{product_context}}`: Product, alternative, or situation under study.

## Optional inputs

- `{{session_length}}`: Available interview time.
- `{{sensitive_topics}}`: Topics requiring special handling.
- `{{incentive_and_consent_process}}`: Approved recruiting and consent language.

## Instructions

```text
You are a UX researcher preparing a Jobs-to-be-Done interview guide. Focus on a specific past event, not hypothetical preferences.

Objective: {{research_objective}}
Participant profile: {{participant_profile}}
Product context: {{product_context}}
Session length: {{session_length}}
Sensitive topics: {{sensitive_topics}}
Consent process: {{incentive_and_consent_process}}

1. State the research objective, assumptions, and participant eligibility. Do not invent screening criteria or consent approval.
2. Build a time-boxed guide: opening/consent, recent-event timeline, first thought, passive and active looking, choice and trade-offs, onboarding/use, outcomes, and closing.
3. Use open, non-leading questions about observable past behavior. Add optional probes; avoid asking participants to predict what they would do.
4. Include interviewer reminders: do not sell, correct, or reveal hypotheses; ask for concrete examples, chronology, alternatives, anxieties, and social context.
5. Add a note-taking template that separates direct quotes, observed facts, interpretations, and follow-up questions.
6. Flag privacy, accessibility, or sensitive-topic handling as TBD unless an approved process was supplied.
```

## Output requirements

- A Markdown interview guide with time boxes, primary questions, optional probes, and interviewer notes.
- Neutral wording; no invented research conclusions or consent requirements.

## Quality checklist

- [ ] Questions target a specific past event and behavioral timeline.
- [ ] Language is open-ended and non-leading.
- [ ] Trade-offs, alternatives, anxieties, and outcomes are explored.
- [ ] Consent, privacy, and sensitive-topic gaps are visible.

## Example

**Input:** `research_objective: understand why freelance designers change invoicing tools`; `participant_profile: freelancers who changed tools in the past six months`.

**Expected result:** A 45-minute guide about the actual switch, not a feature wish list.

## Tool-specific notes

- **ChatGPT / Claude / Gemini:** Review the guide with a qualified researcher before participant use.
- **Codex / Cursor:** Store guides in the approved research location and avoid placing participant data in the repository.
