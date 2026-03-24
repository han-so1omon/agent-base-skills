---
name: completion-gate
description: Final completion review for correctness, scope control, real testing, and maintainability
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
- real tests run as appropriate
- no blocking workaround patterns
- no unnecessary abstraction added
- no unrelated files changed without reason

## Ask
- does it solve the actual request
- does it work through the intended path
- is the patch maintainable
- is anything still partial or stubbed
- what remains unverified

## Do not
- do not say complete if critical behavior is only mocked
- do not hide limitations
- do not describe partial work as finished

## Output
Return:
- complete or incomplete
- evidence supporting that judgment
- known limitations
- next required step if incomplete
