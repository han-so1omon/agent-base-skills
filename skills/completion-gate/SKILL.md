---
name: completion-gate
description: Final review for correctness, scope control, real execution, and maintainability
compatibility: opencode
metadata:
  domain: coding
  stage: final
---

## Use when
Use immediately before declaring a task complete.

## Require
- requested behavior implemented
- smallest reasonable diff
- real tests executed where appropriate
- no blocking workaround patterns
- no unnecessary abstraction added
- no unrelated files changed without reason

## Migration completeness

if replacing prior behavior, verify:

- main execution path uses new implementation
- legacy code removed or clearly marked deprecated
- no silent fallback to old behavior
- no duplicate active logic paths without intent
- imports and dependency wiring updated
- tests exercise new path

## Ask
- does implementation solve actual request
- does system use new behavior
- does code generalize beyond provided inputs
- is anything still partial or stubbed

## Do not
- declare complete if real path not implemented
- present transitional state as finished
- leave dual logic paths unintentionally active

## Output
Return:
- complete or incomplete
- blocking issues
- remaining migration work (if any)
- known limitations
