---
name: robustness-checks
description: Verify behavior remains correct under small realistic changes in inputs or environment
compatibility: opencode
metadata:
  domain: coding
  stage: robustness
---

## Use when
Use after correctness is established.

## Try
- reordered inputs
- renamed files or paths
- fresh environment
- repeated execution
- slightly different valid inputs
- missing optional values
- larger input set
- config changes within valid bounds

## Migration robustness
Ensure system behaves consistently after replacement.

Verify:
- old path does not reappear under variation
- new path remains stable under repeated execution
- behavior does not depend on transitional wiring

## Check
- behavior remains correct
- execution remains idempotent
- failures are graceful
- no hidden assumptions about prior structure

## Output
Return:
- perturbations applied
- brittle assumptions found