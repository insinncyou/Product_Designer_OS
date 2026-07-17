# Design System Workflow

> **Purpose**
>
> このドキュメントは、Design Systemを構成する各設計ドキュメントの役割・関係・参照順序・更新プロセスを整理し、Product Designerが一貫した判断でDesign Systemを構築・運用できるようにするための汎用ワークフローです。
>
> 特定のプロダクトや組織に依存せず、さまざまなDesign Systemの初期設計・拡張・改善に適用できる雛形として利用できます。

## 1. Design Systemの全体像

Design Systemは、ComponentやDesign Tokenだけで構成されるものではありません。

プロダクトの目的、提供したい体験、設計原則、具体的な判断、UIパターン、Component、Design Token、実装までを一貫した構造で接続する必要があります。

```text
Mission / Vision / Product Strategy
    ↓
Design Philosophy
    ↓
UX Philosophy
    ↓
Design Principles
    ↓
Design Decision
    ↓
Pattern Library
    ↓
Component Guideline
    ↓
Design Token
    ↓
Figma Library
    ↓
Code Implementation
    ↓
Validation / Feedback
    ↓
Design Decisionへ還元
```

上位レイヤーほど「なぜそうするのか」を定義し、下位レイヤーほど「どのように具体化・実装するか」を定義します。

## 2. ドキュメントの役割と関係

### 2.1 `DESIGN.md`

`DESIGN.md`はDesign System全体の入口です。

詳細なルールをすべて記載するのではなく、Design Systemの目的、全体構造、各ドキュメントの役割、参照順序、更新方針を案内します。

主な記載内容は以下です。

- Design Systemの目的
- 対象範囲
- 全体アーキテクチャ
- Decision Hierarchy
- ドキュメント一覧
- 利用者別の参照方法
- 更新フロー
- Contribution方針

`DESIGN.md`は、Design Systemを初めて参照する人が最初に読むEntry Pointとして機能します。

### 2.2 `design-philosophy.md`

`design-philosophy.md`は、プロダクトやブランドの設計思想を定義します。

この文書が扱うのは、個別のUIルールではなく、Design System全体の最上位にある「Why」です。

主な記載内容は以下です。

- Missionとの関係
- Visionとの関係
- Product Philosophy
- Primary Users
- UX Value
- Product Personality
- Design Systemが担う役割
- 判断時の最上位基準

この文書は更新頻度が低く、事業方針・プロダクト戦略・ブランドの方向性が大きく変化した場合に見直します。

### 2.3 `ux-philosophy.md`

`ux-philosophy.md`は、ユーザーにどのような体験や状態を提供するかを定義します。

画面の見た目ではなく、ユーザーがどのように理解し、感じ、判断し、行動できる状態を目指すかを扱います。

主な記載内容は以下です。

- UX Goal
- Target Experience
- Experience Principles
- UX Heuristics
- Success Metrics
- Design Systemとの関係

`design-philosophy.md`が「なぜ」を定義するのに対し、`ux-philosophy.md`は「どのような体験を提供するか」を定義します。

### 2.4 `design-principles.md`

`design-principles.md`は、Product Designerが日常の設計・レビューで守るべき原則を定義します。

主なテーマの例は以下です。

- Consistency
- Usability
- Accessibility
- Scalability
- Engineering Alignment
- Documentation First
- AI Collaboration

各Principleには、最低限以下を含めます。

- Principle Name
- Why
- Guideline
- Review Criteria
- 必要に応じてAI Interpretation

Design Principlesは、Design Decision、Pattern、Component Guideline、Design Tokenを判断する際の共通基準です。

### 2.5 `design-decision.md`

`design-decision.md`は、特定の設計課題に対する具体的な判断と、その理由を記録します。

Design Principlesが普遍的な原則を扱うのに対し、Design Decisionは個別の課題に対する結論を扱います。

例：

- Dark ModeのSurface階層
- Component Tokenの導入基準
- Alert背景色の生成方法
- OverlayとScrimの使い分け
- Breakpointの選定理由
- Tableの行選択表現
- Form Validationの表示方針

推奨テンプレートは以下です。

