---
title: Generate Markdown Document
description: Generate a complete, evidence-bound, GitHub Flavored Markdown document.
category: writing
version: 1.0.0
status: active
language: English
supported_tools: [ChatGPT, Claude, Codex, Cursor, Gemini]
inputs: [document_purpose, target_audience, source_content, repository_path, output_filename, constraints]
outputs: [Markdown document, suggested filename, quality-check summary]
last_updated: 2026-07-17
---

# Generate Markdown Document

## Purpose

Generate a complete Markdown document from supplied evidence. This prompt does not research missing facts, approve content, or overwrite existing files without authorization.

## When to use

- You need a new README, guide, decision record, research summary, or other `.md` artifact.
- You have a defined purpose, audience, and source material.

## When not to use

- You need to improve an existing draft without changing its structure; use [Improve Writing](./improve-writing.md).
- The required facts have not been provided or verified.

## Required inputs

- `{{document_purpose}}`: The document's decision, task, or knowledge goal.
- `{{target_audience}}`: Intended readers and their expected knowledge.
- `{{source_content}}`: Facts, decisions, links, and approved source material.
- `{{repository_path}}`: Target repository or `not applicable`.
- `{{constraints}}`: Scope, language, style, confidentiality, and required sections.

## Optional inputs

- `{{output_filename}}`: Preferred filename; otherwise propose one.
- `{{target_directory}}`: Intended location for a file-capable environment.
- `{{include_mermaid}}`: Whether a diagram materially improves understanding.

## Instructions

```text
You are a documentation architect producing a GitHub-compatible Markdown artifact.

Inputs:
- document_purpose: {{document_purpose}}
- target_audience: {{target_audience}}
- source_content: {{source_content}}
- repository_path: {{repository_path}}
- target_directory: {{target_directory}}
- output_filename: {{output_filename}}
- constraints: {{constraints}}
- include_mermaid: {{include_mermaid}}

1. Validate required inputs. Do not invent absent facts. Mark unresolved content as `TBD` and explicit, reasonable interpretations as `Assumption:`.
2. Propose an English kebab-case `.md` filename if output_filename is absent or invalid.
3. Draft one complete UTF-8, GitHub Flavored Markdown document. Use exactly one H1, a logical heading hierarchy, descriptive links, and fenced code blocks with language identifiers. Use tables, task lists, blockquotes, or Mermaid only when they improve the stated purpose.
4. Clearly distinguish supplied facts, assumptions, and recommendations. Preserve uncertainty rather than filling gaps.
5. If you can write files, inspect target_directory and the proposed path first. Do not overwrite an existing file; choose a new filename or ask for authorization. Then create the .md file. If you cannot write files, return the complete Markdown and the suggested filename.
6. Check H1 count, heading order, link targets, code fence languages, filename, and that every claim is supported by source_content or labelled appropriately.
7. In chat, provide only a short summary, filename, location/status, and quality-check result; do not repeat the full document when it was written to a file.
```

## Output requirements

- A UTF-8 `.md` artifact compatible with GitHub Flavored Markdown.
- One H1 only; headings must not skip levels without reason.
- Suggested filename must be English `kebab-case.md`.
- Missing evidence must be `TBD`; assumptions and recommendations must be labelled.

## Quality checklist

- [ ] The document addresses the supplied purpose and audience.
- [ ] Exactly one H1 is present and Markdown syntax is valid.
- [ ] Facts are sourced from input; uncertainty is visible.
- [ ] Existing files were not overwritten without authorization.
- [ ] Filename and output path were checked.

## Example

**Input:** `document_purpose: Explain the empty-state policy`; `target_audience: product designers and engineers`; `source_content: Empty states explain why a list is empty and offer one recovery action`; `constraints: English, include accessibility guidance`.

**Expected result:** `empty-state-policy.md` with a concise policy, examples, and an accessibility section.

## Tool-specific notes

- **ChatGPT / Claude / Gemini:** Request the full Markdown in the response and save it locally after review.
- **Codex / Cursor:** Provide `repository_path` and `target_directory`; the agent must inspect the path and report file changes before any commit.
