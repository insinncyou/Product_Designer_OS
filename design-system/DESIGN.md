# DESIGN / デザインシステムの入口

**ステータス / Status:** `Draft`

## 目的 / Purpose

この文書は Design System の入口です。全ルールを複製するのではなく、対象範囲、参照順序、判断の階層、更新経路を案内します。

This is the entry point to the Design System. It does not duplicate every rule; it guides scope, reading order, decision hierarchy, and update paths.

## 参照順序 / Reading order

1. [Foundations](./foundations/design-principles.md) で共有原則を確認します。 / Start with shared principles.
2. [Tokens](./tokens/README.md) で意味と依存関係を確認します。 / Check token meaning and dependencies.
3. [Components](./components/README.md) と [Patterns](./patterns/README.md) で再利用単位を選びます。 / Select reusable building blocks and patterns.
4. [Design Decisions](./design-decisions/README.md) と [Governance](./governance/governance-model.md) で判断と変更方法を確認します。 / Check decisions and governance for rationale and change process.

## 判断の階層 / Decision hierarchy

`Product intent → Foundations → Design decisions → Tokens → Components → Patterns → Implementation → Validation`。下位の資産は上位の意図と決定に矛盾してはなりません。

`Product intent → Foundations → Design decisions → Tokens → Components → Patterns → Implementation → Validation`. Lower-level assets must not contradict higher-level intent and decisions.

## 範囲 / Scope

共有 UI の設計資産を扱います。オンボーディング、収益化、権限設計などのより広い体験パターンは [Product Experience Patterns](../product-experience-patterns/README.md) で扱います。

It covers shared UI design assets. Broader experience patterns such as onboarding, monetization, and permission architecture live in [Product Experience Patterns](../product-experience-patterns/README.md).
