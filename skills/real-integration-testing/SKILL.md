---
name: real-integration-testing
description: Verify behavior through real execution paths, not only mocks or isolated unit tests
compatibility: opencode
metadata:
  domain: coding
  stage: validation
---

## Use when
Use after implementing any change that touches external systems, persistence, APIs, files, queues, auth, or process boundaries.

## Prefer
- real database
- real filesystem
- real HTTP boundary
- real serialization
- real process startup
- real containerized dependencies where available

## Avoid
- mock-only proof of correctness
- claiming completion from unit tests alone
- replacing integration gaps with stubs

## Check
- does the feature work through the public interface
- does it work in a clean environment
- does it exercise the intended dependency path
- does it persist or communicate correctly

## Output
Return:
- integration path tested
- real dependencies exercised
- evidence from execution
- remaining untested boundaries
