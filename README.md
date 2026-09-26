# Human-Skills-Skills

Human Skillsを**作る・資料からまとめる・直す・公開前に点検する**ためのメタSkill集です。

AIやCoding Agentから利用できますが、生成されるHuman SkillはAgent内部のworkflowではなく、**Human Skills上で人間が読みやすく、検索しやすく、再利用しやすい知識**になることを優先します。

## 含まれるSkill

- `authoring/create-skill` — Human Skillを新しく作る
- `authoring/create-skill-from-sources` — 資料やWebからHuman Skillを作る
- `authoring/edit-skill` — 既存のHuman Skillを読みやすく直す
- `authoring/review-skill` — 公開・import前にHuman Skillを点検する

## ChatGPTで使う

ChatGPTにこのリポジトリやZIPを渡す場合は、`instruction_for_ChatGPT.md` を参照させてください。

特に次を明示しています。

- 新規の外部生成Skillでは `id` と `author` を捏造しない
- Human Skills上で人が読むことを優先する
- routerやAgent orchestration中心のSkillにしない
- 検索されやすい自然なタイトルと本文にする
- Markdownの段落、空行、箇条書き周辺の改行を丁寧に整える

## Coding Agentで使う

`AGENTS.md` を参照してください。

Human Skillsのportable format、編集時のmetadata保持、検索性、Markdown可読性、資料からの知識抽出方針をまとめています。

## 新規Skillのmetadata

Human Skills本体がserver-assigned ID / authorに対応した前提では、外部で新しく生成するSkillは次のようにできます。

```yaml
---
format: human-skill/v1
title: Human Skillを作る
language: ja
license: CC-BY-4.0
---
```

`id` と `author` はimport時にHuman Skills側で確定します。

既存のexport済みSkillを編集する場合は、そのSkillの有効な `id` と `author` を保持してください。
