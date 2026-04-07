# Contributing

Thank you for contributing to `academic-deai`.

## Scope

This repository maintains a Codex skill for **academic-safe de-AI editing of English scholarly prose**.

Please keep contributions aligned with the core design:

- preserve meaning
- preserve evidence and citation relationships
- preserve concrete detail
- reduce templated or inflated phrasing
- prefer safe restraint over aggressive smoothing

## Source of Truth

- This English repository is the source of truth
- The Chinese repository is a translation-first mirror:
  - [zh4men9/academic-deai-zh](https://github.com/zh4men9/academic-deai-zh)

If behavior changes here, the Chinese mirror should be updated afterward.

## Preferred Contribution Types

- tighten safety rules
- improve section-aware guidance
- improve citation-sensitive handling
- improve detail-preservation rules
- improve transparent reporting
- add better examples or synthetic benchmark cases
- fix unclear wording or contradictory instructions

## Please Avoid

- turning the skill into a general blog humanizer
- adding casual, chatty, or personality-oriented rewrite goals
- weakening precision for fluency
- adding undocumented behavior changes without updating references
- changing claim calibration defaults without updating version history and benchmark notes

## Update Checklist

When changing behavior:

1. update `SKILL.md` if routing or top-level behavior changed
2. update affected files in `references/`
3. update `README.md` if the public description changed
4. update `CHANGELOG.md`
5. refresh example prompts or benchmark/demo files if needed
6. validate the skill with `quick_validate.py`

## Validation

At minimum, contributors should confirm:

- the skill remains structurally valid
- output blocks stay consistent
- risky edits remain restrained
- transparent reporting still separates:
  - `Manual Check Items`
  - `Skipped High-Risk Items`
  - `Unchanged Suspicious Items`

## Release Notes

If a contribution materially changes behavior, add a concise entry to `CHANGELOG.md`.
