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
- prefer smallest correct change
- reuse existing code where reasonable
- delete dead code introduced by the change
- keep functions and files compact

## Migration awareness

When replacing an implementation:

prefer modifying existing path over introducing parallel structures.

avoid keeping legacy helpers that are no longer used.

small diff does not mean preserving obsolete code.

avoid introducing new abstraction layers solely to preserve legacy behavior.

## Avoid
- abstraction for single use
- unnecessary configuration layers
- duplicate logic paths
- compatibility layers without requirement

## Check
- is each changed line necessary
- can any branch be removed
- did scope expand beyond request
- did legacy code remain unnecessarily

## Output
Return:
- unnecessary complexity found
- unused legacy code detected
- files with oversized changes
