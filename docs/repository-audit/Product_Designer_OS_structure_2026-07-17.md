# Repository Overview

- **Repository name:** Product_Designer_OS
- **Scan date:** 2026-07-17
- **Total folders:** 17
- **Total files:** 29

This inventory reflects the repository before this audit document was created. The scan excludes `.git/`, `.DS_Store`, `node_modules/`, `dist/`, `build/`, `.idea/`, `.vscode/`, and common generated cache directories (`__pycache__/`, `.cache/`, `.next/`, and `coverage/`).

The repository is an early-stage, bilingual (Japanese/English) product-design knowledge base. Its most developed area is the reusable Prompt Library; the domain folders currently contain draft README scaffolding.

# Directory Tree

```text
Product_Designer_OS
├── .github/
│   └── pull_request_template.md
├── ai-product-design/
│   └── README.md
├── case-studies/
│   └── README.md
├── components/
│   └── README.md
├── design-system/
│   └── README.md
├── design-tokens/
│   └── README.md
├── learning-log/
│   └── README.md
├── product-design-patterns/
│   └── README.md
├── prompts/
│   ├── design-system/
│   │   ├── document-component.md
│   │   ├── generate-design-decision.md
│   │   └── review-design-system.md
│   ├── github/
│   │   └── publish-markdown-document.md
│   ├── meta/
│   │   └── create-new-prompt.md
│   ├── product-design/
│   │   ├── design-review.md
│   │   └── write-prd.md
│   ├── research/
│   │   ├── jtbd-interview.md
│   │   └── synthesize-research.md
│   ├── writing/
│   │   ├── generate-markdown.md
│   │   ├── improve-writing.md
│   │   └── summarize-document.md
│   ├── CONTRIBUTING.md
│   ├── README.md
│   ├── catalog.md
│   ├── prompt-template.md
│   └── prompts.md
├── ux-methodology/
│   └── README.md
├── workflow/
│   └── design-system-workflow_v0.1.md
├── .gitignore
└── README.md
```

# File Inventory

| Path | Type | Status | Description |
| --- | --- | --- | --- |
| `.github/pull_request_template.md` | Markdown | Placeholder | Provides a Japanese pull-request template with sections and checklists for repository contributions. |
| `.gitignore` | Other | Active | Defines repository ignore rules for macOS, editors, logs, temporary files, and generated dependencies or builds. |
| `README.md` | Markdown | Draft | Introduces the bilingual Product Designer OS knowledge base and links to its planned content areas. |
| `ai-product-design/README.md` | Markdown | Draft | Scaffolds a future collection of principles, patterns, evaluation methods, and ethical guidance for AI product experiences. |
| `case-studies/README.md` | Markdown | Draft | Defines the intended structure for documenting reusable project case studies, decisions, outcomes, and lessons. |
| `components/README.md` | Markdown | Draft | Outlines planned reusable UI-component documentation, including anatomy, states, accessibility, and examples. |
| `design-system/README.md` | Markdown | Draft | Describes the planned design-system knowledge area for principles, governance, quality standards, and contribution practices. |
| `design-tokens/README.md` | Markdown | Draft | Defines the future design-token area for token hierarchy, naming, themes, synchronization, and change management. |
| `learning-log/README.md` | Markdown | Draft | Establishes a future learning-log format for recording discoveries, experiments, evidence, and open questions. |
| `product-design-patterns/README.md` | Markdown | Draft | Scaffolds a library of proven product-design approaches for recurring experience-design problems. |
| `prompts/CONTRIBUTING.md` | Markdown | Active | Specifies how to add, validate, catalog, and review Prompt Library entries. |
| `prompts/README.md` | Markdown | Active | Serves as the Prompt Library landing page, with metadata, usage guidance, structure, and quality expectations. |
| `prompts/catalog.md` | Markdown | Active | Catalogs the available reusable prompts by category, purpose, status, and version. |
| `prompts/design-system/document-component.md` | Prompt | Active | Instructs an AI tool to create evidence-bound, implementation-ready guidance for a reusable UI component. |
| `prompts/design-system/generate-design-decision.md` | Prompt | Active | Instructs an AI tool to draft a traceable design decision record with alternatives and trade-offs. |
| `prompts/design-system/review-design-system.md` | Prompt | Active | Instructs an AI tool to audit supplied design-system evidence for gaps in consistency, coverage, accessibility, and governance. |
| `prompts/github/publish-markdown-document.md` | Prompt | Active | Instructs an AI coding agent to safely prepare and validate a Markdown document for repository publication. |
| `prompts/meta/create-new-prompt.md` | Prompt | Active | Instructs an AI tool to design a reusable Prompt Library entry that meets repository standards. |
| `prompts/product-design/design-review.md` | Prompt | Active | Instructs an AI tool to provide prioritized, evidence-bound feedback on a proposed product experience. |
| `prompts/product-design/write-prd.md` | Prompt | Active | Instructs an AI tool to draft a decision-ready product requirements document from supplied evidence and constraints. |
| `prompts/prompt-template.md` | Prompt | Placeholder | Provides the front-matter and section template for authoring a new reusable prompt. |
| `prompts/prompts.md` | Prompt | Draft | Contains Chinese-language operational notes for using an uploaded prompt file in a ChatGPT Project workflow. |
| `prompts/research/jtbd-interview.md` | Prompt | Active | Instructs an AI tool to prepare a neutral jobs-to-be-done interview guide about a past behavioral switch. |
| `prompts/research/synthesize-research.md` | Prompt | Active | Instructs an AI tool to turn supplied research into traceable findings, opportunities, and open questions. |
| `prompts/writing/generate-markdown.md` | Prompt | Active | Instructs an AI tool to generate a complete, evidence-bound GitHub-Flavored Markdown document. |
| `prompts/writing/improve-writing.md` | Prompt | Active | Instructs an AI tool to improve a draft’s clarity and structure without changing its supported meaning. |
| `prompts/writing/summarize-document.md` | Prompt | Active | Instructs an AI tool to create an audience-specific, evidence-preserving summary of supplied material. |
| `ux-methodology/README.md` | Markdown | Draft | Outlines a future UX-methodology collection spanning discovery, research, prototyping, validation, and learning. |
| `workflow/design-system-workflow_v0.1.md` | Markdown | Draft | Documents a versioned, general-purpose workflow connecting strategy, design-system artifacts, tokens, components, and implementation. |

