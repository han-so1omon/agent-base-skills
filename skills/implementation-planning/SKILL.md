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
- identify affected files
- determine smallest viable change
- identify tests needed
- identify dependencies involved

## Migration scope
If replacing existing functionality:

identify:
- which entry points must change
- which legacy components must be removed
- whether compatibility is actually required
- whether both paths would remain active

prefer a complete switch over dual behavior.

## Prefer
- direct solutions
- existing code paths
- minimal new abstractions

## Avoid
- speculative refactors
- broad rewrites
- adding parallel implementations without need

## Output
Return:
- goal
- files to change
- smallest viable approach
- migration scope (if applicable)
- risks
