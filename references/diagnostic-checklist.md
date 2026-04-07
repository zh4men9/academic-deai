# Diagnostic Checklist

Use this checklist before rewriting. Tag only the categories that are clearly present.

## Generic framing

- What it looks like: broad setup sentences that could fit many papers
- Why it reads as LLM-like: it signals template completion rather than paper-specific thinking
- Safe fix: replace broad framing with the paper's actual problem or omit it
- Do not: add new contextual claims that are not already supported

## Template-like transitions

- What it looks like: repeated connectors such as "Furthermore," "Moreover," or "In addition," used mechanically
- Why it reads as LLM-like: the flow becomes uniformly polished and predictable
- Safe fix: vary structure, merge sentences, or remove the transition
- Do not: make the prose chatty or casual

## Inflated novelty or significance

- What it looks like: sweeping claims about importance, effectiveness, or impact without proportionate support
- Why it reads as LLM-like: the text sounds promotional rather than scholarly
- Safe fix: reduce claim strength to match the evidence
- Do not: introduce new claims or broader impact language

## Vague abstraction

- What it looks like: statements such as "offers a valuable perspective" or "has significant implications" without specifics
- Why it reads as LLM-like: it replaces substance with evaluative fog
- Safe fix: name the actual mechanism, finding, scope, or limitation
- Do not: invent details absent from the source text

## Repetitive authorial scaffolding

- What it looks like: repeated phrases such as "This paper proposes," "This study demonstrates," or "The results show" in close succession
- Why it reads as LLM-like: the prose becomes self-announcing and formulaic
- Safe fix: cut repeated scaffolding and let the content carry the sentence
- Do not: remove needed attribution or lose sentence clarity

## List-like prose disguised as sentences

- What it looks like: chains of parallel claims packed into long sentences with weak hierarchy
- Why it reads as LLM-like: the prose reads like bullet points fused into a paragraph
- Safe fix: split or reorder so the logic is explicit
- Do not: flatten important distinctions

## Over-smoothed logical flow

- What it looks like: every sentence leads seamlessly to the next with no friction, qualification, or scope control
- Why it reads as LLM-like: the argument sounds too frictionless and generic
- Safe fix: restore concrete anchors, limits, or sharper transitions
- Do not: make the paragraph abrupt or incoherent

## Unnatural hedging or certainty

- What it looks like: hedging that feels generic, or certainty that exceeds the evidence
- Why it reads as LLM-like: the calibration sounds mechanically produced
- Safe fix: align modal strength with the actual evidence
- Do not: remove justified caution or add false confidence

## Conclusion clichés

- What it looks like: endings built around generic summary formulas or broad future impact statements
- Why it reads as LLM-like: the conclusion sounds detached from the paper's real contribution
- Safe fix: restate the actual contribution and limits in concrete terms
- Do not: add grand future directions without support

## Cover-letter stiffness

- What it looks like: overly polished politeness, repeated appreciation, or procedural boilerplate
- Why it reads as LLM-like: it sounds like a submission template rather than an author's note
- Safe fix: keep the letter concise, direct, and professional
- Do not: become casual or overly personal

## Residual low-risk prose

- What it looks like: unchanged background sentences that still contain generic praise, empty evaluation, or obvious template wording
- Why it reads as LLM-like: the main rewrite pass may look clean while low-risk residue remains untouched
- Safe fix: flag it for `Unchanged Suspicious Items` or apply a low-risk cleanup
- Do not: overreact by forcing a full rewrite of already acceptable prose

## Surface residue

- What it looks like: broken sentence boundaries, missing spaces, `Fig.7`-style label spacing, or full-width numbering in an English manuscript
- Why it reads as LLM-like: it often survives prose cleanup and makes the output look unfinished
- Safe fix: apply deterministic surface cleanup or surface it in `Unchanged Suspicious Items`
- Do not: treat these issues as claim-level or evidence-level rewriting problems
