---
format: human-skill/v1
id: create-human-skill-from-sources
title: Create a Human Skill from Sources
language: en
license: CC-BY-4.0
author: kokuren333
---

# Create a Human Skill from Sources

## こんなとき

Use this when a Human Skill should be built from existing material such as user-provided files, webpages, documentation, manuals, papers, books, notes, transcripts, examples, or web research.

## どうする

1. Define the practical capability the resulting Skill should teach. Do not begin by summarizing every source.
2. Gather only sources relevant to that capability. Use user-provided material first when it is authoritative for the task, and use web research when current or missing information would improve the Skill.
3. Extract operational knowledge from the sources:
   - procedures;
   - heuristics;
   - prerequisites;
   - decision rules;
   - success checks;
   - common mistakes;
   - failure modes;
   - recovery actions;
   - scope limits.
4. Separate durable know-how from source-specific wording, anecdotes, branding, and presentation style.
5. Compare overlapping sources. When they agree, consolidate the common rule. When they disagree, identify the condition under which each recommendation applies, or preserve the uncertainty.
6. Do not copy long passages. Rewrite the extracted knowledge as an independent Skill.
7. Do not turn the output into a literature review or bibliography. Strict citation is not required unless the user explicitly asks for it.
8. Convert descriptive material into executable instructions. Prefer "If X is observed, do Y" over "Y is often considered useful."
9. Remove details that do not affect action, judgment, or verification.
10. Preserve important safety limits, exceptions, and uncertainty instead of overstating the evidence.
11. Write the resulting Human Skill in the language requested by the user, or infer the most appropriate language when unspecified.
12. Output a valid `human-skill/v1` `SKILL.md` with `## こんなとき` and `## どうする`.
13. Review the final Skill as if the sources were no longer available. It should still stand on its own as reusable operational knowledge.

## 補足

Think of this process as compiling sources into a procedure, not compressing sources into a summary.

For example, several sources such as:

- "Usually do X first."
- "Under condition Y, prefer Z."
- "W is a common failure mode."

should become something like:

1. Start with X.
2. If Y is present, use Z instead.
3. Check for W; if it occurs, perform the recovery step.
