---
name: implementation-planning
description: Plan a small, direct implementation before editing code
compatibility: opencode
metadata:
  domain: coding
  stage: planning
---

## Use when
Use before making non-trivial code changes.

## Do
- identify the real requirement
- name the smallest correct change
- identify affected files
- identify required tests
- identify real dependencies involved

## Prefer
- direct solutions
- existing code paths
- minimal new abstractions

## Avoid
- speculative refactors
- broad rewrites
- new patterns without need
- changing unrelated files

## Output
Return:
- goal
- files to change
- smallest viable approach
- tests to run
- risks
