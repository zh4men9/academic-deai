---
name: academic-deai
description: Use when the user wants to reduce AI-like phrasing in English academic writing without changing technical meaning, citation intent, evidential strength, or scholarly tone. Trigger for requests such as de-AI this abstract, make this introduction sound less LLM-written, polish this manuscript paragraph without changing content, or rewrite this cover letter or response letter so it sounds natural and professional. Use balanced claim calibration by default, keep risky edits restrained, and report changed risks, skipped high-risk items, and unchanged suspicious residue transparently.
metadata:
  short-description: Balanced de-AI editing for academic prose
---

# Academic De-AI

## Overview

Use this skill for academic-safe de-AI editing of English scholarly prose. The goal is to reduce templated, inflated, or overly generic LLM-like writing while preserving meaning, evidence, citations, and discipline-appropriate formality.

Default to diagnosis first, balanced claim calibration, and transparent reporting. When the text is already acceptable, prefer minimal edits or no edits over unnecessary smoothing. When risk is real, either keep the rewrite restrained, surface it in `Manual Check Items`, or explicitly disclose that the text was left unchanged.

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
- raw quantitative result statements unless the user explicitly wants style cleanup only
- tables, figure captions, and labels unless the user explicitly asks
- blog-style humanization
- marketing or promotional tone changes
- creative writing
- requests for personality, warmth, humor, or chatty naturalness

If the request is closer to ordinary humanization than scholarly editing, say so and avoid forcing this workflow.

## Default Workflow

1. Identify the genre, section, risk level, and whether the text is citation-sensitive or symbol-bearing.
2. Diagnose AI-like signals before rewriting.
3. Apply `Detail Preservation Guard` before accepting any non-trivial rewrite.
4. Choose one edit level: `No-op`, `Micro-edit only`, or `Full safe rewrite`.
5. Produce revised text only when needed, then run `Residual Scan`.
6. Finish with transparent reporting of changed risks, skipped high-risk items, and unchanged suspicious residue.

For full manuscripts, process section by section rather than rewriting the document in one pass. Start with the abstract, introduction, related work, discussion, and conclusion unless the user explicitly wants methods or results rewritten.

## Claim Calibration

Use one explicit claim mode:

- `closer to source`
- `balanced`
- `conservative`

Default to `balanced`. Use `closer to source` only when the user explicitly wants stronger fidelity to the original emphasis. Use `conservative` only when the user explicitly prefers stronger softening of claims.

## Edit Levels

Use one of these edit levels explicitly:

- `No-op`
  - Use when the prose is already specific, proportionate, and non-templated.
  - Output may recommend no substantive rewrite.

- `Micro-edit only`
  - Use when the safest action is to remove empty transitions, repeated novelty framing, inflated adverbs, minor scaffolding, or surface residue without materially changing sentence structure.
  - This is the default for high-risk, citation-sensitive, and symbol-bearing text.

- `Full safe rewrite`
  - Use only for low-risk academic prose.
  - Sentence reorganization is allowed, but meaning, evidence, claim calibration, and concrete detail must remain intact.

## Mode Selection

Use one of these modes explicitly:

- `Diagnostic mode`
  - Use when the user asks whether the text sounds AI-written or asks for issues first.
  - Output: `Diagnosis`, `Priority Fixes`, and transparent reporting blocks as needed.

- `Conservative rewrite mode`
  - Use when the user explicitly asks for rewritten prose.
  - Output: `Diagnosis`, `Edit Level`, `Claim Mode`, `Revised Text`, `Risk Check`, and transparent reporting blocks as needed.

- `Final audit mode`
  - Use when the user provides revised text or asks for a final check.
  - Output: `Verdict`, `Diagnosis`, `Risk Check`, and transparent reporting blocks as needed.

Default routing:
- "Does this sound AI-written?" -> `Diagnostic mode`
- "Rewrite this to sound less AI-written." -> `Conservative rewrite mode`
- "Check whether this revised version is now safe." -> `Final audit mode`

## Output Blocks

Use these block names consistently:

- `Diagnosis`
- `Edit Level`
- `Claim Mode`
- `Priority Fixes`
- `Revised Text`
- `Risk Check`
- `Manual Check Items`
- `Skipped High-Risk Items`
- `Unchanged Suspicious Items`
- `Verdict`

`Manual Check Items`, `Skipped High-Risk Items`, and `Unchanged Suspicious Items` must remain separate blocks. Do not bury them inside explanatory prose.

## Risk Rules

- High-risk sections such as methods, experimental setup, exact result interpretation, theorem-like language, and symbol-bearing paragraphs should remain diagnosis-first and default to `Micro-edit only`.
- Citation-heavy related work, multi-citation comparisons, and attribution-bearing contrast sentences are citation-sensitive even when they are not otherwise high-risk.
- `Detail Preservation Guard` is mandatory before accepting compression of named algorithms, datasets, environments, enumerations, scoped qualifiers, or comparison bases.
- `Residual Scan` is mandatory after rewriting; it must surface unchanged low-risk residue and deterministic surface hygiene issues.
- Never strengthen claims, invent evidence, or alter citation relationships.
- Never trade precision for fluency.
- If the text is already natural enough, recommend no further change.
- If a high-risk improvement would require restructuring the technical skeleton, leave it unchanged and disclose it in `Skipped High-Risk Items`.

## Reference Routing

Read only what is needed:

- `references/core-rules.md` for non-negotiable safety constraints
- `references/workflow.md` for triage, guards, and full-document process
- `references/section-guidance.md` for section-specific editing policy
- `references/diagnostic-checklist.md` for identifying AI-like signals and residual surface issues
- `references/rewrite-patterns.md` for safe rewrite patterns
- `references/claim-calibration.md` for `closer to source` / `balanced` / `conservative`
- `references/manual-check-items.md` for checklist triggers and field structure
- `references/transparent-reporting.md` for changed / skipped / unchanged reporting
- `references/surface-hygiene.md` for deterministic non-semantic cleanup
- `references/non-goals.md` when deciding what this skill must refuse or avoid
- `references/validation-rubric.md` for final audit and acceptance checks
