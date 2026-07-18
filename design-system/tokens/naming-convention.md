# 命名規則 / Naming Convention

**ステータス / Status:** `Draft`

トークン名は `category.role.variant.state` のように、値ではなく役割を優先して表します。例: `color.text.primary`、`space.layout.section`、`component.button.background.default`。Primitive では `color.blue.500` のような体系的な値名を許容しますが、UI は可能な限り semantic または component token を参照します。

Token names express role before value, using a form such as `category.role.variant.state`: for example, `color.text.primary`, `space.layout.section`, or `component.button.background.default`. Primitives may use systematic value names such as `color.blue.500`, while UI should reference semantic or component tokens whenever possible.

名前、階層、廃止予定の変更は README と decision record に記録します。

Document naming, hierarchy, and deprecations in the README and a decision record.
