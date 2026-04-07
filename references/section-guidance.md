# Section Guidance

## Title / Keywords

- Intervention level: very low
- Default edit level: `No-op` or `Micro-edit only`
- Goal: remove only obvious generic wording or redundant descriptors
- Avoid: creative rebranding or rhetorical embellishment

## Abstract

- Intervention level: medium
- Default edit level: `Full safe rewrite`
- Goal: increase density, specificity, restraint, and sentence economy
- Remove: generic setup, empty motivation, inflated contribution wording
- Keep: exact task, method, evidence, scope, and concrete detail
- Use default claim mode `balanced` unless the user explicitly chooses otherwise

## Introduction

- Intervention level: low to medium
- Default edit level: `Micro-edit only` or `Full safe rewrite`
- Goal: reduce thesis-template rhetoric and empty field-level motivation
- Remove: broad claims that do not advance the paper's actual setup
- Keep: problem framing, gap statement, contribution logic, and named constraints

## Related Work

- Intervention level: low
- Default edit level: `Micro-edit only`
- Goal: preserve comparison logic and citation structure while reducing repetitive scaffolding
- Remove: repeated "X proposed" patterns only when the comparison stays clear
- Keep: attribution and distinctions among cited works
- Preserve the attribution skeleton before compressing language
- Preserve the mapping between each cited method and its description
- If a citation-bearing comparison, contrast sentence, or multi-citation synthesis line is substantively rewritten, add `Manual Check Items`

## Methods

- Intervention level: very low
- Default edit level: `Micro-edit only`
- Goal: preserve precision
- Remove: only obvious formulaic phrasing that does not touch technical content
- Avoid: paraphrases that could shift definitions, procedure, assumptions, or symbol-bearing clauses
- Do not alter inline variables, equation-bearing spans, or definition skeletons
- If a methods, procedure, or assumptions sentence is rewritten beyond micro-edit scope, add `Manual Check Items`
- If safe cleanup would require changing the technical skeleton, report it in `Skipped High-Risk Items`

## Experiments / Results

- Intervention level: very low
- Default edit level: `Micro-edit only`
- Goal: keep findings exact and proportionate
- Remove: formulaic narration around the findings
- Avoid: smoothing that blurs uncertainty, magnitude, comparison basis, datasets, or environments
- Preserve named algorithms, datasets, environments, and comparison bases
- Exact quantitative result wording, causal explanations, and scope changes should go to `Manual Check Items`
- If symbol-bearing technical prose cannot be safely improved through micro-editing, report it in `Skipped High-Risk Items`

## Discussion

- Intervention level: low
- Default edit level: `Micro-edit only` or `Full safe rewrite`
- Goal: tighten interpretation and keep implications proportional
- Remove: overstated significance and generic impact language
- Keep: evidence-linked interpretation and stated limitations
- If the edit changes causal explanation or generality scope, add `Manual Check Items`

## Conclusion

- Intervention level: medium
- Default edit level: `Full safe rewrite`
- Goal: remove recap clichés and unsupported future-impact claims
- Remove: generic "in summary" endings and broad claims unsupported by results
- Keep: the paper's actual takeaways and reasonable future work
- Default to `balanced` claim mode
- If the rewrite changes interpretation-relevant claim strength, cause, or scope, add `Manual Check Items`

## Cover Letter

- Intervention level: medium
- Default edit level: `Full safe rewrite`
- Goal: sound direct, professional, and non-robotic
- Remove: stiff templates and exaggerated self-praise
- Keep: venue fit, contribution summary, and procedural politeness

## Rebuttal / Response Letter

- Intervention level: low to medium
- Default edit level: `Micro-edit only` or `Full safe rewrite`
- Goal: sound respectful, evidence-based, and steady
- Remove: canned gratitude, defensive phrasing, or formulaic over-smoothing
- Keep: exact reviewer-response mapping and concrete changes
