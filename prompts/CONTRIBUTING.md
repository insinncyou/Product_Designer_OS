# Contributing to the Prompt Library

## Add a prompt

1. Choose one primary task and its category: `writing`, `design-system`, `product-design`, `research`, `github`, or `meta`.
2. Create an English `kebab-case` filename from [prompt-template.md](./prompt-template.md).
3. Complete every front matter field and every required section.
4. Add a concise, realistic example and test the prompt with representative inputs.
5. Add the prompt to [catalog.md](./catalog.md) in the same change.
6. Open a pull request from a branch; never commit directly to `main`.

## Front matter

Every prompt must include `title`, `description`, `category`, `version`, `status`, `language`, `supported_tools`, `inputs`, `outputs`, and `last_updated`. Use ISO dates (`YYYY-MM-DD`), semantic versions, an approved status, and a YAML list for tools, inputs, and outputs.

## Prompt review checklist

- The purpose is focused and says what the prompt does not cover.
- Required inputs are sufficient and optional inputs are clearly optional.
- Instructions use named `{{variables}}` and do not depend on hidden chat context.
- Output requirements are observable and include a failure path for missing evidence.
- The quality checklist is specific to the prompt's output.
- The example is short, realistic, and has no sensitive data.
- File and Git instructions check state first, avoid `main`, and seek authorization before high-impact actions.
- The catalog link and metadata are correct.

## Update, deprecate, and remove

Increment `PATCH` for fixes, `MINOR` for backward-compatible capabilities, and `MAJOR` for breaking changes. Update `last_updated` whenever the content changes. To deprecate a prompt, set `status: deprecated`, explain the replacement near the top, retain its catalog entry, and link to the replacement. Do not delete a prompt unless its removal has been explicitly approved; update the catalog in the same change.

## Pull requests

Use a focused branch such as `feat/prompt-name` or `docs/prompt-name`. Before opening a PR, run `git diff --check`, verify Markdown links and heading structure, and confirm the catalog is current. Include the purpose, changed prompts, validation evidence, and any unresolved assumptions in the PR description.
