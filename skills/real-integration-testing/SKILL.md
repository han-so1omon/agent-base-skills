---
name: real-integration-testing
description: Verify behavior through real execution paths, not only mocks or isolated unit tests
compatibility: opencode
metadata:
  domain: coding
  stage: validation
---

## Use when
Use after implementing changes involving:

persistence
APIs
filesystems
queues
authentication
process boundaries
adapters
data models

## Prefer
- real database
- real filesystem
- real HTTP boundary
- real serialization
- real process startup
- real containerized dependencies where available

## Migration verification
Ensure new implementation is actually exercised.

Verify:
- main execution path reaches new code
- tests do not still rely on legacy wiring
- new behavior is observable externally
- old path is not silently used instead

## Evidence over assertion
Do not claim real integration behavior without execution evidence.

State explicitly:
- what was run
- what environment was used
- what remains unverified

Do not infer successful integration solely from code inspection.

## Avoid
- mock-only validation
- assuming tests cover new path
- partial wiring

## Check
- does feature work through public interface
- does it work in clean environment
- does integration use intended path
- is persistence correct

## Output
Return:
- integration path tested
- evidence of execution
- legacy paths still active (if any)
- unverified boundaries