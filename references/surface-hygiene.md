# Surface Hygiene

Use this reference for deterministic low-risk cleanup that should not be treated as claim-level rewriting.

## Covered Issues

- broken sentence-boundary spacing
- missing spaces after periods
- `Fig. 7` / `Table 2` style label spacing
- full-width numbering such as `（1）` / `（2）` inside an English manuscript

## Principles

- Treat these as surface cleanup, not semantic rewriting
- Apply deterministic fixes only when the intended surface form is clear
- If the issue is visible but the correct fix is unclear, surface it in `Unchanged Suspicious Items`

## Safe Examples

- `state.Different` -> `state. Different`
- `Fig.7` -> `Fig. 7`
- `（1）` -> `(1)`

## Do Not

- use surface cleanup as a reason to rewrite nearby technical content
- silently change citation formatting or bibliographic style
- touch inline equations or embedded objects when a simple surrounding fix is enough