```markdown
# DD-001 Decision Title

## Status

Proposed / Accepted / Deprecated / Superseded

## Context

解決すべき課題と背景。

## Decision

採用する方針。

## Rationale

その方針を採用する理由。

## Alternatives Considered

比較した代替案。

## Consequences

メリット、デメリット、影響範囲。

## References

関連するDesign Principles、Figma、Issue、実装、外部資料。
```

Design Decisionが増えた場合は、1ファイルに集約せず、Indexと個別ファイルへ分割することを推奨します。

```text
decisions/
├── README.md
├── DD-001-component-token-strategy.md
├── DD-002-dark-mode-surface-model.md
└── DD-003-overlay-and-scrim.md
```

### 2.6 `pattern-library.md`

`pattern-library.md`は、複数のComponentを組み合わせて実現する画面・業務フロー単位の設計パターンを定義します。

例：

- Search and Filter
- Data Table
- Dashboard
- Detail Page
- Form
- Empty State
- Error and Feedback
- Comparison
- Multi-step Flow

PatternはComponentよりも上位の再利用単位です。

たとえばAdvanced Filterは、Trigger、Filter Panel、Form Controls、Applied Filter Chips、Result Count、Reset / Apply Actionなど複数のComponentで構成されます。このようなものは単一ComponentではなくPatternとして管理します。

### 2.7 `component-guideline.md`

`component-guideline.md`は、Component単位の使用ルールと仕様を定義します。

各Componentは、最低限以下を含めます。

- Purpose
- Anatomy
- Properties
- Variants
- Boolean Properties
- Instance Swap
- States
- Tokens
- Accessibility
- Do / Don't
- Responsive Behavior
- Content Guidance
- Related Patterns

例：

```text
components/
├── button.md
├── input.md
├── alert.md
├── dialog.md
├── menu.md
├── tabs.md
└── table.md
```

Component Guidelineは、Figma Componentと実装Componentの両方を同じ考え方で設計するための仕様書です。

### 2.8 `token-architecture.md`

`token-architecture.md`は、Design Tokenのレイヤー構造、責務、依存関係、追加基準を定義します。

推奨する基本構造は以下です。

```text
Primitive
    ↓
Palette
    ↓
Semantic
    ↓
Component Token
    ↓
Component
```

各レイヤーの責務は以下です。

| Layer | Responsibility | Example |
|---|---|---|
| Primitive | 生の値 | `gray/1000` |
| Palette | ブランド・システム上の色体系 | `primary/500` |
| Semantic | 意味・用途 | `color/text/primary` |
| Component Token | Component固有の役割 | `button/background/default` |
| Component | 実際のUI表現 | Button、Input、Dialog |

依存関係は上から下へ一方向にします。

禁止例：

- ComponentがPrimitiveを直接参照する
- ComponentがPaletteを直接参照する
- Semantic TokenがComponent Tokenを参照する
- 同じ意味の値を複数箇所へ重複定義する

### 2.9 `naming-convention.md`

`naming-convention.md`は、Design Token、Component、Variant、Property、Pattern、文書の命名規則を定義します。

Design Tokenの基本形式例：

```text
{collection}/{category}/{role}/{state}
```

例：

```text
color/text/primary
color/surface/default
color/border/danger
button/background/hover
input/border/focus
```

命名時は見た目より役割を優先します。

推奨原則：

- Role over appearance
- Avoid implementation details
- Consistent hierarchy
- No hard-coded meaning
- Predictable naming
- Searchable naming

## 3. Decision Hierarchy

複数のルールや文書が競合した場合は、以下の順序で判断します。

| Priority | Document | Purpose |
|---:|---|---|
| 1 | `design-philosophy.md` | プロダクトとデザインの存在理由 |
| 2 | `ux-philosophy.md` | 提供したい体験 |
| 3 | `design-principles.md` | 設計時の共通原則 |
| 4 | `design-decision.md` | 個別課題に対する判断 |
| 5 | `pattern-library.md` | 画面・業務フロー単位の設計 |
| 6 | `component-guideline.md` | Component単位の仕様 |
| 7 | `token-architecture.md` | 実装可能な値と依存構造 |
| 8 | Figma / Code | 実際のデザイン・実装 |

