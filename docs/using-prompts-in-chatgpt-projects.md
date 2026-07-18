# ChatGPT Projects で Prompt を使う / Using Prompts in ChatGPT Projects

**ステータス / Status:** `Draft`

## 目的 / Purpose

ChatGPT Project の参照資料として Prompt Library のファイルを使い、限定されたタスクを一貫して実行するためのガイドです。これは再利用可能な Prompt ではないため、Prompt Catalog には掲載しません。

This guide explains how to use a Prompt Library file as ChatGPT Project knowledge for a consistent, bounded task. It is documentation rather than a reusable prompt and is therefore not listed in the Prompt Catalog.

## 手順 / Steps

1. 必要な Prompt ファイル（例: `prompts/writing/generate-markdown.md`）を Project に追加します。 / Add the required prompt file, for example `prompts/writing/generate-markdown.md`, to the Project.
2. 会話で、そのファイルを読み、定義に従うよう明示します。 / In the conversation, explicitly ask ChatGPT to read and follow that file.
3. Prompt が求める入力を、名前付きで完全に渡します。 / Supply every required input by name.
4. 出力ファイル、言語、制約、確認方法を明記します。 / State the output file, language, constraints, and validation expectations.
5. 出力を Prompt の quality checklist と原資料に照らして確認します。 / Validate the output against the prompt’s quality checklist and the source material.

## 例 / Example

`generate-markdown.md` を使用する場合は、document purpose、audience、source content、language、output filename を指定し、実際にダウンロード可能な Markdown ファイルを生成するよう依頼します。入力にない事実を補完しないよう求めてください。

When using `generate-markdown.md`, provide document purpose, audience, source content, language, and output filename, then request a downloadable Markdown file. Ask the tool not to invent facts absent from the inputs.

## 注意 / Notes

Prompt は一つの主要タスク用です。複数段階の作業、テンプレート、参照資料、連携した検証が恒常的に必要になった場合は、Skill への昇格を検討します。

A prompt is for one primary task. When a repeatable outcome consistently needs multiple steps, templates, references, and coordinated validation, consider promoting it to a Skill.
