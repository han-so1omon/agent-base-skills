---
name: robustness-checks
description: Test whether the implementation still works under small, realistic changes in inputs or environment
compatibility: opencode
metadata:
  domain: coding
  stage: robustness
---

## Use when
Use after basic correctness is established.

## Try
- reordered inputs
- renamed files or paths
- fresh environment
- repeated execution
- slightly different valid inputs
- missing optional values
- larger sample size
- different config values within normal bounds

## Check
- does behavior remain correct
- does repeated execution remain safe
- does the code fail gracefully on edge cases
- does the implementation depend on hidden assumptions

## Avoid
- declaring success because the happy path passed once
- treating “did not crash” as sufficient

## Output
Return:
- perturbations applied
- expected behavior
- observed behavior
- brittle assumptions found
