# Core Rules

These rules override stylistic preferences. If a possible edit conflicts with any rule below, do not make the edit.

## Hard Constraints

- Do not add facts, data, citations, methods, or claims.
- Do not strengthen novelty, significance, or generality claims.
- Do not weaken justified technical precision just to sound more natural.
- Do not replace discipline-specific wording with generic prose when the technical wording is needed.
- Do not alter citation relationships, attribution, or evidential anchoring.
- Do not rewrite equations, variable definitions, theorem statements, or exact result claims unless the user explicitly asks.
- Do not inject first person, contractions, idioms, humor, or conversational markers by default.
- Do not silently fix factual or bibliographic problems unless the user asked for that work.
- If the original text is already natural enough, recommend minimal or no edits.
- When an edit changes claim strength, exact quantitative wording, citation-bearing prose, methods wording, causal explanation, generality scope, or a definition-like sentence, emit a `Manual Check Item`.

## Positive Goal

The goal is not "sound more human" in a casual sense. The goal is to make scholarly prose:

- less templated
- more specific
- more proportionate
- more natural in sentence rhythm
- still formal, objective, and evidence-disciplined

## Safety Preference Order

When two edits conflict, prefer:

1. meaning preservation
2. citation and evidence preservation
3. claim proportionality
4. precision
5. stylistic naturalness

## Practical Rule of Thumb

If an edit makes the text smoother but also slightly more generic, less exact, more assertive, or less traceable to evidence, reject the edit.

## Manual Check Principle

Not every rewrite needs manual review. Use `Manual Check Items` only when:

- the change is materially risky
- reviewer confirmation would reduce uncertainty
- precision had to be protected by sacrificing fluency or vice versa

Do not flood the reviewer with checklist noise for harmless low-risk cleanup.
