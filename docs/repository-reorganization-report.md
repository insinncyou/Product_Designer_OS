# Repository Reorganization Report / リポジトリ再編成レポート

**Migration date / 移行日:** 2026-07-18  
**Branch / ブランチ:** `chore/reorganize-repository-architecture`  
**Status / 状態:** `Ready for review — not committed`

## 概要 / Summary

移行前は tokens、components、product patterns、workflow がトップレベルに分散していました。移行後は、共有 UI 資産を `design-system/` に集約し、広いプロダクト体験パターンを独立させ、workflow を複数領域で使う実行プロセスとして配置しました。Prompt Library の有効なカテゴリー構造は維持しています。

Before migration, tokens, components, product patterns, and workflow were scattered at the top level. After migration, shared UI assets are grouped under `design-system/`, broader product-experience patterns are independent, and workflow is placed as a cross-module execution process. The active Prompt Library category structure is preserved.

## Path mapping / パスマッピング

| Previous path | New path | Action | Notes |
| --- | --- | --- | --- |
| `design-tokens/README.md` | `design-system/tokens/README.md` | Moved | Git-aware move; navigation expanded. |
| `components/README.md` | `design-system/components/README.md` | Moved | Git-aware move; navigation expanded. |
| `product-design-patterns/README.md` | `product-experience-patterns/README.md` | Moved and adapted | Preserved content; clarified scope boundary. |
| `workflow/design-system-workflow_v0.1.md` | `workflows/design-system/design-system-workflow.md` | Moved and renamed | Git-aware move; added workflow front matter. |
| `prompts/prompts.md` | `docs/using-prompts-in-chatgpt-projects.md` | Moved and rewritten | Reframed as bilingual documentation, not a catalog prompt. |

## Created / 作成した資料

Created architecture documents in `docs/`; Design System foundations, token scaffolds, component and pattern templates, governance drafts, and decision templates; `workflows/README.md`; and `skills/README.md`. Empty category directories were created only where approved as future homes; no fake component or Skill packages were added.

## Preserved, removed, and links / 保全、削除、リンク

All existing substantive content was preserved. The formerly top-level `design-tokens/`, `components/`, `product-design-patterns/`, and `workflow/` directories became empty after their only files were moved and were removed. `prompts/` active categories and catalog entries were not reorganized. Root navigation now points to the new entry points; `prompts/README.md` now links to the moved ChatGPT Projects guide.

## Known gaps and deferred work / 既知の不足と延期事項

Design tokens retain `TBD` values, and no component or pattern specification is claimed complete. Governance roles, release cadence, product-specific accessibility conformance, and concrete theme decisions remain Draft. Public portfolio and GitHub Pages are deferred and remain disabled.

## Validation / 検証

The old-path search found no active stale links; historical references remain only in this mapping table and the pre-migration repository audit. Relative Markdown links resolve successfully. The obsolete top-level directories were removed after their contents moved. `git diff --check` and Git status were reviewed. No repository Markdown lint or link-check command was configured, and no dependencies were installed. No commit or push has been performed.

## Recommended next action / 推奨する次の作業

Review the architecture boundaries and Draft documents, then validate one real Design System asset or case study before expanding the library.
