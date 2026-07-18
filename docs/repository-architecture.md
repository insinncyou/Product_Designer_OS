# Repository Architecture / リポジトリアーキテクチャ

**ステータス / Status:** `Active` — 構造方針。各コンテンツの成熟度は個別に `Draft` または `Proposed` と表示します。

## 目的と階層 / Purpose and hierarchy

このリポジトリは、上位の意図から下位の実装資産、さらに実践の証拠までを接続します。`docs/` は全体方針、`design-system/` は共有 UI の基盤、領域フォルダーは専門知識、`workflows/`・`prompts/`・`skills/` は実行能力、`case-studies/`・`learning-log/` は証拠と振り返りを扱います。

This repository connects high-level intent to implementation assets and then to evidence from practice. `docs/` holds repository guidance; `design-system/` holds shared UI foundations; domain directories hold expertise; `workflows/`, `prompts/`, and `skills/` hold execution capabilities; `case-studies/` and `learning-log/` hold evidence and reflection.

## トップレベルの責務 / Top-level responsibilities

| Directory | Responsibility |
| --- | --- |
| `docs/` | Blueprint, architecture, roadmap, guides, and migration records. |
| `design-system/` | Shared foundations, tokens, components, interface patterns, governance, and decisions. |
| `product-experience-patterns/` | Product-level and cross-channel experience patterns. |
| `ux-methodology/` | Research and design methods. |
| `ai-product-design/` | AI product-experience knowledge. |
| `workflows/` | Cross-module execution processes. |
| `prompts/` | Mature, bounded, reusable AI instructions. |
| `skills/` | Future multi-step capability packages. |
| `case-studies/` | Reusable evidence from project practice. |
| `learning-log/` | Ongoing discoveries, experiments, and reflection. |

## Design System 内の責務 / Design System responsibilities

Tokens, components, and Design System patterns all govern reusable interface decisions, so they belong together under `design-system/`. Tokens provide named values and semantics; components apply them to reusable UI building blocks; patterns compose components into repeatable interface and interaction solutions. This co-location makes their dependencies and change impact explicit.

`design-system/patterns/` is for interface solutions composed from multiple components, such as filtering, validation, or data management. `product-experience-patterns/` is for broader product choices such as onboarding, trust, collaboration, permissions, monetization, and cross-channel journeys. A product-experience pattern may use Design System assets without owning or governing them.

## 依存関係 / Dependencies

`Foundations → Tokens → Components → Design System Patterns → Product Experience Patterns → Workflows → Practice → Case Studies / Learning Log`. Design decisions and governance constrain and record changes across the Design System. Prompts and Skills support execution but do not replace source knowledge.

## 命名規則 / Naming conventions

Use lowercase `kebab-case` filenames, one focused concept per document, and `README.md` as a directory entry point. Use `_template.md` only for reusable authoring templates. Version belongs in front matter when a document is versioned; do not place version numbers in filenames unless an external compatibility constraint requires it.

## 新しいコンテンツの置き場所 / Where new content belongs

Place reusable shared UI rules in `design-system/`; product-level experience decisions in `product-experience-patterns/`; method guidance in `ux-methodology/`; AI-specific experience guidance in `ai-product-design/`; executable sequences in `workflows/`; single-task instructions in `prompts/`; multi-asset repeatable capabilities in `skills/`; and evidence or reflection in `case-studies/` or `learning-log/`. When uncertain, record the decision in a design-decision document rather than duplicating content.