下位レイヤーが上位レイヤーと矛盾する場合は、上位レイヤーを優先します。

ただし、実装上の制約や技術的な問題が判明した場合は、下位レイヤーだけを修正するのではなく、Design Decisionへ背景と判断を記録し、必要に応じて上位文書を見直します。

## 4. Design System構築ワークフロー

### Step 1：目的と適用範囲を定義する

最初に、Design Systemを作る目的を明確にします。

確認項目：

- どのプロダクト・ブランドを対象にするか
- どの利用者を支援するか
- どの課題を解決するか
- Design Systemの責任範囲はどこまでか
- Figmaと実装のどちらをSingle Source of Truthにするか
- 誰が意思決定・運用・レビューを担当するか

成果物：

- `DESIGN.md`
- `design-philosophy.md`

### Step 2：提供したいUXを定義する

ユーザーに提供する体験を明文化します。

確認項目：

- ユーザーが達成したいことは何か
- どのような不安・迷い・負荷を減らすか
- どのような状態を成功とみなすか
- どのUX品質を優先するか

成果物：

- `ux-philosophy.md`

### Step 3：設計原則を定義する

日常の設計判断で繰り返し使う原則を定義します。

確認項目：

- 一貫性
- 使いやすさ
- アクセシビリティ
- 拡張性
- 実装との整合性
- ドキュメント運用
- AIや自動生成との連携

成果物：

- `design-principles.md`

### Step 4：既存UIを監査する

既存プロダクトがある場合は、ComponentやTokenを作り始める前にUI Inventoryを作成します。

確認項目：

- 同じ目的に複数のUIが存在していないか
- 色・余白・Typographyに重複や矛盾がないか
- Componentの状態が不足していないか
- デザインと実装が一致しているか
- Product固有UIと共通UIを分離できるか
- Accessibility上の問題がないか

成果物例：

- UI Inventory
- Component Audit
- Token Audit
- Accessibility Audit
- Design Debt List

### Step 5：Design Decisionを作成する

監査や新規設計で発見した課題について、複数案を比較して判断を記録します。

判断の流れ：

```text
課題を発見
    ↓
上位思想との整合性を確認
    ↓
既存ルールで解決できるか確認
    ↓
代替案を比較
    ↓
実装影響を確認
    ↓
Decisionを記録
    ↓
関係者レビュー
    ↓
Accepted
```

成果物：

- `design-decision.md`
- または`decisions/DD-xxx-*.md`

### Step 6：Foundationを設計する

UIの基盤となるDesign Tokenを定義します。

対象例：

- Color
- Typography
- Spacing
- Sizing
- Radius
- Border
- Elevation
- Motion
- Breakpoint
- Layout

Token追加時は、以下の順序で検討します。

```text
既存Semantic Token
    ↓
既存Component Token
    ↓
Semantic Token追加
    ↓
Component Token追加
    ↓
Palette追加
    ↓
Primitive追加
```

Primitive追加は最後の手段とします。

成果物：

- `token-architecture.md`
- `naming-convention.md`
- Foundation別の仕様書
- Figma Variables
- Code Tokens

### Step 7：Component Architectureを設計する

Componentの責務、粒度、再利用性、状態、APIを設計します。

新規Componentを作る前に、以下の順番で確認します。

1. 既存Componentで実現できるか
2. Variant追加で対応できるか
3. Property追加で対応できるか
4. Patternで解決できるか
5. 新規Componentが必要か

Component Tokenは、以下の場合に導入を検討します。

- 状態が多い
- 広範囲で再利用される
- Theme変更の影響を受ける
- 独立して進化する必要がある
- Semantic Tokenだけでは意図を表現しづらい

成果物：

- Component Architecture
- Component Inventory
- Figma Components
- Code Components

### Step 8：Component Guidelineを作成する

Componentの構造だけでなく、いつ・なぜ・どのように使うかを文書化します。

成果物：

- `component-guideline.md`
- または`components/*.md`

### Step 9：Pattern Libraryを作成する

複数Componentで構成される再利用可能な画面・フローを定義します。

判断基準：

- 複数画面で繰り返されるか
- Component単体では利用方法を説明できないか
- 業務フローや情報設計を含むか
- Product Designerの判断差を減らせるか

