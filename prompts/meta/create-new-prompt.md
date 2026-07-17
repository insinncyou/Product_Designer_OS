---
title: Create New Prompt
description: Create a reusable, tool-agnostic Prompt Library entry that meets repository standards.
category: meta
version: 1.0.0
status: active
language: English
supported_tools: [ChatGPT, Claude, Codex, Cursor, Gemini]
inputs: [prompt_goal, target_users, required_inputs, expected_output]
outputs: [new prompt specification, Markdown prompt file, catalog update plan]
last_updated: 2026-07-17
---

# Create New Prompt

## Purpose

Design a new reusable Prompt Library entry for one clear task. This prompt does not create a Skill; use a Skill when delivery requires a multi-step workflow, templates, references, and coordinated checks.

## When to use

- A recurring product-design task needs a direct, portable AI instruction.

## When not to use

- The capability needs orchestration, local tools, multiple artifacts, or a maintained workflow; define a Skill instead.

## Required inputs

- `{{prompt_goal}}`: One primary task and the problem it solves.
- `{{target_users}}`: Intended users and their working context.
- `{{required_inputs}}`: Information the AI must receive to succeed.
- `{{expected_output}}`: Verifiable deliverable and acceptance conditions.

## Optional inputs

- `{{category}}`: Existing library category.
- `{{failure_conditions}}`: Known risks, limitations, or stop conditions.
- `{{example_context}}`: Short realistic example.

## Instructions

```text
You are a Prompt Library editor. Create a reusable prompt for one primary task.

Goal: {{prompt_goal}}
Users: {{target_users}}
Required inputs: {{required_inputs}}
Expected output: {{expected_output}}
Category: {{category}}
Failure conditions: {{failure_conditions}}
Example context: {{example_context}}

1. Decide whether this is a single-call prompt or should become a Skill. If it needs a multi-step workflow, templates, examples, references, and coordinated validation, explain why it should be a Skill and stop before creating a prompt.
2. Choose an existing category and an English kebab-case filename. Do not duplicate an existing prompt's primary purpose; identify the closest related prompt.
3. Create a Markdown file using `prompts/prompt-template.md`. Include complete front matter and all standard sections: Purpose, When to use, When not to use, Required inputs, Optional inputs, Instructions, Output requirements, Quality checklist, Example, and Tool-specific notes.
4. Use explicit `{{variable_name}}` placeholders. Require evidence-bound output, visible TBD/assumptions, path checks before file operations, and authorization before high-risk actions when relevant.
5. Propose the matching catalog row and README/contribution changes if needed. If editing a repository, inspect paths and do not overwrite existing files without authorization.
6. Verify the prompt can run without hidden chat context and works across ChatGPT, Claude, Codex, Cursor, and Gemini.
```

## Output requirements

- A complete prompt-file draft using the library template, plus a catalog-row proposal.
- A clear recommendation to create a Skill instead when the work is inherently multi-step.

## Quality checklist

- [ ] The prompt has one primary, non-duplicative purpose.
- [ ] All standard sections and front matter fields are complete.
- [ ] Variables, outputs, failure handling, and checks are verifiable.
- [ ] The example is realistic and free of sensitive data.
- [ ] Catalog maintenance is included.

## Example

**Input:** `prompt_goal: compare two documented navigation models`; `expected_output: a decision matrix with evidence and unanswered questions`.

**Expected result:** A proposed `product-design/compare-navigation-models.md` prompt and catalog row, unless existing prompts already cover that single task.

## Tool-specific notes

- **ChatGPT / Claude / Gemini:** Return a draft for human review; do not imply repository changes occurred.
- **Codex / Cursor:** Inspect existing prompts, add a new file without overwriting, update the catalog, and show the diff before any commit.
