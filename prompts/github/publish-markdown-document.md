---
title: Publish Markdown Document
description: Safely prepare a Markdown document for publication in a Git repository.
category: github
version: 1.0.0
status: active
language: English
supported_tools: [ChatGPT, Claude, Codex, Cursor, Gemini]
inputs: [repository_path, document_content, document_topic, target_directory]
outputs: [saved Markdown document, validation report, commit and PR suggestions]
last_updated: 2026-07-17
---

# Publish Markdown Document

## Purpose

Guide a code agent through safely adding a Markdown document to a Git repository. It prepares, validates, and reports changes; it does not commit, push, merge, or overwrite files without explicit authorization.

## When to use

- A reviewed Markdown artifact needs to be saved into an existing Git repository.

## When not to use

- There is no repository, no approved document content, or the task is to edit an existing file without a reviewed diff.

## Required inputs

- `{{repository_path}}`: Local path to the target Git repository.
- `{{document_content}}`: Reviewed Markdown to publish.
- `{{document_topic}}`: Plain-English topic used for branch and filename suggestions.
- `{{target_directory}}`: Intended repository-relative location.

## Optional inputs

- `{{output_filename}}`: Preferred filename.
- `{{work_type}}`: `docs`, `feat`, or `chore`.
- `{{authorization}}`: Explicit scope for commit and/or push, if granted.

## Instructions

```text
You are a repository maintainer publishing a Markdown document safely.

Repository: {{repository_path}}
Document: {{document_content}}
Topic: {{document_topic}}
Target directory: {{target_directory}}
Filename: {{output_filename}}
Work type: {{work_type}}
Authorization: {{authorization}}

1. Confirm repository_path is a Git repository. Inspect `git status`, current branch, remotes, repository guidance (README, CONTRIBUTING, AGENTS), and target directory before writing.
2. Never modify `main` directly. If on `main`, create and switch to a suitable branch such as `docs/{{topic}}`, `feat/{{topic}}`, or `chore/{{topic}}`; preserve unrelated working-tree changes.
3. Generate an English kebab-case `.md` filename if none is valid. Check the target path and do not overwrite an existing file without explicit authorization.
4. Save the document in the correct directory. Check whether README, catalog, or index files need an update; update only when required by repository convention.
5. Run `git status`, `git diff --check`, and `git diff`. Validate relative Markdown links and heading structure.
6. Generate a Conventional Commit suggestion and a PR title. Do not commit, push, open a PR, or merge unless authorization explicitly grants that action.
7. Report changed files, validation results, unresolved issues, suggested commit message, and suggested PR title. If authorized to commit or push, report each action after it succeeds.
```

## Output requirements

- A newly saved Markdown file or a clear explanation of why saving stopped.
- Validation report containing Git status, diff checks, link/heading checks, and suggested Conventional Commit message.
- No commit, push, PR, merge, or overwrite without explicit authorization.

## Quality checklist

- [ ] Repository and current branch were checked.
- [ ] `main` was not modified directly.
- [ ] Target path and filename were validated before writing.
- [ ] `git diff --check` and `git diff` were run.
- [ ] README/catalog/index impact was considered.
- [ ] Commit and PR suggestions are present; unsafe actions were authorized first.

## Example

**Input:** `repository_path: /work/product-designer-os`; `document_topic: empty state guidance`; `target_directory: product-design-patterns`; `work_type: docs`.

**Expected result:** A new `docs/empty-state-guidance` branch when starting on main, a non-overwriting `empty-state-guidance.md`, validation results, and `docs(product-design-patterns): add empty state guidance` as a suggested commit.

## Tool-specific notes

- **ChatGPT / Claude / Gemini:** These tools may provide the artifact and suggested commands but should not claim to have written, committed, or pushed files unless connected to a repository tool.
- **Codex / Cursor:** Execute the checks in order, preserve unrelated changes, and request confirmation before every commit, push, or PR creation.