成果物：

- `pattern-library.md`
- または`patterns/*.md`

### Step 10：Figmaと実装を同期する

ドキュメント、Figma、実装を同じ変更単位で更新します。

```text
Design Decision
    ↓
Documentation
    ↓
Figma Variables
    ↓
Figma Components
    ↓
Code Tokens
    ↓
Code Components
    ↓
Storybook / Documentation Site
```

変更時の確認項目：

- Markdownを更新したか
- Figma Variablesを更新したか
- Figma Componentsを更新したか
- Code Tokensを更新したか
- Code Componentsを更新したか
- Accessibilityを確認したか
- Migrationが必要か
- Breaking Changeか

### Step 11：検証する

Design Systemは作成して終わりではなく、利用結果を検証します。

検証例：

- Component利用率
- 重複Component数
- Design Token利用率
- デザインと実装の差分
- 新規画面の制作時間
- Accessibilityエラー
- Product Designerからの問い合わせ
- Engineerからの実装上の問題
- ComponentのOverride率
- 未定義パターンの発生頻度

### Step 12：知識を上位レイヤーへ還元する

繰り返し発生する課題は、より上位のルールへ昇格させます。

```text
個別実装の問題
    ↓
Design Decision
    ↓
複数箇所で繰り返される
    ↓
Component Guideline / Pattern
    ↓
さらに普遍化できる
    ↓
Design Principles
```

逆に、不要になったルールはDeprecatedまたはSupersededとして履歴を残します。

## 5. 日常のUI設計ワークフロー

Product Designerが新規画面や改善を行う場合は、以下の順序で進めます。

```text
要件・課題を確認
    ↓
Design Philosophyを確認
    ↓
UX Philosophyを確認
    ↓
Design Principlesを確認
    ↓
既存Design Decisionを検索
    ↓
既存Patternを検索
    ↓
既存Componentを検索
    ↓
既存Tokenを確認
    ↓
UIを設計
    ↓
Design Review
    ↓
Figma・実装・文書を同期
```

既存ルールで解決できない場合は、その場で独自ルールを追加せず、Design Decision候補として記録します。

## 6. 更新先の判断フロー

```text
新しい課題・要望
    ↓
既存ルールで解決できるか？
    ├── Yes → 既存ルールを適用
    └── No
         ↓
特定課題への具体的判断か？
    ├── Yes → Design Decision
    └── No
         ↓
複数画面・業務フローで再利用するか？
    ├── Yes → Pattern Library
    └── No
         ↓
単一Componentの仕様か？
    ├── Yes → Component Guideline
    └── No
         ↓
値・Theme・Stateの定義か？
    ├── Yes → Design Token
    └── No
         ↓
繰り返し使う普遍的な判断基準か？
    ├── Yes → Design Principles
    └── No
         ↓
提供したい体験に関わるか？
    ├── Yes → UX Philosophy
    └── No → Design Philosophyを再確認
```

## 7. 推奨ディレクトリ構成

```text
design-system/
├── DESIGN.md
├── README.md
├── CHANGELOG.md
│
├── philosophy/
│   ├── design-philosophy.md
│   ├── ux-philosophy.md
│   └── design-principles.md
│
├── decisions/
│   ├── README.md
│   └── DD-xxx-decision-title.md
│
├── foundations/
│   ├── token-architecture.md
│   ├── naming-convention.md
│   ├── color.md
│   ├── typography.md
│   ├── spacing.md
│   ├── sizing.md
│   ├── radius.md
│   ├── elevation.md
│   ├── motion.md
│   └── breakpoint.md
│
├── patterns/
│   ├── README.md
│   └── pattern-name.md
│
├── components/
│   ├── README.md
│   └── component-name.md
│
├── implementation/
│   ├── figma.md
│   ├── code.md
│   ├── accessibility.md
│   └── design-code-sync.md
│
└── contribution/
    ├── contribution-guide.md
    ├── review-checklist.md
    └── release-process.md
```

この構成は推奨例です。組織規模、プロダクト数、リポジトリ構成、ドキュメント管理ツールに応じて調整します。

## 8. 更新ルール

### 8.1 更新単位

