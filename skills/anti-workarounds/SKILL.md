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
Flag as suspicious:
- fallback to legacy implementation when new implementation exists
- adapter layers routing back to old logic
- configuration flags selecting old behavior silently
- duplicated logic kept "for compatibility" without requirement
- legacy functions no longer used in main execution path

Verify compatibility is actually required.

## Truthfulness checks
Flag as blocking if the implementation narrative does not match the actual work.

Examples:
- claiming a file was updated when it was not
- claiming a new path is used when old wiring remains
- claiming integration was tested when only unit tests ran
- stating intent, then silently doing different work

Require clear separation between:
- planned actions
- completed actions
- inferred outcomes

## Check
- behavior varies correctly with input
- implementation generalizes beyond examples
- real mechanism implemented
- mocks confined to tests only

## Block completion if
- tests pass via shortcut
- legacy path remains unintentionally active
- compatibility logic obscures actual behavior
- reported work does not match actual work

## Output
Return:
- suspicious files
- suspicious logic patterns
- unsupported claims
- whether each issue blocks completion