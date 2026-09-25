# Human-Skills-Skills

Agent-oriented authoring skills for creating, editing, reviewing, and source-grounding Human Skills.

This repository is intended for coding agents and general-purpose AI agents that need to produce Human Skills in a form that can be imported into Human Skills.

Human Skills  
https://human-skills.kokuren.workers.dev/

## Included authoring skills

- `create-skill` — create a new Human Skill from a user goal, notes, or rough requirements.
- `create-skill-from-sources` — research files and/or the web, extract practical know-how, and compile it into a reusable Human Skill.
- `edit-skill` — revise an existing Human Skill while preserving its intent and import compatibility.
- `review-skill` — audit a Human Skill for actionability, clarity, scope, reuse, and format compliance.

## Repository layout

```text
Human-Skills-Skills/
├── README.md
├── AGENTS.md
└── human-skills/
    ├── manifest.json
    └── authoring/
        ├── create-skill/
        │   └── SKILL.md
        ├── create-skill-from-sources/
        │   └── SKILL.md
        ├── edit-skill/
        │   └── SKILL.md
        └── review-skill/
            └── SKILL.md
```

## Human Skills compatibility

The important artifact is each `SKILL.md`. Human Skills imports skills by discovering `SKILL.md` files in the archive. `manifest.json` is included because exported Human Skills archives contain one, but authoring agents should not depend on it being required for import.

A generated Human Skill should use `format: human-skill/v1` and contain, at minimum:

```markdown
---
format: human-skill/v1
id: stable-id
title: Example title
language: en
license: CC-BY-4.0
author: author-name
---

# Example title

## こんなとき
...

## どうする
...
```

The required section headings are kept exactly as expected by the current Human Skills format, even when the generated skill body is written in another language.

## Language policy

The authoring skills in this repository are written in English because they are instructions for agents.

The generated Human Skill itself should use the language requested by the user. If no language is requested, infer the most appropriate language from the task and source material.

## Source use

When creating a Human Skill from source material:

- use files, webpages, manuals, papers, notes, transcripts, or other relevant material as input;
- extract reusable procedures, heuristics, decision rules, checks, failure modes, and practical know-how;
- do not copy large passages or turn the Skill into a source summary;
- strict academic citation is not required unless the user explicitly asks for it;
- preserve uncertainty and scope limits when the sources do not support a universal rule.

The target output is operational know-how, not a literature review.
