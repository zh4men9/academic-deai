# Manual Check Items

Use `Manual Check Items` as a separate review channel only when changed text remains materially risky.

## What This Block Covers

Use it for:

- changed sentences whose interpretation could matter
- risky claim recalibration
- risky citation-bearing rewrites
- risky methods or result wording changes
- risky causal or scope changes

Do not use it for:

- skipped high-risk text that was intentionally left unchanged
- unchanged suspicious low-risk residue
- harmless low-risk cleanup

Those belong in `Skipped High-Risk Items` or `Unchanged Suspicious Items`, not here.

## When to Generate

Generate a checklist item if any edit:

- changes claim strength in a way that affects interpretation
- changes wording around an exact quantitative result
- rewrites a citation-bearing or attribution-bearing sentence
- rewrites a methods, procedure, or assumptions sentence
- rewrites a causal explanation
- narrows or broadens generality scope
- rewrites a definition-like sentence into a more descriptive sentence
- requires a tradeoff between precision and fluency

Do not generate checklist items for deterministic surface cleanup or minor template cleanup with no interpretation-level risk.

## Required Fields

Each checklist item must contain:

- `Location`
- `Original fragment`
- `Revised fragment`
- `Risk type`
- `Why it needs review`
- `Suggested reviewer question`

## Quality Standard

A good checklist is:

- specific
- short
- tied to one real changed risk
- directly reviewable by a human

A bad checklist is:

- generic
- repetitive
- about unchanged text
- about skipped text
- so long that it recreates full manual editing

## Example

- `Location`: sentence 2
- `Original fragment`: "clearly demonstrating remarkable superiority and strong generalizability across all settings"
- `Revised fragment`: "in the evaluated setting"
- `Risk type`: result-scope narrowing
- `Why it needs review`: the rewrite changes how broad the conclusion sounds
- `Suggested reviewer question`: Does the revised scope still match what the experiment was intended to claim?
