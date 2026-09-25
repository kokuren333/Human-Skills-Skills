---
format: human-skill/v1
id: edit-human-skill
title: Edit a Human Skill
language: en
license: CC-BY-4.0
author: kokuren333
---

# Edit a Human Skill

## こんなとき

Use this when an existing Human Skill needs to be corrected, clarified, shortened, expanded, reorganized, localized, or updated without losing its core purpose or import compatibility.

## どうする

1. Read the existing Skill completely before editing it.
2. Identify its current purpose, trigger conditions, intended user, and reusable capability.
3. Preserve the existing `id` unless the Skill's identity or scope changes enough to justify a new Skill.
4. Preserve valid Human Skills frontmatter and the required headings.
5. Apply the requested change while keeping unrelated behavior stable.
6. Replace vague or descriptive passages with concrete actions and decision rules where possible.
7. Make hidden prerequisites and assumptions explicit.
8. Remove duplicate steps, filler, source-specific baggage, and explanations that do not affect execution.
9. Add checks, failure handling, or stopping conditions when their absence makes the procedure unreliable.
10. If the Skill now contains multiple independently reusable procedures, split them rather than expanding one Skill indefinitely.
11. Preserve the target language unless the user requests a language change.
12. Validate the final result as a complete importable `human-skill/v1` Skill, not as a patch or diff.

## 補足

When editing, optimize for behavioral clarity rather than stylistic polish alone. The question is not only whether the text reads better, but whether someone can perform the Skill more reliably after the edit.
