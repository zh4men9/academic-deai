# Workflow

## 1. Triage

Identify all four before editing:

- genre: manuscript, cover letter, rebuttal, or review response
- section: abstract, introduction, related work, methods, results, discussion, conclusion, or other
- risk level: low, medium, or high
- sensitivity: ordinary or citation-sensitive

## 2. Risk Classification

Use these defaults.

### Low-risk text

- abstract wording
- introduction framing
- conclusion inflation
- cover-letter stiffness

### Medium-risk text

- related work synthesis
- citation-heavy synthesis
- attribution-bearing contrast sentences
- discussion claims
- reviewer-response tone

### High-risk text

- methods
- experimental setup
- exact numerical result interpretation
- theorem-like language
- statistical wording

## 3. Edit Decision

Choose one edit level explicitly.

### No-op

- Use when the text is already specific, proportionate, and non-templated.
- Prefer this over unnecessary smoothing.

### Micro-edit only

- Use for high-risk text by default.
- Use for citation-sensitive text by default.
- Limit changes to removing empty transitions, repeated novelty framing, inflated adverbs, unnecessary repetition, or overbroad scope language.
- Do not materially restructure the sentence unless the gain clearly outweighs the risk.

### Full safe rewrite

- Use only for low-risk text.
- Medium-risk text may use it only when attribution, evidence linkage, and claim calibration remain clearly intact.

## 4. Manual Check Items

Generate a separate `Manual Check Items` block when any of these triggers is hit:

- claim strength changed or softened in a way that affects interpretation
- wording around exact quantitative results changed
- attribution-bearing or citation-bearing sentence rewritten
- methods, procedure, or assumptions sentence rewritten
- causal explanation rewritten
- generality scope narrowed or broadened
- definition-like sentence rewritten into a more descriptive sentence
- any edit where preserving precision required trading off fluency

Use this fixed field structure for each checklist item:

- location or sentence reference
- original fragment
- revised fragment
- risk type
- why it needs review
- suggested reviewer question

## 5. Output Assembly

Use these output blocks consistently:

- `Diagnosis`
- `Priority Fixes` when in diagnostic mode
- `Revised Text` when rewriting
- `Risk Check`
- `Manual Check Items` when a trigger fires
- `Verdict` in final audit mode

## 6. Post-Edit Audit

After any rewrite, check:

- meaning preservation
- claim strength preservation or justified softening
- citation anchoring
- tone consistency
- whether the edit introduced generic prose that is less scholarly than the original
- whether checklist coverage is useful rather than noisy

## 7. Whole-Document Rule

Never rewrite a full manuscript as one undifferentiated pass. Process it section by section.

Preferred order:

1. abstract
2. introduction
3. related work
4. discussion
5. conclusion
6. methods or results only if explicitly requested

## 8. Escalation Rule

If the text has serious factual, citation, or logic issues, do not hide them under stylistic editing. Flag them separately and keep the de-AI edits minimal.
