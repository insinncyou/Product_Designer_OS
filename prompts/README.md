---
title: Product Designer OS Prompt Library
description: Reusable, tool-agnostic AI instructions for product design work.
category: library
version: 1.0.0
status: active
language: English
supported_tools: [ChatGPT, Claude, Codex, Cursor, Gemini]
inputs: [task context, prompt-specific variables]
outputs: [validated AI-assisted deliverable]
last_updated: 2026-07-17
---

# Product Designer OS Prompt Library

This library contains reusable AI instructions for product design, design systems, research, writing, and repository workflows. Each prompt is self-contained: supply its declared inputs, copy its **Instructions** section into a compatible AI tool, and review the output against its checklist.

## Prompt and Skill

- A **Prompt** handles one primary task with limited context and can be copied and run directly.
- A **Skill** is a multi-step capability. It normally combines prompts, templates, examples, checklists, references, and a workflow.

Start with a prompt. Promote it to a skill when dependable delivery requires repeated steps, supporting assets, or coordinated validation beyond one instruction.

## How to use this library

### ChatGPT

Copy a prompt's **Instructions** section and replace every `{{variable_name}}` with real input. Alternatively, upload this `prompts/` directory as Project Knowledge. For file-generation work, explicitly ask ChatGPT to generate a downloadable file.

### Codex

```text
Follow the instructions in:
prompts/writing/generate-markdown.md

Use these inputs:
- document_purpose: ...
- target_audience: ...
- output_filename: ...
```

### Cursor

```text
@prompts/design-system/generate-design-decision.md

Use the selected material to generate a Design Decision document.
```

### Claude

Upload or reference the relevant prompt file, then provide the required inputs and source material in the same request.

### Gemini

Upload the prompt file or paste its **Instructions** section, then replace the variables with task-specific input.

## Variables

Use `{{variable_name}}` placeholders exactly as written. Replace them before execution, or state that an optional variable is unavailable. Never silently invent a missing required input.

## Versioning and status

This library uses semantic versioning:

- **PATCH**: wording, examples, or error corrections.
- **MINOR**: new inputs, checks, or output capabilities.
- **MAJOR**: a breaking change to purpose or execution logic.

Allowed statuses are `draft`, `active`, `deprecated`, and `archived`.

## Authoring rules

- One prompt solves one primary problem.
- Use instructions and outcomes that can be checked; avoid vague requests such as “make it better.”
- Declare inputs, outputs, failure handling, and quality checks.
- Do not fabricate facts, sources, user research, or repository state.
- Check paths before file operations and request authorization for destructive or high-risk actions.
- Do not instruct an agent to modify `main` directly.

Browse the complete inventory in the [Prompt Catalog](./catalog.md). See [CONTRIBUTING.md](./CONTRIBUTING.md) to add or maintain prompts.
