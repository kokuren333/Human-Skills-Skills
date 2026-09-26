# Human-Skills-Skills — Agent instructions

This repository contains meta-skills for creating, editing, reviewing, and source-grounding Human Skills.

The generated Human Skills are primarily for **people to read, search, and reuse on Human Skills**. Do not optimize them as hidden agent workflows. Agents act as editors and compilers of practical human knowledge.

## Target Human Skills format

Use `format: human-skill/v1`.

For a newly generated external Skill, the canonical server-managed fields may be omitted:

- `id` — omit for a new externally generated Skill. Human Skills assigns the stable ID at import time.
- `author` — omit for a new externally generated Skill. Human Skills attributes it to the importing Human at import time.

When editing an existing exported Skill, preserve an existing valid `id` and `author` unless the user is intentionally creating a distinct Skill.

Always include:

- `format: human-skill/v1`
- `title`
- `language`
- `license: CC-BY-4.0`

The body must contain:

- `# <title>`
- `## こんなとき`
- `## どうする`

`## 補足` and useful third-level headings may be added when they improve reading.

Current implementation limits include:

- `title`: 1–100 characters after trimming
- `language`: 2–20 characters
- `license`: exactly `CC-BY-4.0`
- `SKILL.md`: at most 32 KB
- folder hierarchy: at most 6 levels under `human-skills/`
- path length: at most 240 characters
- each path segment: at most 80 Unicode code points
- no raw HTML

Do not invent a Human Skills author ID or a canonical Skill ID for a new draft.

## Human-first writing

A Human Skill should make sense when opened directly on Human Skills without repository context.

Prefer:

- a title that names the actual problem or capability in ordinary language;
- a short `こんなとき` section that helps readers recognize their situation;
- a `どうする` section that can be scanned quickly;
- concrete judgment criteria, examples, mistakes, and recovery advice;
- terminology that a likely reader would naturally search for;
- one coherent reusable capability per Skill.

Avoid:

- router Skills whose main purpose is to dispatch to other Skills;
- agent orchestration language such as "invoke", "route", "pipeline", or "tool call" unless the Skill is genuinely about those concepts;
- numbered folders that imply hidden execution order;
- generic titles such as "Workflow" or "Process";
- keyword stuffing;
- long background essays before the useful guidance begins.

## Markdown and line breaks

Human Skills is read as rendered Markdown, so whitespace is part of usability.

Use these rules:

1. Put exactly one blank line after YAML frontmatter before the first heading.
2. Put one blank line after every heading before paragraph text or a list.
3. Separate distinct paragraphs with one blank line.
4. Put one blank line before and after a list when the surrounding content is prose.
5. Do not hard-wrap ordinary prose every sentence or every 40–80 characters. Let a paragraph remain a paragraph.
6. Do not put every sentence on its own line unless each line is intentionally a separate list item or step.
7. Keep list items compact. If one item becomes a mini-essay, split it into a short item plus a following paragraph or subheading.
8. Use `###` subheadings when the `どうする` section contains clearly different concerns such as steps, judgment criteria, common mistakes, or examples.
9. Avoid multiple consecutive blank lines.
10. Before finalizing, inspect the raw Markdown specifically for cramped text, accidental line breaks, and visually unbalanced sections.

A readable shape is usually:

```markdown
# タイトル

## こんなとき

短い導入段落。

必要ならもう一段落。

## どうする

### 基本

説明。

1. 手順。
2. 手順。

### よくある失敗

- 失敗例。
- 失敗例。
```

## Searchability

Human Skills search uses the title, `こんなとき`, `どうする`, `補足`, and path.

Make Skills discoverable by naturally including likely search words and synonyms in meaningful sentences. Do not append artificial keyword lists.

Folder paths should describe broad human-facing categories. They should not encode execution sequence.

## Creating from sources

Sources may include user files, notes, webpages, papers, manuals, transcripts, examples, or web research.

Do not summarize sources for their own sake. Extract reusable know-how:

- procedures;
- heuristics;
- decision criteria;
- prerequisites;
- exceptions;
- common mistakes;
- failure and recovery patterns;
- practical examples.

Reconcile disagreements when possible. When guidance depends on context, preserve that condition rather than forcing one universal rule.

Rewrite in original language suitable for a standalone Human Skill. Do not reproduce long source passages.

## Editing existing Skills

When editing an existing Skill:

- read the whole Skill before rewriting it;
- preserve an existing valid `id` and `author` unless identity truly changes;
- preserve the core purpose unless the user requests a scope change;
- improve the human reading experience before adding more structure;
- remove duplicate or repository-specific wording;
- split only when the resulting Skills would each be independently useful and searchable;
- return the complete final `SKILL.md` when a usable artifact is requested.

## Final validation

Before packaging or returning a Human Skill:

- verify the frontmatter rules;
- confirm new external drafts do not fabricate `id` or `author`;
- confirm existing canonical metadata is preserved when appropriate;
- confirm `## こんなとき` and `## どうする` exist;
- confirm the Markdown is visually readable, especially blank lines and paragraph boundaries;
- confirm the Skill is useful to a human without hidden agent context;
- confirm the content is concise enough to scan and concrete enough to act on.

Do not claim a Skill is importable unless it has been checked against the current Human Skills format.