Design Systemの変更は、可能な限り以下を1つの変更単位として扱います。

- Decision
- Documentation
- Figma
- Code
- Migration
- Release Note

### 8.2 Status管理

Design Decisionや新規ComponentにはStatusを付与します。

推奨例：

- Draft
- Proposed
- In Review
- Accepted
- Implemented
- Deprecated
- Superseded

### 8.3 Breaking Change

以下の場合はBreaking Changeとして扱います。

- Token名の変更・削除
- Component APIの変更
- VariantやPropertyの削除
- Visual Behaviorの大幅変更
- Accessibility Behaviorの変更
- Theme構造の変更
- 利用側でMigrationが必要な変更

Breaking Changeには、Migration Guideと影響範囲を明記します。

### 8.4 Changelog

主要な変更は`CHANGELOG.md`へ記録します。

最低限、以下を含めます。

- 変更日
- 変更内容
- 対象
- Breaking Changeの有無
- Migrationの必要性
- 関連Decision
- Figma / CodeのRelease Version

## 9. Design Review Checklist

### Philosophy / UX

- プロダクトの目的と整合しているか
- 提供したいUXを支援しているか
- ユーザーの判断や行動を妨げていないか

### Consistency

- 同じ意味に同じUIを使用しているか
- 既存ComponentやPatternを再利用しているか
- 不要な新規Componentを追加していないか

### Accessibility

- 色だけで情報を伝えていないか
- コントラストを確保しているか
- キーボード操作を考慮しているか
- Focus Stateが定義されているか
- Screen Readerで理解できるか

### Scalability

- Product固有の例外を増やしていないか
- 将来のThemeや機能追加に対応できるか
- 命名規則が一貫しているか
- Tokenの責務が適切か

### Engineering Alignment

- 実装可能な構造か
- FigmaとCodeのAPIが大きく乖離していないか
- ハードコードされた値を追加していないか
- Design Tokenを正しく参照しているか

### Documentation

- 判断理由が記録されているか
- 関連文書が更新されているか
- FigmaとCodeが同期しているか
- 未定義事項を独自ルールとして扱っていないか

## 10. 運用開始時の優先順位

Design Systemを初めて構築する場合は、すべてを同時に完成させる必要はありません。

推奨する優先順位は以下です。

1. `DESIGN.md`
2. `design-philosophy.md`
3. `ux-philosophy.md`
4. `design-principles.md`
5. Design Decisionのテンプレート
6. UI / Component / Token Audit
7. `token-architecture.md`
8. `naming-convention.md`
9. 主要Component
10. 主要Pattern
11. FigmaとCodeの同期方法
12. Contribution・Release・Migrationフロー

最初から完全なDesign Systemを目指すのではなく、影響度と利用頻度の高い領域から段階的に整備します。

## 11. Example

たとえば、Dark ModeでAlertの背景色が不統一になっている場合は、次のように進めます。

```text
問題を発見
    ↓
Design PrinciplesのConsistencyとAccessibilityを確認
    ↓
既存Semantic Tokenで解決可能か確認
    ↓
既存Alert ComponentのVariantで対応可能か確認
    ↓
Alpha合成・Palette追加・Component Token追加を比較
    ↓
Design Decisionを作成
    ↓
Token Architectureへ反映
    ↓
Alert Guidelineへ反映
    ↓
Figma VariablesとComponentを更新
    ↓
Code TokenとComponentを更新
    ↓
Contrastと各Stateを検証
```

この例の重要点は、Figma上で色を直接追加することから始めないことです。

設計判断、Token、Component、Figma、Codeを一つのワークフローとして接続します。

## 12. Summary

Design Systemは、以下の循環によって継続的に成長します。

```text
思想
    ↓
体験
    ↓
原則
    ↓
判断
    ↓
Pattern
    ↓
Component
    ↓
Token
    ↓
Figma / Code
    ↓
検証
    ↓
学習
    ↓
思想・原則・判断へ還元
```

Product Designerの役割は、UIを統一することだけではありません。

プロダクトの目的から実装までを接続し、なぜその設計が適切なのかを判断可能な形で残し、チームが同じ基準で設計・実装・改善できる状態を作ることです。
