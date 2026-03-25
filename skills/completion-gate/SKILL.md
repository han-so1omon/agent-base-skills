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
If replacing prior behavior, verify:
- main execution path uses new implementation
- legacy code removed or clearly marked deprecated
- no silent fallback to old behavior
- no duplicate active logic paths without intent
- imports and dependency wiring updated
- tests exercise new path

## Truthfulness and execution match
Before declaring completion, verify that:
- stated plan matches actual changes
- claimed tests were actually run
- claimed integration paths were actually exercised
- claimed migrations actually changed live execution path
- any deviation from earlier plan is explicitly disclosed

Do not report:
- intended work as completed
- assumed behavior as verified behavior
- partial progress as finished implementation

## Ask
- does implementation solve actual request
- does system use new behavior
- does code generalize beyond provided inputs
- is anything still partial or stubbed
- what remains unverified

## Do not
- declare complete if real path not implemented
- present transitional state as finished
- leave dual logic paths unintentionally active

## Output
Return:
- complete or incomplete
- blocking issues
- deviations from plan
- remaining migration work (if any)
- known limitations
- unverified areas