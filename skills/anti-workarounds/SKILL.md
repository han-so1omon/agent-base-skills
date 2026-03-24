---
name: anti-workarounds
description: Detect shortcuts, stubs, hardcoding, compatibility fallbacks, and other fake-work patterns
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
- constant return values
- stubbed logic in production paths
- fake adapters used to satisfy tests
- TODO logic presented as done

## Migration-related shortcuts

flag as suspicious:

- fallback to legacy implementation when new implementation exists
- adapter layers routing back to old logic
- configuration flags selecting old behavior silently
- duplicated logic kept "for compatibility" without requirement
- legacy functions no longer used in main execution path

verify compatibility is actually required.

## Check
- behavior varies correctly with input
- implementation generalizes beyond examples
- real mechanism implemented
- mocks confined to tests only

## Block completion if
- tests pass via shortcut
- legacy path remains unintentionally active
- compatibility logic obscures actual behavior

## Output
Return:
- suspicious files
- suspicious logic patterns
- whether each issue blocks completion
