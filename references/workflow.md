# Workflow

## 1. Triage

Identify all five before editing:

- genre: manuscript, cover letter, rebuttal, or review response
- section: abstract, introduction, related work, methods, results, discussion, conclusion, or other
- risk level: low, medium, or high
- sensitivity: ordinary, citation-sensitive, or symbol-bearing
- claim mode: `closer to source`, `balanced`, or `conservative`

Default claim mode is `balanced`.

## 2. Diagnostic Pass

Use the diagnostic checklist before rewriting.

Look for:

- AI-like prose signals
- citation-sensitive comparison structure
- concrete detail that must not be lost
- deterministic surface residue such as broken sentence boundaries, missing spaces, figure-label spacing, or full-width numbering

## 3. Risk Classification

Use these defaults.

### Low-risk text

- abstract wording
- introduction framing
- conclusion inflation
- cover-letter stiffness
- general background prose without citation-sensitive comparisons

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
- symbol-bearing technical paragraphs

## 4. Detail Preservation Guard

Before accepting any non-trivial rewrite, check whether the revision drops or weakens:

- named algorithms
- datasets or environments
- enumerations
- scoped qualifiers
- comparison bases
- evidence-linked conditions

If concrete detail is lost, do one of the following:

- revert to `Micro-edit only`
- keep the original text
- surface the issue explicitly in `Risk Check`

Do not compress away concrete lists when the safer option is to compress around them.

## 5. Edit Decision

Choose one edit level explicitly.

### No-op

- Use when the text is already specific, proportionate, and non-templated.
- Prefer this over unnecessary smoothing.

### Micro-edit only

- Use for high-risk text by default.
- Use for citation-sensitive text by default.
- Use for symbol-bearing text by default.
- Limit changes to empty transitions, repeated novelty framing, inflated adverbs, reminder phrases, unnecessary repetition, overbroad scope language, and deterministic surface cleanup.
- Do not materially restructure the sentence.
- Do not alter inline math, variable-bearing spans, embedded objects, or definition skeletons.

### Full safe rewrite

- Use only for low-risk text.
- Medium-risk text may use it only when attribution, evidence linkage, and claim calibration remain clearly intact.

## 6. Manual Check Items

Generate a separate `Manual Check Items` block only when a changed sentence is materially risky.

Typical triggers:

- claim strength changed in a way that affects interpretation
- wording around an exact quantitative result changed
- attribution-bearing or citation-bearing sentence rewritten
- methods, procedure, or assumptions sentence rewritten
- causal explanation rewritten
- generality scope narrowed or broadened
- definition-like sentence rewritten into a more descriptive sentence
- an edit required a tradeoff between precision and fluency

Do not use `Manual Check Items` for skipped high-risk candidates or unchanged suspicious residue.

## 7. Transparent Reporting

After rewriting, separate three reporting surfaces:

- `Manual Check Items`: changed text that still needs review
- `Skipped High-Risk Items`: text left unchanged because safe rewriting would require violating the skill's risk limits
- `Unchanged Suspicious Items`: low-risk or surface-level residue that still looks suspicious after the pass

Do not collapse all residual uncertainty into `Manual Check Items`.

## 8. Residual Scan

After any rewrite pass, scan unchanged text for:

- residual low-risk AI-like prose
- broken sentence boundaries
- missing sentence or label spacing
- figure/table label formatting residue
- full-width numbering or other obvious surface-style mismatches

Surface these findings in `Unchanged Suspicious Items`.

## 9. Post-Edit Audit

After any rewrite, check:

- meaning preservation
- detail preservation
- claim calibration consistency
- citation anchoring
- tone consistency
- whether the edit introduced generic prose that is less scholarly than the original
- whether changed / skipped / unchanged reporting is transparent rather than optimistic

## 10. Whole-Document Rule

Never rewrite a full manuscript as one undifferentiated pass. Process it section by section.

Preferred order:

1. abstract
2. introduction
3. related work
4. discussion
5. conclusion
6. methods or results only if explicitly requested
7. residual scan and transparent reporting

## 11. Escalation Rule

If the text has serious factual, citation, logic, or formatting issues that are outside stylistic editing, flag them separately and keep the de-AI edits minimal.
