---
name: minimal-diff
description: Keep changes small, direct, and proportional to the requested capability
compatibility: opencode
metadata:
  domain: coding
  stage: implementation
---

## Use when
Use during implementation and before finalizing a patch.

## Do
- prefer the smallest correct change
- reuse existing code where reasonable
- delete dead code introduced by the change
- keep functions and files compact

## Avoid
- adding abstraction for one use
- large refactors without explicit need
- extra configuration layers
- helper functions with only one trivial caller

## Check
- is every changed line necessary
- can any branch be removed
- can logic be made more direct
- did scope expand beyond the request

## Output
Return:
- unnecessary complexity found
- files with oversized changes
- lines or sections that can be removed
