# トークンアーキテクチャ / Token Architecture

**ステータス / Status:** `Draft`

トークンは具体的な値を名前で隠すだけの仕組みではなく、設計意図を再利用可能な契約にします。

Tokens are not merely names that hide values; they make design intent into reusable contracts.

`Primitive → Semantic → Component` の三層を採用します。Primitive は色相やサイズなどの基礎値、Semantic は surface や text のような役割、Component は button や input の部品固有の役割を表します。下位レイヤーは上位の意味を重複させず、必要な場合にのみ参照します。

Use three layers: `Primitive → Semantic → Component`. Primitives are basic values such as hue and size; semantics describe roles such as surface or text; component tokens describe roles specific to a component such as button or input. A lower layer does not duplicate higher-level meaning and references it only when needed.

値、テーマ、同期元、破壊的変更の扱いは承認前のため `TBD` です。

Values, themes, sources of synchronization, and breaking-change policy are `TBD` pending approval.
