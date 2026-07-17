---
title: "{{prompt_title}}"
description: "{{one_sentence_description}}"
category: "{{category}}"
version: 0.1.0
status: draft
language: English
supported_tools: [ChatGPT, Claude, Codex, Cursor, Gemini]
inputs: ["{{required_input}}"]
outputs: ["{{deliverable}}"]
last_updated: YYYY-MM-DD
---

# {{Prompt name}}

## Purpose

Describe the one problem this prompt solves and the adjacent work it does not solve.

## When to use

- Describe the triggering situation.

## When not to use

- Describe an out-of-scope situation and point to a better workflow if known.

## Required inputs

- `{{required_input}}`: Explain why it is necessary.

## Optional inputs

- `{{optional_input}}`: Explain how it changes the result.

## Instructions

```text
You are {{role}}.

Goal: {{goal}}

Inputs:
- {{required_input}}
- {{optional_input}}

Process:
1. Validate the required inputs. If an input is missing, ask for it or mark the affected result as TBD; do not invent it.
2. Perform the task using only the supplied evidence. Separate facts, assumptions, and recommendations.
3. Produce the deliverable in the requested format.
4. Run the quality checks below before responding.
```

## Output requirements

- Define deliverable format, filename (if applicable), language, and acceptance criteria.

## Quality checklist

- [ ] The primary goal is answered.
- [ ] Required inputs are reflected accurately.
- [ ] Facts, assumptions, and recommendations are distinguishable.
- [ ] The output satisfies the stated format.

## Example

**Input:** `{{required_input}}: Example context`

**Expected result:** A concise description of the deliverable.

## Tool-specific notes

- **ChatGPT / Claude / Gemini:** Paste the Instructions section with populated variables.
- **Codex / Cursor:** Reference this file and provide populated variables; ask before committing or modifying existing files.
