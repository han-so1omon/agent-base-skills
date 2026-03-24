---
name: anti-workarounds
description: Detect test-passing shortcuts, hardcoding, stubs, and other fake-work patterns
compatibility: opencode
metadata:
  domain: coding
  stage: review
---

## Use when
Use before claiming completion on any non-trivial task.

## Look for
- fixture-specific branching
- hardcoded outputs
- constant return values for expected cases
- stubs left in production paths
- fake adapters used to satisfy tests
- hidden fallback logic bypassing the real path
- TODO or placeholder logic presented as done

## Check
- does behavior vary correctly with input
- does the implementation generalize beyond the provided examples
- is the real mechanism implemented
- are mocks confined to test-only contexts

## Block completion if
- tests pass only because of a shortcut
- the real dependency path was not implemented
- the code works only for the visible cases

## Output
Return:
- suspicious files
- suspicious logic patterns
- whether each issue blocks completion
