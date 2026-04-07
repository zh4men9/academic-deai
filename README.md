# Academic De-AI

An open-source Codex skill for reducing AI-like phrasing in **English academic writing** without changing technical meaning, citation intent, evidential strength, or scholarly tone.

This skill is designed for journal and conference prose, not for casual humanization. Its goal is to make academic text sound **less templated, less inflated, and more specific** while keeping the writing formal, evidence-linked, and discipline-appropriate.

## Related Repository

- Chinese mirror: [zh4men9/academic-deai-zh](https://github.com/zh4men9/academic-deai-zh)

## Installation

### Codex

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/zh4men9/academic-deai.git ~/.codex/skills/academic-deai
```

### Claude Code

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/zh4men9/academic-deai.git ~/.claude/skills/academic-deai
```

### Update

If you installed the skill into Codex:

```bash
git -C ~/.codex/skills/academic-deai pull
```

If you installed the skill into Claude Code:

```bash
git -C ~/.claude/skills/academic-deai pull
```

### Verify

Ask your agent:

- `De-AI this abstract without changing technical meaning.`
- `Rewrite this introduction so it sounds less LLM-written but keep the citations and evidence intact.`

## What This Skill Does

- De-AIs abstracts, introductions, related work, discussions, conclusions, cover letters, and rebuttal letters
- Defaults to **balanced** claim calibration rather than blanket softening
- Uses **section-aware** and **risk-aware** editing rules
- Keeps high-risk edits restrained through `Micro-edit only`
- Reports residual risk transparently instead of pretending every pass is clean

This skill is best suited to requests such as:

- "De-AI this abstract."
- "Make this introduction sound less LLM-written."
- "Polish this paragraph without changing technical meaning."
- "Rewrite this response letter so it sounds natural but still professional."

## What This Skill Does Not Do

- It is not a blog or marketing humanizer
- It is not a citation repair tool
- It is not a factual editor
- It is not a journal-formatting tool
- It is not a fluency maximizer at the cost of precision
- It is not a substitute for human review on genuinely risky academic edits

## Directory Layout

```text
academic-deai/
├── SKILL.md
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CHANGELOG.md
├── agents/
│   └── openai.yaml
├── benchmark-demo/
│   ├── README.md
│   ├── cases.md
│   └── results.md
├── examples/
│   ├── README.md
│   └── prompts.md
└── references/
    ├── claim-calibration.md
    ├── core-rules.md
    ├── diagnostic-checklist.md
    ├── manual-check-items.md
    ├── non-goals.md
    ├── rewrite-patterns.md
    ├── section-guidance.md
    ├── surface-hygiene.md
    ├── transparent-reporting.md
    ├── validation-rubric.md
    └── workflow.md
```

## Default v3 Behavior

The current default behavior is:

- `Claim Mode = balanced`
- `Edit Level` chosen from `No-op`, `Micro-edit only`, or `Full safe rewrite`
- Transparent reporting enabled by default
- `Detail Preservation Guard` required before non-trivial rewrites
- `Residual Scan` required after rewriting

For full manuscripts, the skill expects **section-by-section processing** rather than one undifferentiated rewrite pass.

## Canonical Output Blocks

The skill uses these output blocks consistently:

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

The three residual-risk buckets are intentionally separate:

- `Manual Check Items`: changed text that still needs review
- `Skipped High-Risk Items`: text intentionally left unchanged because safe editing would require crossing a risk boundary
- `Unchanged Suspicious Items`: low-risk or surface-level residue left unchanged after the pass

## Claim Modes

This skill supports three claim-calibration modes:

- `closer to source`
  - Use when the user explicitly wants stronger fidelity to the original emphasis
- `balanced`
  - Default mode; preserve the paper's intended direction while reducing obvious inflation
- `conservative`
  - Use only when the user explicitly wants stronger softening

## Safety Model

The skill is designed around these constraints:

1. Preserve meaning
2. Preserve citation and evidence linkage
3. Preserve concrete detail
4. Keep claim strength proportionate
5. Improve naturalness only when the first four remain intact

High-risk text such as methods, exact results, theorem-like language, and symbol-bearing paragraphs defaults to `Micro-edit only`. If safe improvement would require changing technical skeletons, the skill should surface the issue instead of pretending the text was safely rewritten.

## Version History

### v1

The original version established the core academic-safe de-AI workflow:

- diagnosis-first editing
- conservative rewriting
- section-aware handling
- clear boundaries against casual humanization
- protection of technical meaning, citation intent, and scholarly tone

This version proved that the skill could improve low-risk prose safely, especially in abstracts, introductions, and conclusions. Its main limitation was that it still relied too heavily on implicit judgment during difficult cases.

### v2

Version 2 added **controlled automation with explicit risk review**:

- introduced `No-op`, `Micro-edit only`, and `Full safe rewrite`
- added `Manual Check Items` as a dedicated review channel
- tightened defaults for related work, citation-sensitive prose, and high-risk technical sections
- improved behavior on whole-manuscript passes by separating low-risk cleanup from risky edits

This version made the workflow more usable in practice because it reduced unnecessary manual rereading. Its remaining weakness was that reporting could still be too optimistic, and some risky edits still required manual interpretation after the fact.

### v3

Version 3 formalized the behaviors that had previously been handled by manual QA:

- made `balanced` the default claim mode
- added `Detail Preservation Guard`
- added `Residual Scan`
- formalized transparent reporting with three separate residual-risk buckets
- added `Surface Hygiene` as deterministic low-risk cleanup
- strengthened citation-sensitive compression rules
- strengthened symbol-safe and high-risk micro-edit behavior

This is the first version intended for open-source use as a stable, reusable workflow rather than an internal prototype.

## Open-Source Maintenance Policy

- The **English skill is the source of truth**
- The Chinese mirror skill is translation-first and should follow the English structure as closely as possible
- When the English version changes:
  1. Update `SKILL.md`
  2. Update affected `references/`
  3. Update this `README.md` if behavior or version history changed
  4. Sync the Chinese mirror
  5. Re-run validation for both skills

## Chinese Mirror

A Chinese mirror of this skill is maintained in a separate repository:

- [zh4men9/academic-deai-zh](https://github.com/zh4men9/academic-deai-zh)

The Chinese mirror is intended for maintainability and accessibility. It should stay structurally aligned with the English version rather than evolve independently.