# Folder Summary

| Top-level folder | Purpose | Files | Current maturity | Missing contents / obvious gaps |
| --- | --- | ---: | --- | --- |
| `.github/` | Repository collaboration configuration. | 1 | Placeholder | Issue templates, workflow automation, CODEOWNERS, and contribution-policy support are not present. |
| `ai-product-design/` | Planned knowledge base for designing AI-powered product experiences. | 1 | Draft scaffold | The principles, patterns, evaluation framework, and ethics content listed in its README are not yet present. |
| `case-studies/` | Planned archive of reusable project case studies. | 1 | Draft scaffold | No case-study templates or completed case studies are present. |
| `components/` | Planned documentation library for reusable UI components. | 1 | Draft scaffold | No component inventory, specifications, examples, or accessibility guidance files are present. |
| `design-system/` | Planned home for design-system strategy, governance, and standards. | 1 | Draft scaffold | No design principles, governance model, contribution process, or standards documents are present. |
| `design-tokens/` | Planned home for reusable visual and behavioral token definitions. | 1 | Draft scaffold | No token source files, schemas, naming rules, or theme definitions are present. |
| `learning-log/` | Planned record of ongoing product-design learning and experiments. | 1 | Draft scaffold | No dated entries, log template, or index is present. |
| `product-design-patterns/` | Planned library of repeatable solutions to product-design problems. | 1 | Draft scaffold | No individual pattern records, taxonomy, or examples are present. |
| `prompts/` | Reusable, tool-agnostic AI instructions for product-design work. | 18 | Active | The core library is established; potential gaps include an explicit changelog and a documented deprecation/archive location. |
| `ux-methodology/` | Planned UX research and design-methods reference. | 1 | Draft scaffold | No method guides, templates, decision criteria, or example artifacts are present. |
| `workflow/` | Cross-cutting documented workflows. | 1 | Early draft | Contains one v0.1 design-system workflow; related workflows and index/navigation are not present. |

# Cross References

```text
README.md
  ↓ introduces and links to
design-system/ · design-tokens/ · components/ · product-design-patterns/
ai-product-design/ · ux-methodology/ · case-studies/ · learning-log/
workflow/ · prompts/

workflow/design-system-workflow_v0.1.md
  ↓ describes the relationship among
product strategy → design philosophy → design principles → UI patterns
  → components → design tokens → implementation

design-system/README.md
  ↓ is intended to connect
design-tokens/README.md ↔ components/README.md

prompts/README.md
  ↓ governs and introduces
prompts/CONTRIBUTING.md → prompts/prompt-template.md → prompts/catalog.md
  ↓ indexes
writing/ · design-system/ · product-design/ · research/ · github/ · meta/

prompts/catalog.md
  ↓ links directly to
every active reusable prompt in the categorized prompt subdirectories

prompts/github/publish-markdown-document.md
  ↓ supports repository-document publishing workflows, including the style of
Markdown documentation used across this knowledge base
```

# Observations for Future Reorganization

- The root README is the primary navigation point; the eight knowledge-domain folders are consistently named but are presently README-only scaffolds.
- `prompts/` is the only substantive content collection and has its own governance, template, catalog, metadata standard, and category taxonomy.
- `workflow/` has a cross-cutting design-system workflow that conceptually overlaps with `design-system/`, `design-tokens/`, and `components/`; its eventual ownership or linking model should be made explicit.
- `prompts/prompts.md` is a Chinese-language usage note outside the current catalog and does not use the Prompt Library’s standard front matter, so its role should be clarified during later reorganization.
