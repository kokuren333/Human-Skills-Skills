# Agent instructions

This repository contains meta-skills for authoring Human Skills.

## Core goal

Produce Human Skills that are directly importable into Human Skills and useful as reusable procedural knowledge.

## Output location

When adding a new authoring skill to this repository, use:

`human-skills/<category>/<skill-name>/SKILL.md`

When generating a user-facing Human Skill, preserve a directory structure that can be placed under `human-skills/` and zipped for import.

## Required Human Skill format

Each `SKILL.md` must contain YAML frontmatter with at least:

- `format`
- `id`
- `title`
- `language`
- `license`
- `author`

Use:

`format: human-skill/v1`

The body must contain:

- `# <title>`
- `## こんなとき`
- `## どうする`

Additional sections such as `## 補足` are allowed when useful.

Do not make repository-specific helper files mandatory for the generated Skill.

## Language

These meta-skills are written in English for agents.

Generated Human Skills should be written in the language requested by the user. If unspecified, infer the most appropriate language from the task or source material.

Do not translate the required Human Skills section headings unless the platform format changes.

## Authoring principles

A Human Skill is not merely a summary of information. It should encode reusable operational knowledge.

Prefer:

- trigger conditions;
- prerequisites;
- ordered actions;
- concrete decision rules;
- checkpoints;
- failure modes;
- recovery steps;
- stopping conditions;
- scope limits.

Avoid relying on vague instructions such as "appropriately", "carefully", or "as needed" without explaining what observable condition should guide the decision.

## Using sources

Agents may use user-provided files, repository material, documentation, web search, papers, articles, manuals, transcripts, or other relevant sources.

When using sources:

1. identify the practical knowledge relevant to the target Skill;
2. extract procedures, heuristics, conditions, checks, and failure patterns;
3. reconcile disagreements when possible;
4. preserve conditionality when sources disagree or apply only in certain contexts;
5. rewrite the result as an independent procedural Skill;
6. avoid copying source prose or reproducing long source-specific examples;
7. do not invent certainty that the sources do not provide.

Strict citation is optional unless requested by the user. The Skill should remain useful even if the source list is removed.

## Editing existing Skills

Preserve the original intent unless the user asks for a change in scope.

When revising:

- keep stable IDs stable unless identity truly changes;
- preserve import compatibility;
- remove redundancy;
- make implicit assumptions explicit;
- convert descriptive prose into actionable steps where possible;
- split a Skill when it contains multiple independently reusable procedures.

## Review checklist

Before finalizing a Skill, check:

- Is the trigger situation clear?
- Can a person or agent execute the steps in order?
- Are prerequisites explicit?
- Are decision points concrete?
- Are failure and recovery paths covered where relevant?
- Is the scope narrow enough to remain reusable?
- Is source-specific baggage removed?
- Is the wording concise enough to scan?
- Is the output valid `human-skill/v1`?
- Can it be imported without repository-specific tooling?
