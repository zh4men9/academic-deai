---
name: academic-deai
description: Use when the user wants to reduce AI-like phrasing in English academic writing without changing technical meaning, citation intent, evidential strength, or scholarly tone. Trigger for requests such as de-AI this abstract, make this introduction sound less LLM-written, polish this manuscript paragraph without changing content, or rewrite this cover letter or response letter so it sounds natural and professional. For risky edits, pair the revision with a separate Manual Check Items block for human review.
metadata:
  short-description: Conservative de-AI editing for academic prose
---

# Academic De-AI

## Overview

Use this skill for academic-safe de-AI editing of English scholarly prose. The goal is to reduce templated, inflated, or overly generic LLM-like writing while preserving meaning, evidence, citations, and discipline-appropriate formality.

Default to diagnosis first and conservative rewriting second. When the text is already acceptable, prefer minimal edits or no edits over unnecessary smoothing. If an edit touches a high-risk area, keep the rewrite restrained and surface the risky change in a separate `Manual Check Items` block.

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

1. Identify the genre, section, and whether the text is citation-sensitive.
2. Diagnose AI-like signals before rewriting.
3. Choose one edit level: `No-op`, `Micro-edit only`, or `Full safe rewrite`.
4. Produce revised text only when needed, plus a separate risk review channel when a trigger fires.
5. Run a post-edit academic risk audit.

For full manuscripts, process section by section rather than rewriting the document in one pass. Start with the abstract, introduction, discussion, and conclusion unless the user explicitly wants methods or results rewritten.

## Edit Levels

Use one of these edit levels explicitly:

- `No-op`
  - Use when the prose is already specific, proportionate, and non-templated.
  - Output may recommend no substantive rewrite.

- `Micro-edit only`
  - Use when the safest action is to remove empty transitions, repeated novelty framing, inflated adverbs, or minor scaffolding without changing sentence structure materially.
  - This is the default for high-risk and citation-sensitive text unless a fuller rewrite is clearly safe.

- `Full safe rewrite`
  - Use only for low-risk academic prose.
  - Sentence reorganization is allowed, but meaning, evidence, and claim calibration must remain intact.

## Mode Selection

Use one of these modes explicitly:

- `Diagnostic mode`
  - Use when the user asks whether the text sounds AI-written or asks for issues first.
  - Output: `Diagnosis`, `Priority Fixes`, and `Manual Check Items` when the text is high-risk, citation-sensitive, or unresolved risk remains.

- `Conservative rewrite mode`
  - Use when the user explicitly asks for rewritten prose.
  - Output: `Diagnosis`, `Revised Text`, `Risk Check`, and `Manual Check Items` when any trigger fires.

- `Final audit mode`
  - Use when the user provides revised text or asks for a final check.
  - Output: `Verdict`, `Diagnosis`, `Risk Check`, and `Manual Check Items` if unresolved risk remains.

Default routing:
- "Does this sound AI-written?" -> `Diagnostic mode`
- "Rewrite this to sound less AI-written." -> `Conservative rewrite mode`
- "Check whether this revised version is now safe." -> `Final audit mode`

## Output Blocks

Use these block names consistently:

- `Diagnosis`
- `Priority Fixes`
- `Revised Text`
- `Risk Check`
- `Manual Check Items`
- `Verdict`

`Manual Check Items` must always be a separate block. Do not bury high-risk review notes inside the prose explanation.

## Risk Rules

- High-risk sections such as methods, experimental setup, exact result interpretation, and theorem-like language should remain diagnosis-first and default to `Micro-edit only`.
- Citation-heavy related work, multi-citation comparisons, and attribution-bearing contrast sentences are citation-sensitive even when they are not otherwise high-risk.
- Never strengthen claims, invent evidence, or alter citation relationships.
- Never trade precision for fluency.
- If the text is already natural enough, recommend no further change.
- Any substantive change in a high-risk or citation-sensitive sentence must appear in `Manual Check Items`.

## Reference Routing

Read only what is needed:

- `references/core-rules.md` for non-negotiable safety constraints
- `references/workflow.md` for triage, risk, and full-document process
- `references/section-guidance.md` for section-specific editing policy
- `references/diagnostic-checklist.md` for identifying AI-like signals
- `references/rewrite-patterns.md` for safe rewrite patterns
- `references/manual-check-items.md` for checklist triggers and field structure
- `references/non-goals.md` when deciding what this skill must refuse or avoid
- `references/validation-rubric.md` for final audit and acceptance checks
