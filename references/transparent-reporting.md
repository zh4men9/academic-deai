# Transparent Reporting

Use transparent reporting by default. Do not hide residual risk behind a clean rewrite.

## Reporting Buckets

### Manual Check Items

Use for changed text that remains materially risky after editing.

### Skipped High-Risk Items

Use for text that was intentionally left unchanged because safe editing would require:

- altering inline math or symbol-bearing spans
- restructuring technical skeletons
- weakening precision
- changing attribution or evidence linkage

### Unchanged Suspicious Items

Use for unchanged text that still contains:

- low-risk AI-like residue
- broken sentence boundaries
- missing spaces
- figure or table label spacing residue
- numbering-style mismatch

## Output Blocks

Use these block names exactly:

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

## Quality Rules

- Keep the three residual-risk buckets separate
- Do not report unchanged residue as if it were a changed risky edit
- Do not report skipped text as if it had been revised
- If a bucket is empty, say so briefly rather than omitting the category silently
- Prefer a short truthful report over an over-clean report that hides uncertainty
