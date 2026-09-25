---
format: human-skill/v1
id: create-human-skill
title: Create a Human Skill
language: en
license: CC-BY-4.0
author: kokuren333
---

# Create a Human Skill

## こんなとき

Use this when a user wants to turn a goal, practice, workflow, technique, set of notes, or rough idea into a reusable Human Skill that can be imported into Human Skills.

## どうする

1. Identify the smallest reusable capability being requested.
2. Determine the trigger: describe when someone should use this Skill and when they should not.
3. Identify prerequisites, inputs, tools, or context required before starting.
4. Convert the knowledge into an ordered procedure rather than a general explanation.
5. Make decision points explicit. Replace vague phrases with observable conditions whenever possible.
6. Add checks that tell the user whether each important step worked.
7. Include likely failure modes and recovery steps when they materially affect success.
8. Keep the Skill focused. If it contains multiple independently reusable procedures, split them into separate Skills.
9. Choose a stable, descriptive `id` and a clear human-facing `title`.
10. Write the generated Skill in the language requested by the user. If no language is requested, infer it from the task or source material.
11. Produce an importable `SKILL.md` using `format: human-skill/v1` with the required headings `## こんなとき` and `## どうする`.
12. Perform a final pass for actionability, unnecessary repetition, hidden assumptions, and format validity.

## 補足

A good Human Skill should let another person act without needing to reconstruct the author's reasoning from scratch. Prefer compact operational knowledge over background exposition.
