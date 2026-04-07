---
name: academic-deai
description: Use when the user wants to reduce AI-like phrasing in English academic writing without changing technical meaning, citation intent, evidential strength, or scholarly tone. Trigger for requests such as de-AI this abstract, make this introduction sound less LLM-written, polish this manuscript paragraph without changing content, or rewrite this cover letter or response letter so it sounds natural and professional.
metadata:
  short-description: Conservative de-AI editing for academic prose
---

# Academic De-AI

## Overview

Use this skill for academic-safe de-AI editing of English scholarly prose. The goal is to reduce templated, inflated, or overly generic LLM-like writing while preserving meaning, evidence, citations, and discipline-appropriate formality.

Default to diagnosis first and conservative rewriting second. When the text is already acceptable, prefer minimal edits or no edits over unnecessary smoothing.

## When to Use

Use this skill for:
- abstracts
- introductions
- related work sections
- discussions and conclusions
- cover letters for journal or conference submission
- rebuttal letters and reviewer response letters
- paragraph-level academic polishing requests that explicitly ask for less AI-like wording

Typical triggers:
- "De-AI this abstract."
- "Make this introduction sound less LLM-written."
- "Polish this paragraph without changing technical meaning."
- "Rewrite this response letter so it sounds natural but still professional."

## When Not to Use

Do not use this skill as the main workflow for:
- equations, proofs, theorem statements, and variable definitions
- references and citation formatting
- raw quantitative result statements
- tables, figure captions, and labels unless the user explicitly asks
- blog-style humanization
- marketing or promotional tone changes
- creative writing
- requests for personality, warmth, humor, or chatty naturalness

If the request is closer to ordinary humanization than scholarly editing, say so and avoid forcing this workflow.

## Default Workflow

1. Identify the genre and section.
2. Diagnose AI-like signals before rewriting.
3. Choose the minimum safe edit level.
4. Rewrite conservatively only if needed.
5. Run a post-edit academic risk audit.

For full manuscripts, process section by section rather than rewriting the document in one pass. Start with the abstract, introduction, discussion, and conclusion unless the user explicitly wants methods or results rewritten.

## Mode Selection

Use one of these modes explicitly:

- `Diagnostic mode`
  - Use when the user asks whether the text sounds AI-written or asks for issues first.
  - Output: short diagnosis, top issue categories, priority fixes, and an optional 1-3 sentence sample rewrite.

- `Conservative rewrite mode`
  - Use when the user explicitly asks for rewritten prose.
  - Output: one-sentence diagnosis, revised text, a short risk check, and a note on what was intentionally left unchanged when relevant.

- `Final audit mode`
  - Use when the user provides revised text or asks for a final check.
  - Output: pass/fail-style assessment, remaining AI-like issues, any academic-risk warning, and whether further edits are needed.

Default routing:
- "Does this sound AI-written?" -> `Diagnostic mode`
- "Rewrite this to sound less AI-written." -> `Conservative rewrite mode`
- "Check whether this revised version is now safe." -> `Final audit mode`

## Risk Rules

- High-risk sections such as methods, experimental setup, exact result interpretation, and theorem-like language should remain diagnosis-first and minimally rewritten.
- Never strengthen claims, invent evidence, or alter citation relationships.
- Never trade precision for fluency.
- If the text is already natural enough, recommend no further change.

## Reference Routing

Read only what is needed:

- `references/core-rules.md` for non-negotiable safety constraints
- `references/workflow.md` for triage, risk, and full-document process
- `references/section-guidance.md` for section-specific editing policy
- `references/diagnostic-checklist.md` for identifying AI-like signals
- `references/rewrite-patterns.md` for safe rewrite patterns
- `references/non-goals.md` when deciding what this skill must refuse or avoid
- `references/validation-rubric.md` for final audit and acceptance checks
