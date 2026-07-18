# スキル / Skills

**ステータス / Status:** `Planned — early foundation`

Skill は、単一の Prompt より広い、反復可能な実行能力です。通常は指示、ワークフロー、テンプレート、参照資料、例、チェックリスト、検証手順を組み合わせます。

A Skill is a repeatable execution capability broader than a single Prompt. It normally combines instructions, a workflow, templates, references, examples, checklists, and validation steps.

## Prompt と Workflow との違い / Difference from Prompt and Workflow

Prompt は一つの主要タスクの指示、Workflow は作業の順序、Skill はその作業を安定して実行するために必要な資産一式です。Agent は目的に応じてこれらを選びます。

A Prompt instructs one primary task; a Workflow orders the work; a Skill packages the assets needed to perform it reliably. An Agent selects these elements for an objective.

## Skill へ昇格する基準 / Promotion criteria

同じ Prompt が繰り返し使われ、複数ステップ、固定テンプレート、参照、または連携した検証を必要とするときに昇格を検討します。実際の利用で安定性を確認するまでは、空の production-ready Skill パッケージを作成しません。

Consider promotion when the same prompt is repeatedly used and requires multiple steps, fixed templates, references, or coordinated validation. Do not create an empty production-ready Skill package before validating the practice in real use.

## 想定パッケージ構成 / Expected package structure

将来の Skill は、目的を説明する `SKILL.md`、必要に応じた `templates/`、`references/`、`examples/`、`scripts/`、および検証手順を含みます。すべての要素は明確な所有者と更新方法を持つ必要があります。

A future Skill may include `SKILL.md` for purpose, plus `templates/`, `references/`, `examples/`, `scripts/`, and validation instructions as needed. Every element needs clear ownership and an update method.
