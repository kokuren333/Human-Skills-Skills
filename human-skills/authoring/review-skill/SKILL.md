---
format: human-skill/v1
id: review-human-skill
title: Review a Human Skill
language: en
license: CC-BY-4.0
author: kokuren333
---

# Review a Human Skill

## こんなとき

Use this when a Human Skill needs to be audited before publishing, importing, sharing, or revising.

## どうする

1. Check format validity:
   - valid YAML frontmatter;
   - `format: human-skill/v1`;
   - stable `id`;
   - clear `title`;
   - appropriate `language`, `license`, and `author`;
   - required `## こんなとき` and `## どうする` sections.
2. Check the trigger. A reader should understand when the Skill applies and when it does not.
3. Check prerequisites. Required inputs, tools, permissions, knowledge, or context should not be hidden.
4. Check actionability. The procedure should describe actions in a usable order rather than merely explain the topic.
5. Check decision points. Replace vague judgment calls with concrete conditions where possible.
6. Check verification. Important steps should have observable success criteria when practical.
7. Check failures. Include common failure modes and recovery paths when they materially affect successful execution.
8. Check scope. The Skill should represent one coherent reusable capability rather than an entire field of knowledge.
9. Check portability. Remove unnecessary source-specific wording, anecdotes, branding, or assumptions that prevent reuse.
10. Check concision. Delete repetition and background detail that does not improve execution or judgment.
11. Check epistemic limits. Do not present conditional or uncertain guidance as universally true.
12. Return concrete revision recommendations, and when asked to revise the Skill, output the complete corrected `SKILL.md`.

## 補足

A strong review focuses on whether the Skill transfers reliable know-how. Grammar and style matter, but they are secondary to trigger clarity, executable steps, decision quality, and recovery from failure.
